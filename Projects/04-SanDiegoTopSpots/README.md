# San Diego Top Spots

There are some great places to see in downtown San Diego. In this project you'll get to know a few of them by turning the provided JSON file into a table in HTML with links to Google Maps using jQuery.

<img src="http://i.imgur.com/4UU4Ye4.png" />

## Tasks
1. Create a folder named `SanDiegoTopSpots` in your `dev` folder.
2. Setup your Git workflow.
  - Initialize an empty git repository in `SanDiegoTopspots` by running `git init` in the command prompt.
  - Create a repository on GitHub called `SanDiegoTopspots` and follow the instructions to add a remote origin.
3. Open this folder in your favorite text editor (Ours is Sublime!)
4. Create an `index.html` file and a corresponding `index.js` file.
5. Download [topspots.json](topspts.json) to your `SanDiegoTopspots` folder.
6. Create an HTML `table` structure with the headers you see in the image above.
7. Also make sure you reference your `index.js` before the `</body>` tag.
8. Write the following JavaScript in your `index.js` file
   - Use the `$.getJSON` method to download the contents of [topspots.json](topspts.json)
   - Iterate through the top spots and create rows for each spot.
   - Create a link to the location using the longitude and latitude provided. (Example https://www.google.com/maps?q=33.09745,-116.99572)
9. To start/test your application - navigate to `SanDiegoTopSpots` in command line and run `static .` to start a web server that you can access by going to `http://localhost:8080`. You MUST follow this step and use a static web server in order to read in the contents of a file on your local file system as required in this project.

## Extra Credit
- Play around with the [Google Maps Javascript API](https://developers.google.com/maps/documentation/javascript/) and see if you can draw all the locations in the JSON file into markers on an embedded Google Maps element. (Difficult!)

## Turn In Instructions
* Push your changes to GitHub.
* [Click here to create an issue in the class repository]()
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
