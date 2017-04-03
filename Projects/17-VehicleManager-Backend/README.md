# Vehicle Manager (Backend)

## Table of Contents
- [Setup the Project](#setup-the-project)
- [Create Model Classes](#create-model-classes)
- [Create Data Context](#create-data-context)
- [Setup Relationships using ModelBuilder](#setup-relationships-using-modelbuilder)
- [Use `.Select` to extract only required data for GET actions](#use-select-to-extract-only-required-data-for-get-actions)
- [Turn in your project](#turn-in-instructions)

## Setup the Project

> First things first, let's go ahead and create a new Visual Studio project in which to build our backend.

- [ ] Create a new repository on GitHub called `vehiclemanager-api`.

- [ ] Create a new ASP.NET project called `VehicleManager.API` (Remember to call your solution `VehicleManager`)

- [ ] Initialize a `git` repository to contain the new project. (You should also do an initial commit and push your empty project to GitHub at this point.)

- [ ] Download the following NuGet packages to the project.
	* [ ] `EntityFramework`
	* [ ] `Microsoft.AspNet.WebApi.Cors`

- [ ] Enable CORS in `App_Start/WebApiConfig.cs` (See VSTDA)
- [ ] Enable Camel Case Resolving in `App_Start/WebApiConfig.cs` (See VSTDA)
- [ ] Disable XML formatting in `App_Start/WebApiConfig.cs` (See VSTDA)

## Create Entity Classes

> Phew! Ok, now we've setup the project - let's start building our backend. The first thing you need to do is create Classes that model the types of data that are going to be stored in the SQL database (entities).

> Take some time to review the following Entity Relationship Diagram so you have a good feel for the relations between the three entities we will need for this app.

![](http://i.imgur.com/Oy1FmSv.png)

* [ ] Create the following three classes in the `Models` folder of your project.
* [ ] Vehicle
	* _Scalar Properties_
		* [ ] VehicleId (int, PK)
		* [ ] Make (string)
		* [ ] Model (string)
		* [ ] Year (string)
		* [ ] Color (string)
		* [ ] VehicleType (string)
		* [ ] RetailPrice (decimal)
	* _Navigation Properties_
		* [ ] `public virtual ICollection<Sale> Sales { get; set; }`
* [ ] Customer
	* _Scalar Properties_
		* [ ] CustomerId (int, PK)
		* [ ] FirstName (string)
		* [ ] LastName (string)
		* [ ] EmailAddress (string)
		* [ ] Telephone (string)
		* [ ] DateOfBirth (DateTime?) (See [nullable types in C#](https://msdn.microsoft.com/en-us/library/1t3y8s4s.aspx))
	* _Navigation Properties_
		* [ ] `public virtual ICollection<Sale> Sales { get; set; }`
* [ ] Sale
	* _Scalar Properties_
		* [ ] SaleId (int, PK)
		* [ ] VehicleId (int, FK)
		* [ ] CustomerId (int, FK)
		* [ ] SalePrice (decimal)
		* [ ] InvoiceDate (DateTime?)
		* [ ] PaymentReceivedDate (DateTime?)
	* _Navigation Properties_
		* [ ] `public virtual Vehicle Vehicle { get; set; }`
		* [ ] `public virtual Customer Customer { get; set; }`

## Create Data Context

> After defining our entities, it's time to create a DataContext. As you already know, the DataContext acts as a sort of buffer between ASP.NET and SQL - eliminating the need to write SQL queries in C#.

- [ ] Create a folder called `Data`
- [ ] Create a class called `VehicleManagerDataContext`.
- [ ] Add your Constructor (same as VSTDA)
- [ ] Add your DbSets (same as VSTDA)

## Setup Relationships with ModelBuilder

> Setup the relationships between your 3 model classes as shown in Monday's video. Here are the relationships explained in text form.

- [ ] One `Vehicle` can have many `Sales`
- [ ] One `Customer` can have many `Sales`

## Run Migrations

> At this point we're ready to generate a database. Run the following three commands in Package Manager Console.

```
Enable-Migrations
Add-Migration InitialMigration
Update-Database
```

## Create Controllers

> Create the following controllers, using the Web API 2 Controller with Entity Framework Actions scaffolder.

- [ ] `CustomersController` (`api/customers`)
- [ ] `VehiclesController` (`api/vehicles`)
- [ ] `SalesController` (`api/sales`)

## Use `.Select` to extract only required data for GET actions

> A problem we will have down the road is that the more information we add to our database, the bigger our `GetAll` responses are going to become, because ASP.NET serializes every relationship associated with a given object.

> For example, getting a single Vehicle will pull down the following

```
Vehicle (the object we want)
	- All sales for the vehicle
		- Each sale has the customer for the sale
			- That customer has all their sales serialized also
				- Each of THOSE sales has the customer associated with it..
					- This goes on forever.
```

> To get around this, we can make use of the [`.Select`](https://www.dotnetperls.com/select) method, which behaves similar to the [`.map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) function in JavaScript.

> You may also want to take the time to look into what a Lambda function is in C#. (TL;DR - It's basically the same thing as a callback in JavaScript.)

Example Before

```csharp
public class VehiclesController
{
	public IQueryable<Vehicle> GetVehicles()
	{
		return db.Vehicles;
	}
}
```

Example After

```csharp
public class VehiclesController
{
	public IHttpActionResult GetVehicles()
	{
		return db.Vehicles.Select(v => new
		{
			v.VehicleId,
			v.Make,
			v.Model,
			v.Color,
			v.Year
		});
	}
}
```

## Extras

#### Optional Tables
> Currently, `VehicleType` and `Color` are strings, which is fine technically - but isn't the best approach in terms of User Experience, as the user will have to "conjure a value" to populate the variable.

> A better approach is to give the user a prepopulated list of Colors or VehicleTypes and let the user decide based on that list.

> The best way to approach this is to store all possible choices in a SQL table, then link the choices (Colors, VehicleTypes) to the root entity (Vehicle) via a foreign key.

> Here are some optional tables for you to implement:

VehicleType

```
* VehicleType
	* VehicleTypeId (int, PK)
	* Description
```

Color

```
* Color
	* ColorId (int, PK)
	* Description
```

If you choose to implement these tables, you need to modify the `Vehicle` class and add new relationship configurations to the data context as shown below.


Before<br />

```csharp
// Models/Vehicle.cs
public class Vehicle
{
	public string Color { get; set; }
}
```

After<br />

```csharp
// Models/Vehicle.cs
public class Vehicle
{
	public int ColorId { get; set; }

	public virtual Color Color { get; set; }
}

// Models/Color.cs
public class Color
{
	public int ColorId { get; set; }
	public string Description { get; set; }

	public virtual ICollection<Vehicle> Vehicles { get; set; }
}

// Data/VehicleManagerDataContext.cs
public class VehicleManagerDataContext : DbContext
{
	...

	protected override void OnModelCreating(DbModelBuilder modelBuilder)
	{
		modelBuilder.Entity<Color>()
			.HasMany(c => c.Vehicles)
			.WithRequired(v => v.Color);
			.HasForeignKey(v => v.ColorId);
	}
}
```

### Turn-in Instructions
* Push your Visual Studio solution to a GitHub repository
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=17-VehicleManager-Backend&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20Describe%20the%20difference%20between%20%22Code%20First%22%20and%20%22Database%20First%22%20in%20relation%20to%20Entity%20Framework.%0A%0A3.%20Describe%20the%20difference%20between%20Static%20and%20Dynamic%20polymorphism%20in%20relation%20to%20C%23.%0A%0A4.%20Describe%20the%20difference%20between%20a%20Class%20and%20an%20Object%20in%20C%23.)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
