[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Evented

# Class: Evented

[maplibregl](../modules/maplibregl.md).Evented

Methods mixed in to other classes for event capabilities.

**`Mixin`**

Evented

## Hierarchy

- **`Evented`**

  ↳ [`GeolocateControl`](maplibregl.GeolocateControl.md)

  ↳ [`FullscreenControl`](maplibregl.FullscreenControl.md)

  ↳ [`Popup`](maplibregl.Popup.md)

  ↳ [`Marker`](maplibregl.Marker.md)

  ↳ [`Style`](maplibregl.Style.md)

  ↳ [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

  ↳ [`ImageSource`](maplibregl.ImageSource.md)

  ↳ [`VectorTileSource`](maplibregl.VectorTileSource.md)

  ↳ [`SourceCache`](maplibregl.SourceCache.md)

  ↳ [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

## Table of contents

### Methods

- [listens](maplibregl.Evented.md#listens)
- [off](maplibregl.Evented.md#off)
- [on](maplibregl.Evented.md#on)
- [once](maplibregl.Evented.md#once)
- [setEventedParent](maplibregl.Evented.md#seteventedparent)

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

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### off

▸ **off**(`type`, `listener`): [`Evented`](maplibregl.Evented.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`Evented`](maplibregl.Evented.md)

`this`

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`Evented`](maplibregl.Evented.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`Evented`](maplibregl.Evented.md)

`this`

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`Evented`](maplibregl.Evented.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`Evented`](maplibregl.Evented.md)

`this` or a promise if a listener is not provided

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`Evented`](maplibregl.Evented.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`Evented`](maplibregl.Evented.md)

`this`

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)
