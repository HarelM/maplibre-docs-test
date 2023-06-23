[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / VideoSource

# Class: VideoSource

[maplibregl](../modules/maplibregl.md).VideoSource

A data source containing video.
(See the [Style Specification](https://maplibre.org/maplibre-style-spec/#sources-video) for detailed documentation of options.)

**`Example`**

```ts
// add to map
map.addSource('some id', {
   type: 'video',
   url: [
       'https://www.mapbox.com/blog/assets/baltimore-smoke.mp4',
       'https://www.mapbox.com/blog/assets/baltimore-smoke.webm'
   ],
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

**`See`**

[Add a video](https://maplibre.org/maplibre-gl-js-docs/example/video-on-a-map/)

## Hierarchy

- [`ImageSource`](maplibregl.ImageSource.md)

  ↳ **`VideoSource`**

## Table of contents

### Constructors

- [constructor](maplibregl.VideoSource.md#constructor)

### Methods

- [getVideo](maplibregl.VideoSource.md#getvideo)
- [listens](maplibregl.VideoSource.md#listens)
- [off](maplibregl.VideoSource.md#off)
- [on](maplibregl.VideoSource.md#on)
- [once](maplibregl.VideoSource.md#once)
- [pause](maplibregl.VideoSource.md#pause)
- [play](maplibregl.VideoSource.md#play)
- [prepare](maplibregl.VideoSource.md#prepare)
- [seek](maplibregl.VideoSource.md#seek)
- [setCoordinates](maplibregl.VideoSource.md#setcoordinates)
- [setEventedParent](maplibregl.VideoSource.md#seteventedparent)
- [updateImage](maplibregl.VideoSource.md#updateimage)

## Constructors

### constructor

• `Private` **new VideoSource**(`id`, `options`, `dispatcher`, `eventedParent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |
| `options` | `VideoSourceSpecification` |
| `dispatcher` | [`Dispatcher`](maplibregl.Dispatcher.md) |
| `eventedParent` | [`Evented`](maplibregl.Evented.md) |

#### Overrides

[ImageSource](maplibregl.ImageSource.md).[constructor](maplibregl.ImageSource.md#constructor)

#### Defined in

[src/source/video_source.ts:57](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L57)

## Methods

### getVideo

▸ **getVideo**(): `HTMLVideoElement`

Returns the HTML `video` element.

#### Returns

`HTMLVideoElement`

The HTML `video` element.

#### Defined in

[src/source/video_source.ts:132](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L132)

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

### off

▸ **off**(`type`, `listener`): [`VideoSource`](maplibregl.VideoSource.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`VideoSource`](maplibregl.VideoSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[off](maplibregl.ImageSource.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`VideoSource`](maplibregl.VideoSource.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`VideoSource`](maplibregl.VideoSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[on](maplibregl.ImageSource.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`VideoSource`](maplibregl.VideoSource.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`VideoSource`](maplibregl.VideoSource.md)

`this` or a promise if a listener is not provided

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[once](maplibregl.ImageSource.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### pause

▸ **pause**(): `void`

Pauses the video.

#### Returns

`void`

#### Defined in

[src/source/video_source.ts:99](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L99)

___

### play

▸ **play**(): `void`

Plays the video.

#### Returns

`void`

#### Defined in

[src/source/video_source.ts:108](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L108)

___

### prepare

▸ **prepare**(): `void`

Sets the video's coordinates and re-renders the map.

**`Method`**

setCoordinates

**`Instance`**

**`Memberof`**

VideoSource

#### Returns

`void`

this

#### Overrides

ImageSource.prepare

#### Defined in

[src/source/video_source.ts:156](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L156)

___

### seek

▸ `Private` **seek**(`seconds`): `void`

Sets playback to a timestamp, in seconds.

#### Parameters

| Name | Type |
| :------ | :------ |
| `seconds` | `number` |

#### Returns

`void`

#### Defined in

[src/source/video_source.ts:118](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/video_source.ts#L118)

___

### setCoordinates

▸ **setCoordinates**(`coordinates`): [`VideoSource`](maplibregl.VideoSource.md)

Sets the image's coordinates and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `coordinates` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |

#### Returns

[`VideoSource`](maplibregl.VideoSource.md)

this

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[setCoordinates](maplibregl.ImageSource.md#setcoordinates)

#### Defined in

[src/source/image_source.ts:196](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L196)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`VideoSource`](maplibregl.VideoSource.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`VideoSource`](maplibregl.VideoSource.md)

`this`

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[setEventedParent](maplibregl.ImageSource.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### updateImage

▸ **updateImage**(`options`): [`VideoSource`](maplibregl.VideoSource.md)

Updates the image URL and, optionally, the coordinates. To avoid having the image flash after changing,
set the `raster-fade-duration` paint property on the raster layer to 0.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `Object` | Options object. |
| `options.coordinates?` | `Coordinates` | Four geographical coordinates, represented as arrays of longitude and latitude numbers, which define the corners of the image. The coordinates start at the top left corner of the image and proceed in clockwise order. They do not have to represent a rectangle. |
| `options.url` | `string` | Required image URL. |

#### Returns

[`VideoSource`](maplibregl.VideoSource.md)

this

#### Inherited from

[ImageSource](maplibregl.ImageSource.md).[updateImage](maplibregl.ImageSource.md#updateimage)

#### Defined in

[src/source/image_source.ts:150](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/image_source.ts#L150)
