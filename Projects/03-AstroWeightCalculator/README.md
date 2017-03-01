# Astro Weight Calculator

<img src="http://i.imgur.com/x189kBb.png" />

For this assignment, you've been hired by the NASA Jet Propulsion Laboratory to create a simple weight calculator that would be used by future astronauts to calculate their weight on the surface of the 9 planets (ok, 8 planets and a dwarf!) as well as the moon and the sun of our solar system.

## Considerations
- It is **not** necessary to style your HTML to look like the example above. You can be creative or uncreative as you want. That being said, one of the extras is to style it exactly as above.

## Tasks

1. Create a folder named `dev` to store all of your future projects.
    - For Mac - create a `dev` folder in your Home Directory.
    - For Windows - create a `dev` folder in the top level of your `C:` drive.
2. Create a folder named `AstroWeightCalculator` in your `dev` folder.
3. Initialize an empty git repository in `AstroWeightCalculator` by running `git init` in the terminal.
4. Open this folder in Sublime Text.
5. Create an `index.html` file and a corresponding `index.js` file.
6. Create a basic HTML page, and make sure it has the following HTML elements.    -
    - An `input` element for the user to enter their weight.
    - A `select` element for the user to select a planet, populated with `option` elements where the value attribute is set to the surface gravity for that planet, and the content inside of the `option` elements represents the name of that planet.
    - A `button` element for the user to calculate their weight based on the above inputs.
    - A `p` element to display the expected output.
7. Also make sure you reference your `index.js` before the `</body>` tag.
8. Write the following JavaScript in your `index.js` file
    - Populate the select element options _dynamically_ using this array of objects:
```js
var planets = [
  {planet: 'Sun', gravity: 27.9},
  {planet: 'Mercury', gravity: 0.377},
  {planet: 'Venus', gravity: 0.9032},
  {planet: 'Earth', gravity: 1},
  {planet: 'Moon', gravity: 0.1655},
  {planet: 'Mars', gravity: 0.3895},
  {planet: 'Jupiter', gravity: 2.640},
  {planet: 'Saturn', gravity: 1.139},
  {planet: 'Uranus', gravity: 0.917},
  {planet: 'Neptune', gravity: 1.148},
  {planet: 'Pluto', gravity: 0.06}
];
```
  - Create a function that will be called when the user clicks on the `button` element you added to your HTML.
  - This function should grab the values entered by the user from the `input` element and the `select` element.
  - The function should then calculate the weight of the user on the selected planet, and show the weight to the user in the `p` element you added to your HTML.

## Extras
- Add a checkbox that when clicked, either shows or hides Pluto as an option in the dropdown.
- Style your HTML to match the example image above exactly.

## Turn In Instructions
* Push your changes to GitHub
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=03-AstroWeightCalculator&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20a%20link%20below)%0A%0A2.%20What%20was%20your%20best%20accomplishment%20in%20this%20project%3F%0A%0A3.%20What%20was%20the%20most%20challenging%20piece%20of%20this%20project%20for%20you%3F)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
