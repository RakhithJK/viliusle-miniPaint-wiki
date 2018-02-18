Layers class - manages layers. Each layer is object with various types. You can access layers class globally: `window.Layers` or `document.getElementById('miniPaint').contentWindow.Layers` if outside of iframe. 

Layer keys:

- id (int)
- link (image)
- parent_id (int)
- name (string)
- type (string)
- x (int)
- y (int)
- width (int)
- height (int)
- width_original (int)
- height_original (int)
- visible (bool)
- opacity (0-100)
- order (int)
- composition (string)
- rotate (int) 0-359
- data (various data here)
- params (object)
- color {hex}
- status (string)
- filters (array)
- render_function (function)


## Methods

| Method | Arguments | Returns |Comment |
|:---|:---|:---:|:---|
|`add_filter(layer_id, name, params)`|`layer_id`: layer id<br>`name`: filter name<br />`params`: parameters, object| | register new live filter|
|`autoresize(width, height, layer_id, can_automate = true)`|`width`: width<br>`height`: height<br>`layer_id`: layer id><br>`can_automate `: if allow to resize down | | Resize layer based on dimensions, up - always, if 1 layer - down.|
|`convert_layer_to_canvas(layer_id, actual_area = false, can_trim)`|`layer_id`: layer id<br>`actual_area`: actual_area used for resized image<br />`can_trim`: can we trim it? | `canvas`| exports (active) layer to canvas for saving|
|`convert_layers_to_canvas(ctx, layer_id)`|`ctx`: canvas context<br>`layer_id`: layer id|  | exports all layers to canvas for saving |
|`delete(id, force)`|`id`: layer id<br>`force`: force to delete first layer|  | Removes layer |
|`delete_filter(layer_id, filter_id)`|`layer_id`: layer id<br>`filter_id`: filter id| | delets live filter |
|`find_next(id)`|`id`: layer id | `layer`| Find next layer|
|`find_previous(id)`|`id`: layer id | `layer`| Find previous layer|
|`get_dimensions()`| | `object`| Returns canvas dimensions, width and height |
|`get_layer(id)`|`id`: layer id | `layer` or `null` | Get layer|
|`get_sorted_layers()`| | `array`| return sorted layers list (copy) |
|`get_world_coords(x, y)`|`x`: x<br>`y`: y| `object`| returns global position, for example if canvas is zoomed, it will convert relative mouse position to absolute at 100% zoom. |
|`insert(settings, can_automate=true)`|`settings`: object of configs<br>`can_automate`: if additional actions can be applied | `Promise `| Inserts new layer. Async function. |
|`is_layer_empty(id)`|`id`: layer id | `boolean`| Checks if layer empty|
|`layer_clear(id)`|`id`: layer id | | clear layer data |
|`move(id, direction)`|`id`: layer id<br>`direction`: if negative - up, else - down | | move layer up or down|
|`refresh_gui()`|| | renew layers HTML |
|`render(force=false)`|`force`: force to render now |  | Renders all layers and preview on next frame |
|`render_object(ctx, object)`|`ctx`: canvas<br>`object`: layer object| | Renders given object on given canvas |
|`reset_layers(auto_insert=false)`|`auto_insert`: if true, will create 1 empty layer| | removes all layers|
|`select(id)`|`id`: layer id | | marks layer as selected|
|`set_opacity(id, value)`|`id`: layer id<br>`value`: opacity value 0-100| | change layer opacity|
|`toggle_visibility(id)`|`id`: layer id | `layer`| toggle layer visibility|
|`update_layer_image(canvas, layer_id)`|`canvas`: canvas<br>`layer_id`: layer id| | updates layer image data|

