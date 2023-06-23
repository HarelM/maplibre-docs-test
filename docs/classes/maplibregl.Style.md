[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Style

# Class: Style

[maplibregl](../modules/maplibregl.md).Style

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`Style`**

## Table of contents

### Methods

- [\_serializeByIds](maplibregl.Style.md#_serializebyids)
- [\_serializedAllLayers](maplibregl.Style.md#_serializedalllayers)
- [addLayer](maplibregl.Style.md#addlayer)
- [addSprite](maplibregl.Style.md#addsprite)
- [getFilter](maplibregl.Style.md#getfilter)
- [getLayer](maplibregl.Style.md#getlayer)
- [getLayoutProperty](maplibregl.Style.md#getlayoutproperty)
- [getSource](maplibregl.Style.md#getsource)
- [getSprite](maplibregl.Style.md#getsprite)
- [hasLayer](maplibregl.Style.md#haslayer)
- [listens](maplibregl.Style.md#listens)
- [moveLayer](maplibregl.Style.md#movelayer)
- [off](maplibregl.Style.md#off)
- [on](maplibregl.Style.md#on)
- [once](maplibregl.Style.md#once)
- [removeLayer](maplibregl.Style.md#removelayer)
- [removeSource](maplibregl.Style.md#removesource)
- [removeSprite](maplibregl.Style.md#removesprite)
- [setEventedParent](maplibregl.Style.md#seteventedparent)
- [setGeoJSONSourceData](maplibregl.Style.md#setgeojsonsourcedata)
- [setSprite](maplibregl.Style.md#setsprite)
- [setState](maplibregl.Style.md#setstate)
- [update](maplibregl.Style.md#update)

## Methods

### \_serializeByIds

▸ `Private` **_serializeByIds**(`ids?`): `LayerSpecification`[]

take an array of string IDs, and based on this._layers, generate an array of LayerSpecification

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `ids?` | `string`[] | an array of string IDs, for which serialized layers will be generated. If omitted, all serialized layers will be returned |

#### Returns

`LayerSpecification`[]

generated result

#### Defined in

[src/style/style.ts:456](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L456)

___

### \_serializedAllLayers

▸ `Private` **_serializedAllLayers**(): `Object`

Lazy initialization of this._serializedLayers dictionary and return it

#### Returns

`Object`

this._serializedLayers dictionary

#### Defined in

[src/style/style.ts:478](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L478)

___

### addLayer

▸ **addLayer**(`layerObject`, `before?`, `options?`): `void`

Add a layer to the map style. The layer will be inserted before the layer with
ID `before`, or appended if `before` is omitted.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerObject` | `LayerSpecification` \| [`CustomLayerInterface`](../interfaces/maplibregl.CustomLayerInterface.md) | The style layer to add. |
| `before?` | `string` | ID of an existing layer to insert before |
| `options` | `StyleSetterOptions` | Style setter options. |

#### Returns

`void`

The [Map](maplibregl.Map.md) object.

#### Defined in

[src/style/style.ts:810](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L810)

___

### addSprite

▸ **addSprite**(`id`, `url`, `options?`, `completion?`): `void`

Add a sprite.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the desired sprite |
| `url` | `string` | url to load the desired sprite from |
| `options?` | `StyleSetterOptions` | style setter options |
| `completion?` | (`err`: `Error`) => `void` | completion handler |

#### Returns

`void`

#### Defined in

[src/style/style.ts:1604](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1604)

___

### getFilter

▸ **getFilter**(`layer`): `void` \| `FilterSpecification`

Get a layer's filter object

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layer` | `string` | the layer to inspect |

#### Returns

`void` \| `FilterSpecification`

the layer's filter, if any

#### Defined in

[src/style/style.ts:1022](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1022)

___

### getLayer

▸ **getLayer**(`id`): `StyleLayer`

Return the style layer object with the given `id`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the desired layer |

#### Returns

`StyleLayer`

a layer, if one with the given `id` exists

#### Defined in

[src/style/style.ts:956](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L956)

___

### getLayoutProperty

▸ **getLayoutProperty**(`layerId`, `name`): `any`

Get a layout property's value from a given layer

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | the layer to inspect |
| `name` | `string` | the name of the layout property |

#### Returns

`any`

the property value

#### Defined in

[src/style/style.ts:1047](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1047)

___

### getSource

▸ **getSource**(`id`): [`Source`](../interfaces/maplibregl.Source.md)

Get a source by id.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the desired source |

#### Returns

[`Source`](../interfaces/maplibregl.Source.md)

source

#### Defined in

[src/style/style.ts:798](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L798)

___

### getSprite

▸ **getSprite**(): { `id`: `string` ; `url`: `string`  }[]

Get the current sprite value.

#### Returns

{ `id`: `string` ; `url`: `string`  }[]

empty array when no sprite is set; id-url pairs otherwise

#### Defined in

[src/style/style.ts:1657](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1657)

___

### hasLayer

▸ **hasLayer**(`id`): `boolean`

checks if a specific layer is present within the style.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the desired layer |

#### Returns

`boolean`

a boolean specifying if the given layer is present

#### Defined in

[src/style/style.ts:966](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L966)

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

[Evented](maplibregl.Evented.md).[listens](maplibregl.Evented.md#listens)

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### moveLayer

▸ **moveLayer**(`id`, `before?`): `void`

Moves a layer to a different z-position. The layer will be inserted before the layer with
ID `before`, or appended if `before` is omitted.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | ID of the layer to move |
| `before?` | `string` | ID of an existing layer to insert before |

#### Returns

`void`

#### Defined in

[src/style/style.ts:885](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L885)

___

### off

▸ **off**(`type`, `listener`): [`Style`](maplibregl.Style.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`Style`](maplibregl.Style.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`Style`](maplibregl.Style.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`Style`](maplibregl.Style.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`Style`](maplibregl.Style.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`Style`](maplibregl.Style.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### removeLayer

▸ **removeLayer**(`id`): `void`

Remove the layer with the given id from the style.

If no such layer exists, an `error` event is fired.

**`Fires`**

error

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the layer to remove |

#### Returns

`void`

#### Defined in

[src/style/style.ts:920](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L920)

___

### removeSource

▸ **removeSource**(`id`): [`Style`](maplibregl.Style.md)

Remove a source from this stylesheet, given its id.

**`Throws`**

if no source is found with the given ID

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the source to remove |

#### Returns

[`Style`](maplibregl.Style.md)

The [Map](maplibregl.Map.md) object.

#### Defined in

[src/style/style.ts:756](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L756)

___

### removeSprite

▸ **removeSprite**(`id`): `void`

Remove a sprite by its id. When the last sprite is removed, the whole `this.stylesheet.sprite` object becomes
`undefined`. This falsy `undefined` value later prevents attempts to load the sprite when it's absent.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | the id of the sprite to remove |

#### Returns

`void`

#### Defined in

[src/style/style.ts:1625](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1625)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`Style`](maplibregl.Style.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`Style`](maplibregl.Style.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setGeoJSONSourceData

▸ **setGeoJSONSourceData**(`id`, `data`): `void`

Set the data of a GeoJSON source, given its id.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the source |
| `data` | `string` \| `GeoJSON` | GeoJSON source |

#### Returns

`void`

#### Defined in

[src/style/style.ts:782](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L782)

___

### setSprite

▸ **setSprite**(`sprite`, `options?`, `completion?`): `void`

Set a new value for the style's sprite.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `sprite` | `SpriteSpecification` | new sprite value |
| `options?` | `StyleSetterOptions` | style setter options |
| `completion?` | (`err`: `Error`) => `void` | completion handler |

#### Returns

`void`

#### Defined in

[src/style/style.ts:1668](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L1668)

___

### setState

▸ `Private` **setState**(`nextState`, `options?`): `boolean`

Update this style's state to match the given style JSON, performing only
the necessary mutations.

May throw an Error ('Unimplemented: METHOD') if the mapbox-gl-style-spec
diff algorithm produces an operation that is not supported.

#### Parameters

| Name | Type |
| :------ | :------ |
| `nextState` | `StyleSpecification` |
| `options` | `StyleSwapOptions` |

#### Returns

`boolean`

true if any changes were made; false otherwise

#### Defined in

[src/style/style.ts:648](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L648)

___

### update

▸ `Private` **update**(`parameters`): `void`

Apply queued style updates in a batch and recalculate zoom-dependent paint properties.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parameters` | `EvaluationParameters` |

#### Returns

`void`

#### Defined in

[src/style/style.ts:526](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style.ts#L526)
