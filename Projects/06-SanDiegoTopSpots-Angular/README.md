# San Diego Top Spots in AngularJS

There are some great places to see in downtown San Diego. In this project you'll get to know a few of them by turning the provided JSON file into a table in HTML with links to Google Maps using Angular.

<img src="http://i.imgur.com/4UU4Ye4.png" />

## Tasks
1. Create a folder named `TopspotsAngular` in your `dev` folder.
2. Setup your Git workflow.
  - Initialize an empty git repository in `TopspotsAngular` by running `git init` in the command prompt.
  - Create a repository on GitHub called `TopspotsAngular` and follow the instructions to add a remote origin.
3. Open this folder in your favorite text editor (Ours is Sublime!)
4. Create an `index.html` file and a corresponding `index.js` file.
5. Download [topspots.json]("https://github.com/OriginCodeAcademy/2016-SC-WinterCohort/tree/master/Projects/Week%201/05-SanDiegoTopSpots/topspots.json") to your `TopspotsAngular` folder.
6. Create an HTML `table` structure with the headers you see in the image above.
7. Also make sure you reference your `index.js` before the closing `</body>` tag.
8. Add the following to your index.html file
	- an ng-app directive in the `<html>` tag.
	- an ng-controller directive in the `<body>` tag.
	- an ng-repeat directive to generate the rows of Top Spots data
9. Write the following JavaScript in your `index.js` file
	- Create an Angular module.
	- Create an Angular controller.
	- Use the `$http` angular service to read the contents of `topspots.json` into a local variable in your controller.
	- Use $scope in your controller to bind the JSON data received to the view elements in your html.
10. To start/test your application - navigate to `TopspotsAngular` in command line and run `static .` to start a web server that you can access by going to `http://localhost:8080`.

## Extras
- Can you create a form to add new locations to the topspots array?
- Can you find an Angular plugin to show the locations on a google map?
- Try updating this project so that it runs locally using the gulfile in the Server Side JavaScript setup in our cohort's Required Tools: https://github.com/OriginCodeAcademy/2016-SC-WinterCohort/tree/master/Notes/Required%20Tools/Server%20Side%20JS%20setup

## Turn In Instructions
* Push your changes to GitHub using `git push origin master`
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=06-SanDiegoTopSpots-Angular&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20did%20you%20enjoy%20most%20about%20this%20project%3F%0A%0A3.%20What%20was%20the%20toughest%20part%3F%0A%0A)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
