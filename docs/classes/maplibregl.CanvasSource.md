[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / CanvasSource

# Class: CanvasSource

[maplibregl](../modules/maplibregl.md).CanvasSource

A data source containing the contents of an HTML canvas. See CanvasSourceOptions for detailed documentation of options.

**`Example`**

```ts
// add to map
map.addSource('some id', {
   type: 'canvas',
   canvas: 'idOfMyHTMLCanvas',
   animate: true,
   coordinates: [
       [-76.54, 39.18],
       [-76.52, 39.18],
       [-76.52, 39.17],
       [-76.54, 39.17]
   ]
});

// update
var mySource = map.getSource('some id');
mySource.setCoordinates([
    [-76.54335737228394, 39.18579907229748],
    [-76.52803659439087, 39.1838364847587],
    [-76.5295386314392, 39.17683392507606],
    [-76.54520273208618, 39.17876344106642]
]);

map.removeSource('some id');  // remove
```

## Hierarchy

- [`ImageSource`](maplibregl.ImageSource.md)

  ↳ **`CanvasSource`**

## Table of contents

### Constructors

- [constructor](maplibregl.CanvasSource.md#constructor)

### Methods

- [getCanvas](maplibregl.CanvasSource.md#getcanvas)
- [listens](maplibregl.CanvasSource.md#listens)
- [load](maplibregl.CanvasSource.md#load)
- [off](maplibregl.CanvasSource.md#off)
- [on](maplibregl.CanvasSource.md#on)
- [once](maplibregl.CanvasSource.md#once)
- [setCoordinates](maplibregl.CanvasSource.md#setcoordinates)
- [setEventedParent](maplibregl.CanvasSource.md#seteventedparent)
- [updateImage](maplibregl.CanvasSource.md#updateimage)

## Constructors

### constructor

• `Private` **new CanvasSource**(`id`, `options`, `dispatcher`, `eventedParent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |
| `options` | `CanvasSourceSpecification` |
| `dispatcher` | [`Dispatcher`](maplibregl.Dispatcher.md) |
| `eventedParent` | [`Evented`](maplibregl.Evented.md) |

#### Overrides

[ImageSource](maplibregl.ImageSource.md).[constructor](maplibregl.ImageSource.md#constructor)

#### Defined in

[src/source/canvas_source.ts:71](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/canvas_source.ts#L71)

## Methods

### getCanvas

▸ **getCanvas**(): `HTMLCanvasElement`

Returns the HTML `canvas` element.

#### Returns

`HTMLCanvasElement`

The HTML `canvas` element.

#### Defined in

[src/source/canvas_source.ts:147](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/canvas_source.ts#L147)

___

### listens

▸ `Private` **listens**(`type`): `any`

Returns a true if this instance of Evented or any forwardeed instances of Evented have a listener for the specified type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type |

#### Returns

`any`

`true` if there is at least one registered listener for specified event type, `false` otherwise

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[listens](maplibregl.ImageSource.md#listens)

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### load

▸ **load**(): `void`

Disables animation. The map will display a static copy of the canvas image.

**`Method`**

pause

**`Instance`**

**`Memberof`**

CanvasSource

#### Returns

`void`

#### Overrides

ImageSource.load

#### Defined in

[src/source/canvas_source.ts:110](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/canvas_source.ts#L110)

___

### off

▸ **off**(`type`, `listener`): [`CanvasSource`](maplibregl.CanvasSource.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`CanvasSource`](maplibregl.CanvasSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[off](maplibregl.ImageSource.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`CanvasSource`](maplibregl.CanvasSource.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`CanvasSource`](maplibregl.CanvasSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[on](maplibregl.ImageSource.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`CanvasSource`](maplibregl.CanvasSource.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`CanvasSource`](maplibregl.CanvasSource.md)

`this` or a promise if a listener is not provided

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[once](maplibregl.ImageSource.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setCoordinates

▸ **setCoordinates**(`coordinates`): [`CanvasSource`](maplibregl.CanvasSource.md)

Sets the image's coordinates and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `coordinates` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |

#### Returns

[`CanvasSource`](maplibregl.CanvasSource.md)

this

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[setCoordinates](maplibregl.ImageSource.md#setcoordinates)

#### Defined in

[src/source/image_source.ts:196](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L196)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`CanvasSource`](maplibregl.CanvasSource.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`CanvasSource`](maplibregl.CanvasSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[setEventedParent](maplibregl.ImageSource.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### updateImage

▸ **updateImage**(`options`): [`CanvasSource`](maplibregl.CanvasSource.md)

Updates the image URL and, optionally, the coordinates. To avoid having the image flash after changing,
set the `raster-fade-duration` paint property on the raster layer to 0.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `Object` | Options object. |
| `options.coordinates?` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |
| `options.url` | `string` | Required image URL. |

#### Returns

[`CanvasSource`](maplibregl.CanvasSource.md)

this

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[updateImage](maplibregl.ImageSource.md#updateimage)

#### Defined in

[src/source/image_source.ts:150](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L150)
