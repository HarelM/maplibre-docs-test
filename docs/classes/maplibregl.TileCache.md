[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TileCache

# Class: TileCache

[maplibregl](../modules/maplibregl.md).TileCache

A [least-recently-used cache](http://en.wikipedia.org/wiki/Cache_algorithms)
with hash lookup made possible by keeping a list of keys in parallel to
an array of dictionary of values

## Table of contents

### Constructors

- [constructor](maplibregl.TileCache.md#constructor)

### Methods

- [add](maplibregl.TileCache.md#add)
- [filter](maplibregl.TileCache.md#filter)
- [get](maplibregl.TileCache.md#get)
- [getAndRemove](maplibregl.TileCache.md#getandremove)
- [has](maplibregl.TileCache.md#has)
- [remove](maplibregl.TileCache.md#remove)
- [reset](maplibregl.TileCache.md#reset)
- [setMaxSize](maplibregl.TileCache.md#setmaxsize)

## Constructors

### constructor

• **new TileCache**(`max`, `onRemove`)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `max` | `number` | number of permitted values |
| `onRemove` | (`element`: [`Tile`](maplibregl.Tile.md)) => `void` | callback called with items when they expire |

#### Defined in

[src/source/tile_cache.ts:25](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L25)

## Methods

### add

▸ `Private` **add**(`tileID`, `data`, `expiryTimeout`): [`TileCache`](maplibregl.TileCache.md)

Add a key, value combination to the cache, trimming its size if this pushes
it over max length.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | lookup key for the item |
| `data` | [`Tile`](maplibregl.Tile.md) | any value |
| `expiryTimeout` | `number` \| `void` | - |

#### Returns

[`TileCache`](maplibregl.TileCache.md)

this cache

#### Defined in

[src/source/tile_cache.ts:61](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L61)

___

### filter

▸ **filter**(`filterFn`): `void`

Remove entries that do not pass a filter function. Used for removing
stale tiles from the cache.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `filterFn` | (`tile`: [`Tile`](maplibregl.Tile.md)) => `boolean` | Determines whether the tile is filtered. If the supplied function returns false, the tile will be filtered out. |

#### Returns

`void`

#### Defined in

[src/source/tile_cache.ts:203](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L203)

___

### get

▸ `Private` **get**(`tileID`): [`Tile`](maplibregl.Tile.md)

Get the value attached to a specific key without removing data
from the cache. If the key is not found, returns `null`

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the key to look up |

#### Returns

[`Tile`](maplibregl.Tile.md)

the data, or null if it isn't found

#### Defined in

[src/source/tile_cache.ts:144](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L144)

___

### getAndRemove

▸ `Private` **getAndRemove**(`tileID`): [`Tile`](maplibregl.Tile.md)

Get the value attached to a specific key and remove data from cache.
If the key is not found, returns `null`

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the key to look up |

#### Returns

[`Tile`](maplibregl.Tile.md)

the data, or null if it isn't found

#### Defined in

[src/source/tile_cache.ts:108](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L108)

___

### has

▸ `Private` **has**(`tileID`): `boolean`

Determine whether the value attached to `key` is present

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the key to be looked-up |

#### Returns

`boolean`

whether the cache has this value

#### Defined in

[src/source/tile_cache.ts:96](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L96)

___

### remove

▸ `Private` **remove**(`tileID`, `value?`): [`TileCache`](maplibregl.TileCache.md)

Remove a key/value combination from the cache.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the key for the pair to delete |
| `value?` | `Object` | If a value is provided, remove that exact version of the value. |
| `value.timeout` | `Timeout` | - |
| `value.value` | [`Tile`](maplibregl.Tile.md) | - |

#### Returns

[`TileCache`](maplibregl.TileCache.md)

this cache

#### Defined in

[src/source/tile_cache.ts:159](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L159)

___

### reset

▸ `Private` **reset**(): [`TileCache`](maplibregl.TileCache.md)

Clear the cache

#### Returns

[`TileCache`](maplibregl.TileCache.md)

this cache

#### Defined in

[src/source/tile_cache.ts:37](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L37)

___

### setMaxSize

▸ `Private` **setMaxSize**(`max`): [`TileCache`](maplibregl.TileCache.md)

Change the max size of the cache.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `max` | `number` | the max size of the cache |

#### Returns

[`TileCache`](maplibregl.TileCache.md)

this cache

#### Defined in

[src/source/tile_cache.ts:186](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile_cache.ts#L186)
