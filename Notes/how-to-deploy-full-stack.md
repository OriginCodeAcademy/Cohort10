# Deployment Steps

**Before you get started!!**<br />
You will be doing all of this in Windows. No apples for you.

## Network Topology

![](https://snag.gy/wgmyEI.jpg)

## Deploying Website to Heroku

- [ ] Navigate to your website folder (`cd <where_you_keep_your_website>`)
- [ ] Install the following npm packages to your project

```
$ npm install express bower --save
```

- [ ] Add a `scripts` section to your `package.json` file as follows. This ensures that Heroku will download your bower packages once code is deployed to the server.

`package.json`<br />

```js
{
  "name": "vehicle-manager-frontend",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "postinstall": "bower install"
  },
  "devDependencies": {
    "browser-sync": "^2.18.8",
    "gulp": "^3.9.1",
    "gulp-inject": "^4.2.0",
    "wiredep": "^4.0.0"
  }
}
```


- [ ] Add a file called `server.js` to the root of your project folder. This will spin up a web server that will serve your web assets once deployed to Heroku.

```js
// Require modules (similar to Angular Dependency Injection)
const express = require('express');
const app = express();
const path = require('path');

// Tell express to make all files in `/src` available
app.use(express.static('src'));

// Setup the default route to serve the index page
app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname + '/src/index.html'));
});

// Either use the Heroku port, or use 4200
const port = process.env.PORT || 4200;

// Start the web server
app.listen(port, () => {
    console.log('App listening on port ' + port);
});
```

- [ ] Change the `apiUrl` value in `src/app/app.module.js` to `https://{{initials}}-vehicle-api.azurewebsites.net/api/`

- [ ] Add/Commit/Push your latest changes to Git.

```
$ git add .
$ git commit -m "Ready for deployment"
$ git push origin master
```

- [ ] Sign up for a [Heroku account](https://www.heroku.com)
- [ ] Download and install the [Heroku Toolbelt for Windows](https://devcenter.heroku.com/articles/heroku-cli)
- [ ] Run the following terminal commands to deploy your application

```
$ heroku login
$ heroku apps:create {{initials}}-vehicle-manager    <-- Use your own initials!
$ git push heroku master
```

## Deploying API to Azure

### Step 1 - Sign up for Windows Azure

- [ ] First, sign up for Microsoft's [VS Dev Essentials](https://www.visualstudio.com/dev-essentials/) program. (Click `Join or access now`)
- [ ] Login to your Microsoft account (create one if you don't have one)
- [ ] Click the Activate link for Azure

<img src="https://i.snag.gy/t2z3ET.jpg" width="300" />

- [ ] Fill out the form that appears (You will need to enter a credit card number, **you will not be charged for any service**. After a year, the trial will simply end.)

Congratulations! You are now the proud owner of a Microsoft Azure account. You have $300 to spend in one year.

### Step 2 - Deploy your backend to Azure

- [ ] Sign into your Microsoft Account in Visual Studio (You might have already done this, check the top right of Visual Studio)

<img src="https://i.snag.gy/2MRG6d.jpg" />

- [ ] Navigate to your API folder (`cd <where_you_keep_your_api>`)
- [ ] Check your latest code to Git
- [ ] Add the following code to the constructor in `Data/VehicleManagerDataContext.cs` (You will need to add `using VehicleManager.API.Migrations` to the top of this file)

```csharp
public VehicleManagerDataContext() : base("VehicleManager")
{
    Database.SetInitializer(
	    new MigrateDatabaseToLatestVersion<VehicleManagerDataContext, Configuration>()
    );
}
```

- [ ] Right click on your Project and click Publish

<img src="https://i.snag.gy/sJBUfe.jpg" width="300" />

- [ ] Make sure the next screen looks like this, then hit Publish

<img src="https://i.snag.gy/PxXnLZ.jpg" width="300" />

- [ ] On the next screen, perform the following steps
	- [ ] Click `Change Type` and select `API App`  (It's a small link immediately under Microsoft Account)
	- [ ] Name your web app under `API App Name` "{{initials}}-vehicle-api" (example `cw-vehicle-api`)
	- [ ] Select your Subscription
	- [ ] Click New under `Resource Group`
		- [ ] Enter `VehicleManager` as a resource name
	- [ ] Click New under `App Service Plan`
		- [ ] Enter `VehicleManager` for `App Service Plan`
		- [ ] Choose `West US` for Location
		- [ ] Choose `Free` for Size
	- [ ] Click `Services` on the left
		- [ ] Click the plus icon next to `SQL Database`
			- [ ] Click New next to SQL Server
				- [ ] Fill out this form and click OK (It doesn't matter what you name your server)
			- [ ] Enter `VehicleManager` for both `Database Name` and `Connection String Name`
			- [ ] Click OK
	- [ ] Click `Create` and watch your API/Database be published all at once!

## You're done!

Go load `https://{{initials}}-vehicle-manager.herokuapp.com` and show off your efforts to your friends!
