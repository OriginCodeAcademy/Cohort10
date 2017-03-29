# Very Simple Todo App

For your weekend project you are going to extend your Very Simple Todo App to store Todo items in a SQL database via a Web Service.

<img src="http://i.imgur.com/vhMYF1s.png" />

## Tasks
1. Download and install the following to your Windows machine.
	a) [SQL Server Express 2016](https://go.microsoft.com/fwlink/?LinkID=799012)
	b) [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkID=824938)
2. Create a folder named `15-VSTDA-API` in your `dev` folder.
3. Setup your Git workflow.
  - Initialize an empty git repository in `15-VSTDA-API` by running `git init` in the command prompt.
  - Create a repository on GitHub called `15-VSTDA-API` and follow the instructions to add a remote origin.
4. Create a new Visual Studio solution in this folder called `VSTDA` with a project name of `VSTDA.API` (See todays video).
5. Create an ASP.NET Web API 2 Project
6. Create and add properties to a class called `TodoItem.cs` in your Models folder.
7. Add a new `Data` folder in your API project.
8. Create and setup your Entity Framework DataContext class in a new `VSTDADataContext.cs` stored in your `Infrastructure` folder.
9. Open Package Manager and run the migration commands shown in the video to initialize your SQL database via C#
10. Create a `TodoItemsController.cs` file in your API project, following the wizard to generate an Entity Framework controller in the same way you saw in todays video.
11. At this point - your API is setup. Your challenge now is to integrate this API with your existing Angular application.

## Requirements
- Must be able to Create new Todo items (Which are ultimately stored in a database)
- Must be able to Read Todo items from the Database via the Web Service you created.
- Must be able to Delete Todo items (Items must be deleted from the database)

## Extras
- Add the ability for users to Update Todo items
- Allow users to mark todo items as completed.
	
## Turn In Instructions
* Push your changes to GitHub
	* Push your Angular application to it's existing repository (07-VSTDA)
	* Push your C# Web Service to a new repository called 15-VSTDA-API.
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=15-VSTDA-API&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20did%20you%20enjoy%20most%20about%20this%20project%3F%0A%0A3.%20What%20was%20the%20toughest%20part%3F%0A%0A)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description