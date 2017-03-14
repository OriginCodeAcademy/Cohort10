# ESLint

ESLint is a command line tool that will inspect a given JavaScript file for syntax errors.

We can use ESLint in Atom by installing the `linter-eslint` plugin to help us write better code while we're writing it.

## How to get ESLint up and running in Atom

1. Open up terminal and run `npm install -g eslint`. This will install the command line tool.
2. While still in the terminal, run `apm install linter-eslint`. This will install the atom plugin that calls on the command line tool.
3. Navigate to the project directory in which you'd like to setup ESLint and run `eslint --init`. Make sure you select the AirBNB style guide.
4. This will create a `.eslintrc.js` file in your project. Now open this project in Atom using `atom .`
5. As you edit your JavaScript files you will see errors as you write. It will seem annoying at first, but it will help you get better at writing clean JavaScript!
