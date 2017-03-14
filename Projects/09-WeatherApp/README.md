# Weather App

In this assignment, you will be building an Angular application that allows a user to search for weather data using the [OpenWeatherMap](http://openweathermap.org/) API in a similar fashion to the following screenshot.

<img src="http://i.imgur.com/vLI7hzb.png" />

## Tasks
1. Create a folder named `WeatherApp` in your `dev` folder.
2. Setup your Git workflow.
  - Initialize an empty git repository in `WeatherApp` by running `git init` in the command prompt.
  - Create a repository on GitHub called `WeatherApp` and follow the instructions to add a remote origin.
3. Open this folder in your favorite text editor (Ours is Sublime!)
4. Create an `index.html` file and a corresponding `index.js` file.
5. Make use of the following AngularJS features to build this application.
  - Create a `controller`. The code for this controller will be very similar in nature to your previous assignment, except it will now call the OpenWeatherMap API.
  - Create an HTML Template to bind the information received from OpenWeatherMap to a view.

## Requirements
- Must be able to search for a city by name and see weather for that location.
- Must have a group of buttons for preloaded cities - when clicked, these buttons should load weather information for that location.
- Must have a search history that tracks the term entered and the time that the term was entered.
- Must be able to handle errors gracefully (Use the [angular-toastr](https://github.com/Foxandxss/angular-toastr) package to show an error to the user if the call to the API fails. It can be installed to your project using `bower install angular-toastr`.)

## Turn in instructions
* Push your changes to GitHub
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=09-WeatherApp&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20does%20it%20mean%20when%20an%20action%20is%20idempotent%3F%0A%0A3.%20Were%20the%20actions%20you%20performed%20against%20the%20Weather%20API%20idempotent%3F%0A%0A4.%20Curveball!%20Explain%20the%20difference%20between%20implicit%20and%20explicit%20coercion.)
  * Include a link to your repository in the description
  * Answer the questions filled out for you in the description
