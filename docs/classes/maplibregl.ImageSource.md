[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / ImageSource

# Class: ImageSource

[maplibregl](../modules/maplibregl.md).ImageSource

A data source containing an image.
(See the [Style Specification](https://maplibre.org/maplibre-style-spec/#sources-image) for detailed documentation of options.)

**`Example`**

```ts
// add to map
map.addSource('some id', {
   type: 'image',
   url: 'https://www.maplibre.org/images/foo.png',
   coordinates: [
       [-76.54, 39.18],
       [-76.52, 39.18],
       [-76.52, 39.17],
       [-76.54, 39.17]
   ]
});

// update coordinates
var mySource = map.getSource('some id');
mySource.setCoordinates([
    [-76.54335737228394, 39.18579907229748],
    [-76.52803659439087, 39.1838364847587],
    [-76.5295386314392, 39.17683392507606],
    [-76.54520273208618, 39.17876344106642]
]);

// update url and coordinates simultaneously
mySource.updateImage({
   url: 'https://www.maplibre.org/images/bar.png',
   coordinates: [
       [-76.54335737228394, 39.18579907229748],
       [-76.52803659439087, 39.1838364847587],
       [-76.5295386314392, 39.17683392507606],
       [-76.54520273208618, 39.17876344106642]
   ]
})

map.removeSource('some id');  // remove
```

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`ImageSource`**

  ↳↳ [`CanvasSource`](maplibregl.CanvasSource.md)

  ↳↳ [`VideoSource`](maplibregl.VideoSource.md)

## Implements

- [`Source`](../interfaces/maplibregl.Source.md)

## Table of contents

### Constructors

- [constructor](maplibregl.ImageSource.md#constructor)

### Methods

- [listens](maplibregl.ImageSource.md#listens)
- [off](maplibregl.ImageSource.md#off)
- [on](maplibregl.ImageSource.md#on)
- [once](maplibregl.ImageSource.md#once)
- [setCoordinates](maplibregl.ImageSource.md#setcoordinates)
- [setEventedParent](maplibregl.ImageSource.md#seteventedparent)
- [updateImage](maplibregl.ImageSource.md#updateimage)

## Constructors

### constructor

• `Private` **new ImageSource**(`id`, `options`, `dispatcher`, `eventedParent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |
| `options` | `VideoSourceSpecification` \| `ImageSourceSpecification` \| `CanvasSourceSpecification` |
| `dispatcher` | [`Dispatcher`](maplibregl.Dispatcher.md) |
| `eventedParent` | [`Evented`](maplibregl.Evented.md) |

#### Overrides

Evented.constructor

#### Defined in

[src/source/image_source.ts:91](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L91)

## Methods

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

[Evented](maplibregl.Evented.md).[listens](maplibregl.Evented.md#listens)

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### off

▸ **off**(`type`, `listener`): [`ImageSource`](maplibregl.ImageSource.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`ImageSource`](maplibregl.ImageSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`ImageSource`](maplibregl.ImageSource.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`ImageSource`](maplibregl.ImageSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`ImageSource`](maplibregl.ImageSource.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`ImageSource`](maplibregl.ImageSource.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setCoordinates

▸ **setCoordinates**(`coordinates`): [`ImageSource`](maplibregl.ImageSource.md)

Sets the image's coordinates and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `coordinates` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |

#### Returns

[`ImageSource`](maplibregl.ImageSource.md)

this

#### Defined in

[src/source/image_source.ts:196](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L196)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`ImageSource`](maplibregl.ImageSource.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`ImageSource`](maplibregl.ImageSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### updateImage

▸ **updateImage**(`options`): [`ImageSource`](maplibregl.ImageSource.md)

Updates the image URL and, optionally, the coordinates. To avoid having the image flash after changing,
set the `raster-fade-duration` paint property on the raster layer to 0.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `Object` | Options object. |
| `options.coordinates?` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |
| `options.url` | `string` | Required image URL. |

#### Returns

[`ImageSource`](maplibregl.ImageSource.md)

this

#### Defined in

[src/source/image_source.ts:150](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L150)
