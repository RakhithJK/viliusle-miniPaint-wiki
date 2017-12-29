miniPaint can be extended, modified by adding:

- **modules** - extra functionality accessed from menu.
- **tools** - extra tool in left sidebar.

## Adding modules

1. Register new menu on **src/js/config-menu.js** (example: `<li><a class="trn" data-target="effects/example.functionName" href="#">Title</a>`)
2. Create module file in **src/js/modules/effects/example.js**. From there you can import **src/js/config.js**, **src/js/core/base-layers.js** or any other file including files in `node_modules`.
3. Add class `example `with method `functionName`, which will be called on new menu click.
4. Add your functionality. You can check existing examples to help you.
5. Test.

## Adding tools