This project use webpack and npm. Npm helps to install and update all libraries with only 1 simple command `npm update`. Webpack helps to bundle many diffrend js, css files into 1 bundle.js and improve page load time a lot.

## Requirements

- **npm** - a package manager, helps to manage dependencies. Update it to latest version using `npm install npm@latest -g`

Also these are required, unless using npx mode (will execute local packages, not global):

- **webpack** - install using `npm install -g webpack` (**optional**)
- **webpack-dev-server** - install using `npm install -g webpack-dev-server` (optional, but very useful) (**optional**)

## Build instructions

- `git clone https://github.com/viliusle/miniPaint.git`
- `cd miniPaint`
- `npm update` - it will install all dependencies from **package.json** file into **node_module** folder
- There are 2 ways to edit files:
  - using `webpack-dev-server` - it will create simple local server with live reload. Start server, edit files and debug using http://localhost:8080/ URL. Recommended way.
  - Edit files and run `webpack` or `npx webpack` command to generate/update **dist/bundle.js**

p.s. **index.html** has everything it needs, dont add additional css or js files here.

## Useful commands

- `webpack` - creates or updates **dist/bundle.js** file, so you changes will be visible.
- `npx webpack` - same as `webpack`, but will use local webpack, not global.
- `webpack -p` - build for production
- `webpack-dev-server` - creates http://localhost:8080/ server for easy development.
- `npm update` - it will install all required libraries from **package.json** file into **node_module** folder.

Related: [Contributing](/viliusle/miniPaint/wiki/Contributing)