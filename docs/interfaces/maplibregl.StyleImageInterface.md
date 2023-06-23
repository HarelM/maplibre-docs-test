[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / StyleImageInterface

# Interface: StyleImageInterface

[maplibregl](../modules/maplibregl.md).StyleImageInterface

Interface for dynamically generated style images. This is a specification for
implementers to model: it is not an exported method or class.

Images implementing this interface can be redrawn for every frame. They can be used to animate
icons and patterns or make them respond to user input. Style images can implement a
[render](maplibregl.StyleImageInterface.md#render) method. The method is called every frame and
can be used to update the image.

 StyleImageInterface

**`See`**

[Add an animated icon to the map.](https://maplibre.org/maplibre-gl-js-docs/example/add-image-animated/)

**`Example`**

```ts
var flashingSquare = {
    width: 64,
    height: 64,
    data: new Uint8Array(64 * 64 * 4),

    onAdd: function(map) {
        this.map = map;
    },

    render: function() {
        // keep repainting while the icon is on the map
        this.map.triggerRepaint();

        // alternate between black and white based on the time
        var value = Math.round(Date.now() / 1000) % 2 === 0  ? 255 : 0;

        // check if image needs to be changed
        if (value !== this.previousValue) {
            this.previousValue = value;

            var bytesPerPixel = 4;
            for (var x = 0; x < this.width; x++) {
                for (var y = 0; y < this.height; y++) {
                    var offset = (y * this.width + x) * bytesPerPixel;
                    this.data[offset + 0] = value;
                    this.data[offset + 1] = value;
                    this.data[offset + 2] = value;
                    this.data[offset + 3] = 255;
                }
            }

            // return true to indicate that the image changed
            return true;
        }
    }
 }

 map.addImage('flashing_square', flashingSquare);
```

## Table of contents

### Properties

- [data](maplibregl.StyleImageInterface.md#data)
- [height](maplibregl.StyleImageInterface.md#height)
- [onAdd](maplibregl.StyleImageInterface.md#onadd)
- [onRemove](maplibregl.StyleImageInterface.md#onremove)
- [render](maplibregl.StyleImageInterface.md#render)
- [width](maplibregl.StyleImageInterface.md#width)

## Properties

### data

• **data**: `Uint8Array` \| `Uint8ClampedArray`

#### Defined in

[src/style/style_image.ts:96](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L96)

___

### height

• **height**: `number`

#### Defined in

[src/style/style_image.ts:92](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L92)

___

### onAdd

• `Optional` **onAdd**: (`map`: [`Map`](../classes/maplibregl.Map.md), `id`: `string`) => `void`

#### Type declaration

▸ (`map`, `id`): `void`

Optional method called when the layer has been added to the Map with [addImage](../classes/maplibregl.Map.md#addimage).

**`Function`**

**`Memberof`**

StyleImageInterface

**`Instance`**

**`Name`**

onAdd

##### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](../classes/maplibregl.Map.md) | The Map this custom layer was just added to. |
| `id` | `string` | - |

##### Returns

`void`

#### Defined in

[src/style/style_image.ts:123](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L123)

___

### onRemove

• `Optional` **onRemove**: () => `void`

#### Type declaration

▸ (): `void`

Optional method called when the icon is removed from the map with [removeImage](../classes/maplibregl.Map.md#removeimage).
This gives the image a chance to clean up resources and event listeners.

**`Function`**

**`Memberof`**

StyleImageInterface

**`Instance`**

**`Name`**

onRemove

##### Returns

`void`

#### Defined in

[src/style/style_image.ts:133](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L133)

___

### render

• `Optional` **render**: () => `boolean`

#### Type declaration

▸ (): `boolean`

This method is called once before every frame where the icon will be used.
The method can optionally update the image's `data` member with a new image.

If the method updates the image it must return `true` to commit the change.
If the method returns `false` or nothing the image is assumed to not have changed.

If updates are infrequent it maybe easier to use [updateImage](../classes/maplibregl.Map.md#updateimage) to update
the image instead of implementing this method.

**`Function`**

**`Memberof`**

StyleImageInterface

**`Instance`**

**`Name`**

render

##### Returns

`boolean`

`true` if this method updated the image. `false` if the image was not changed.

#### Defined in

[src/style/style_image.ts:113](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L113)

___

### width

• **width**: `number`

#### Defined in

[src/style/style_image.ts:88](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_image.ts#L88)
