
# Astro Weight Calculator jQuery

<img src="http://i.imgur.com/x189kBb.png" />

For this assignment, you've been hired by the NASA Jet Propulsion Laboratory to create the now virally popular Astro Weight Calculator using jQuery.

## Tasks

1. Create a folder named `dev` to store all of your future projects.
    - For Mac - create a `dev` folder in your Home Directory.
    - For Windows - create a `dev` folder in the top level of your `C:` drive.
2. Create a folder named `AstroWeightCalculator-jQuery` in your `dev` folder.
3. Initialize an empty git repository in `AstroWeightCalculator-jQuery` by running `git init` in the command prompt.
4. Open this folder in your favorite text editor (Ours is Atom!)
5. Create an `index.html` file and a corresponding `index.js` file.
6. Create a basic HTML page, and make sure it has the following HTML elements.
    - An `input` element for the user to enter their weight.
    - A `select` element for the user to select a planet, populated with `option` elements where the value attribute is set to the surface gravity for that planet, and the content inside of the `option` elements represents the name of that planet.
    - A `button` element for the user to calculate their weight based on the above inputs.
    - A `p` element to display the expected output.
7. Also make sure you reference your `index.js` before the `</body>` tag.
8. Write the following jQuery in your `index.js` file
    - Create a function that will be called when the user clicks on the `button` element you added to your HTML.
    - This function should grab the values entered by the user from the `input` element and the `select` element.
    - The function should then calculate the weight of the user on the selected planet, and show the weight to the user in the `p` element you added to your HTML.
9. Use Bootstrap to style your html according to one of the available layouts.
10. Reverse the following two-dimensional array, then populate the select element options _dynamically_ .:
```javascript
var planets = [
  ['Pluto', 0.06],
  ['Neptune', 1.148],
  ['Uranus', 0.917],
  ['Saturn', 1.139],
  ['Jupiter', 2.640],
  ['Mars', 0.3895],
  ['Moon', 0.1655],
  ['Earth', 1],
  ['Venus', 0.9032],
  ['Mercury', 0.377],
  ['Sun', 27.9]
];     
```
11. To build the planets select element, you should use the jQuery [`$.each()`](http://api.jquery.com/jquery.each/) method and NOT a Javascript `for` loop. Try to program the logic that goes inside of the `each` method using just one line of code!

## Planet Data
`
<table>
    <thead>
        <tr>
            <th>Planet Name</th>
            <th>Multiple of Earth Gravity</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Sun</td>
            <td>27.9</td>
        </tr>
        <tr>
            <td>Mercury</td>
            <td>0.377</td>
        </tr>
        <tr>
            <td>Venus</td>
            <td>0.9032</td>
        </tr>
        <tr>
            <td>Earth</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Moon</td>
            <td>0.1655</td>
        </tr>
        <tr>
            <td>Mars</td>
            <td>0.3895</td>
        </tr>
        <tr>
            <td>Jupiter</td>
            <td>2.640</td>
        </tr>
        <tr>
            <td>Saturn</td>
            <td>1.139</td>
        </tr>
        <tr>
            <td>Uranus</td>
            <td>0.917</td>
        </tr>
        <tr>
            <td>Neptune</td>
            <td>1.148</td>
        </tr>
        <tr>
            <td>Pluto</td>
            <td>0.06</td>
        </tr>
    </tbody>  
</table>
`
For extra credit, write a function to sort the above data from lowest to highest relative gravity and generate the display using a Bootstrap zebra-stripe table.
## Turn In Instructions
* Push your changes to GitHub
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=04-AstroWeightCalculator-jQuery&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20a%20link%20below)%0A%0A2.%20What%20was%20your%20best%20accomplishment%20in%20this%20project%3F%0A%0A3.%20What%20was%20the%20most%20challenging%20piece%20of%20this%20project%20for%20you%3F)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description  
