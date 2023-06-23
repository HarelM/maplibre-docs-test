[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / VectorTileSource

# Class: VectorTileSource

[maplibregl](../modules/maplibregl.md).VectorTileSource

A source containing vector tiles in [Mapbox Vector Tile format](https://docs.mapbox.com/vector-tiles/reference/).
(See the [Style Specification](https://maplibre.org/maplibre-style-spec/) for detailed documentation of options.)

**`Example`**

```ts
map.addSource('some id', {
    type: 'vector',
    url: 'https://demotiles.maplibre.org/tiles/tiles.json'
});
```

**`Example`**

```ts
map.addSource('some id', {
    type: 'vector',
    tiles: ['https://d25uarhxywzl1j.cloudfront.net/v0.1/{z}/{x}/{y}.mvt'],
    minzoom: 6,
    maxzoom: 14
});
```

**`Example`**

```ts
map.getSource('some id').setUrl("https://demotiles.maplibre.org/tiles/tiles.json");
```

**`Example`**

```ts
map.getSource('some id').setTiles(['https://d25uarhxywzl1j.cloudfront.net/v0.1/{z}/{x}/{y}.mvt']);
```

**`See`**

 - [Add a vector tile source](https://maplibre.org/maplibre-gl-js-docs/example/vector-source/)
 - [Add a third party vector tile source](https://maplibre.org/maplibre-gl-js-docs/example/third-party/)

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`VectorTileSource`**

## Implements

- [`Source`](../interfaces/maplibregl.Source.md)

## Table of contents

### Methods

- [listens](maplibregl.VectorTileSource.md#listens)
- [off](maplibregl.VectorTileSource.md#off)
- [on](maplibregl.VectorTileSource.md#on)
- [once](maplibregl.VectorTileSource.md#once)
- [setEventedParent](maplibregl.VectorTileSource.md#seteventedparent)
- [setTiles](maplibregl.VectorTileSource.md#settiles)
- [setUrl](maplibregl.VectorTileSource.md#seturl)

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

▸ **off**(`type`, `listener`): [`VectorTileSource`](maplibregl.VectorTileSource.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`VectorTileSource`](maplibregl.VectorTileSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`VectorTileSource`](maplibregl.VectorTileSource.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`VectorTileSource`](maplibregl.VectorTileSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`VectorTileSource`](maplibregl.VectorTileSource.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`VectorTileSource`](maplibregl.VectorTileSource.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`VectorTileSource`](maplibregl.VectorTileSource.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`VectorTileSource`](maplibregl.VectorTileSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setTiles

▸ **setTiles**(`tiles`): [`VectorTileSource`](maplibregl.VectorTileSource.md)

Sets the source `tiles` property and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tiles` | `string`[] | An array of one or more tile source URLs, as in the TileJSON spec. |

#### Returns

[`VectorTileSource`](maplibregl.VectorTileSource.md)

this

#### Defined in

[src/source/vector_tile_source.ts:146](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/vector_tile_source.ts#L146)

___

### setUrl

▸ **setUrl**(`url`): [`VectorTileSource`](maplibregl.VectorTileSource.md)

Sets the source `url` property and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `url` | `string` | A URL to a TileJSON resource. Supported protocols are `http:` and `https:`. |

#### Returns

[`VectorTileSource`](maplibregl.VectorTileSource.md)

this

#### Defined in

[src/source/vector_tile_source.ts:160](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/vector_tile_source.ts#L160)
