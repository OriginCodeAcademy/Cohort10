# Top Spots API

# Due 11AM Tuesday

In this assignment you will be returning one more time to the Top Spots website.

Your task is to create an API in Visual Studio that returns a JSON array of top spots in the same format as the file given in the previous project, and modify your Angular code to call your API instead of reading the JSON file from the file system.

Before:
```js
$http.get('topspots.json')
```

After:
```js
$http.get('http://localhost:00000/api/topspots');
```

You must also make sure that your API returns the JSON in camelCase format (the casing standard for JavaScript) as opposed to NormalCase format (the casing standard for C#).

## Tasks
1. Create a folder named `14-TopSpotsAPI` in your `dev` folder. (For Mac owners - create a `dev` folder in your virtual machine.)
2. Setup your Git workflow.
	- Initialize an empty git repository in `14-TopSpotsAPI` by running `git init` in the command prompt.
	- Create a repository on GitHub called `14-TopSpotsAPI` and follow the instructions to add a remote origin.
3. Open Visual Studio, and create a new Project
4. Select `Web > ASP.NET Application`
5. In the wizard, under .NET 4.X, select an Empty ASP.NET Application, and check the Web API checkbox. (Do **not** select the Web API template)
6. Configure the SerializerSettings as shown in todays video
7. Enable Cross Origin Request Sharing (CORS) as shown in todays video
8. Create a Controller class named `TopSpotsController`
9. Create a `TopSpot` class in your Models folder, add the necessary properties of a Top Spot.
10. Create an Action that returns `IEnumerable<TopSpot>`. This Action should read and deserialize the JSON file of top spots into a C# object array, then return the array to end the method.
11. Test your API using Postman
12. Modify your Angular application to call your new API instead of reading from the file system.

## Extras
- Implement the rest of the HTTP Verbs (POST, PUT and DELETE).
	- `POST` will involve reading the JSON from the file system, adding a TopSpot object to the end of the array and then saving the array back to the file system.
	- `PUT` will involve reading the JSON from the file system, finding the TopSpot to be updated, modifying those properties, then saving the array back to the file system.
	- `DELETE` will involve reading the JSON from the file system, finding the TopSpot to be deleted, removing it from the array, then saving the array back to the file system.
- Implement factories in your Angular application

## Turn in instructions
* Push your changes to GitHub
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=14-TopSpotsAPI&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20On%20a%20scale%20of%201-10%2C%20how%20difficult%20did%20you%20find%20this%20assignment%20to%20be%3F%0A%0A3.%20Did%20you%20complete%20the%20extra%20for%20this%20assignment%3F)
	* Include a link to your repository in the description
	* Answer the questions filled out for you in the description
