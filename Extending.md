miniPaint can be extended, modified by adding:

- **modules** - extra functionality accessed from menu.
- **tools** - extra tool in left sidebar. It can be accessed fast and easy, but GUI has limited numbers of space there.

## Adding modules

1. Register new menu on **src/js/config-menu.js** (example: `<li><a class="trn" data-target="effects/example.functionName" href="#">Title</a>`)
2. Create module file in **src/js/modules/effects/example.js**.
3. Add class with method `functionName`, which will be called on new menu click.
4. Add your functionality. You can check existing examples to help you.
5. Test.

## Adding tools

1. Register your new tool in **src/js/config.js**, on variable `config.TOOLS`.
2. Create new file **src/js/tools/example.js**.
3. Add class with methods `load` (will be called on app load one time) and `render` (will be called every time when app needs to re-render canvas).
4. Add your functionality. You can check existing examples to help you.
5. Test.

### Notes

- To include files, for example something.js, use: `import config from './something.js';` (path must be related). Most common included files will be **src/js/config.js**, **src/js/core/base-layers.js**.
- Don't forget to export yourclass, for example: `export default Example_class;`
- Make sure your code works with all types of objects. To test all types, open `images/json-test.json` file with miniPaint.
- You also can access some global objects after onload event: `window.Layers`, `window.AppConfig`.

**Related**: [Examples](/viliusle/miniPaint/wiki/Examples), [Base_layers_class](/viliusle/miniPaint/wiki/Class:-Base_layers_class)