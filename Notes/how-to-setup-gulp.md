# How to use Gulp in your projects

## High Level Steps
- Install `gulp` globally
- Create a `package.json` in your web folder using `npm init`
- Create a `bower.json` in your web folder using `bower init`
- Add your `gulpfile.js` to your web folder
- Override `bootstrap` and `font-awesome` main definitions
- Add hooks in index.html

## Install `gulp` globally
Before we can use `gulp`, we need to make sure it can be executed on the command line. To ensure this, open up your terminal/command prompt and type:

`npm install gulp -g`

This will put `gulp` in your PATH so it can be run from the command line.

## Create a `package.json` file in your web folder
1. Navigate to your web folder in the terminal
2. Run `npm init` and keep pressing enter to choose the default options.
3. This creates a `package.json` file in your project.

## Create a `bower.json` file in your web folder

1. Similar to `npm init`, navigate to your web folder in the terminal
2. Run `bower init` - **when it asks if you'd like to include installed dependencies, choose yes.**
3. This creates a `bower.json` file in your project.

## Install the folowing gulp extensions
### Install gulp
(Yes, I know you think you already did this - but this time we're installing gulp into the project, not globally.)

`npm install gulp --save`

### Install gulp-inject
`npm install gulp-inject --save`

### Install wiredep
`npm install wiredep --save`

### Install browser-sync
`npm install browser-sync --save`

## Add this `gulpfile.js` to your web folder
```js
const gulp = require('gulp');const inject = require('gulp-inject');const wiredep = require('wiredep').stream;const browserSync = require('browser-sync');/* injects the files that you create */gulp.task('inject', function() {	var sources = [										// Define the files we'd like to inject		'./app/**/*.module.js', 						// *.module.js files go first		'./app/**/*.js', 								// *.js files come next		'./app/**/*.css'								// *.css files come next	];    gulp.src('./index.html') 							// Read your index.html        .pipe(inject(sources, { relative: true })) 		// Pipe it through gulp-inject        .pipe(gulp.dest('./')); 						// Write it out to ./});/* injects your bower dependencies */gulp.task('inject:bower', ['inject'], function() {    return gulp.src('./index.html') 					// Read your index.html        .pipe(wiredep()) 								// Pipe it through wiredep        .pipe(gulp.dest('./')); 						// Write it out to ./});/* watches for changes made to your files */gulp.task('watch', function() {    return gulp        .watch('./app/**/*', ['reload']); 				// Watch for any changes in your app folder    													// which will trigger the 'reload' task});/* reloads the browser */gulp.task('reload', function() {    return browserSync.reload(); 						// reloads your app through browser-sync})/* starts a browser-sync server */gulp.task('serve', ['inject:bower', 'watch'], function() {    return browserSync.init({ 							// starts a browser-sync service        server: './' 									// serving the ./ directory    })});
```

## Override `bootstrap` and `font-awesome` main definitions
In your `bower.json` file, add the following object between the `ignore` array and the `dependencies` object.

```json
  "overrides": {    "font-awesome": {      "main": "css/font-awesome.css"    },    "bootstrap": {      "main": [        "dist/css/bootstrap.css",        "dist/js/bootstrap.js"      ]    }  }
```

## Add hooks to index.html
In your `index.html` file, add the following "hooks", similar to the example file.

```html
<html>

	<head>
		<!-- bower:css -->
		<!-- endbower -->
	
		<!-- inject:css -->
		<!-- endinject -->
	</head>

	<body>
		<!-- bower:js -->
		<!-- endbower -->
		
		<!-- inject:js -->
		<!-- endinject -->
	</body>

</html>
```

## Run gulp tasks!
Now, simply run `gulp serve` in the command line to run your gulp file. This will:

- Inject all your bower dependencies as `<script>` or `<link>` elements
- Inject all your custom CSS files as `<link>` elements
- Inject all your custom JS files as `<script>` elements
- Start a web server on port `3000`
- Reload the page automatically when changes to files are detected. (**Awesome!!**)