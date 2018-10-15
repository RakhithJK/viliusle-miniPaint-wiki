This project use webpack and npm. Npm helps to install and update all libraries with only 1 simple command `npm update`. Webpack helps to bundle many diffrend js, css files into 1 bundle.js and improve page load time a lot.

## Requirements

- **npm** - package manager, helps to manage dependencies. Update it to latest version using `npm install npm@latest -g`. Make sure you have at least version 6: `npm run build`

## Build instructions

- `git clone https://github.com/viliusle/miniPaint.git`
- `cd miniPaint`
- `npm install` - it will install all dependencies from **package.json** file into **node_module** folder
- There are 2 ways to edit files:
  - Run `npm run server` - it will create simple local server (webpack-dev-server) with live reload. Run command, edit files and debug using http://localhost:8080/ URL. **Recommended way**.
  - Edit files and run `npm run dev` command to generate/update **dist/bundle.js**

To generate minified code for production, run `npm run build`.
Code is build using webpack.

## Useful commands

- `npm update` - it will install all required libraries from **package.json** file into **node_module** folder.
- `npm run` - list all possible npm run commands. (AKA help)
- `npm run server` - creates http://localhost:8080/ server for easy development (also live reload)
- `npm run dev` - creates or updates **dist/bundle.js** file, so you changes will be visible.
- `npm run build` - build for production

Related: [Contributing](/viliusle/miniPaint/wiki/Contributing)