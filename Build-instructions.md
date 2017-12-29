This project use webpack and npm. Npm helps to install and update all libraries with only 1 simple command `npm update`. Webpack helps to bundle many diffrend js, css files into 1 bundle.js and improve page load time a lot.

## Requirements

- **npm** - a package manager, helps to manage dependencies.
- **webpack** - install using `npm install -g webpack`
- **webpack-dev-server** - install using `npm install -g webpack-dev-server` (optional, but very useful)

## Build instructions

- `git clone https://github.com/viliusle/miniPaint.git`
- `cd miniPaint`
- `npm update` - it will install all dependencies from **package.json** file into **node_module** folder
- There are 2 ways to edit files:
  - using `webpack-dev-server` - it will create simple local server with live reload. Start server, edit files and debug using http://localhost:8080/ URL. Recommended way.
  - Edit files and run `webpack` command to generate/update **dist/bundle.js**

p.s. **index.html** has everything it needs, dont add additional css or js files here.

## Useful commands

- `webpack` - creates or updates **dist/bundle.js** file, so you changes will be visible.
- `webpack -p` - build for production
- `webpack-dev-server` - creates http://localhost:8080/ server for easy development.
- `npm update` - it will install all required libraries from **package.json** file into **node_module** folder.

Related: [Extending app](/viliusle/miniPaint/wiki/Extending)