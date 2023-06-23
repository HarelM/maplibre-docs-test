[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TerrainSourceCache

# Class: TerrainSourceCache

[maplibregl](../modules/maplibregl.md).TerrainSourceCache

This class is a helper for the Terrain-class, it:
  - loads raster-dem tiles
  - manages all renderToTexture tiles.
  - caches previous rendered tiles.
  - finds all necessary renderToTexture tiles for a OverscaledTileID area
  - finds the corresponding raster-dem tile for OverscaledTileID

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`TerrainSourceCache`**

## Table of contents

### Methods

- [freeRtt](maplibregl.TerrainSourceCache.md#freertt)
- [getRenderableTiles](maplibregl.TerrainSourceCache.md#getrenderabletiles)
- [getSourceTile](maplibregl.TerrainSourceCache.md#getsourcetile)
- [getTerrainCoords](maplibregl.TerrainSourceCache.md#getterraincoords)
- [getTileByID](maplibregl.TerrainSourceCache.md#gettilebyid)
- [listens](maplibregl.TerrainSourceCache.md#listens)
- [off](maplibregl.TerrainSourceCache.md#off)
- [on](maplibregl.TerrainSourceCache.md#on)
- [once](maplibregl.TerrainSourceCache.md#once)
- [setEventedParent](maplibregl.TerrainSourceCache.md#seteventedparent)
- [tilesAfterTime](maplibregl.TerrainSourceCache.md#tilesaftertime)
- [update](maplibregl.TerrainSourceCache.md#update)

## Methods

### freeRtt

▸ **freeRtt**(`tileID?`): `void`

Free render to texture cache

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID?` | `OverscaledTileID` | optional, free only corresponding to tileID. |

#### Returns

`void`

#### Defined in

[src/source/terrain_source_cache.ts:92](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L92)

___

### getRenderableTiles

▸ **getRenderableTiles**(): [`Tile`](maplibregl.Tile.md)[]

get a list of tiles, which are loaded and should be rendered in the current scene

#### Returns

[`Tile`](maplibregl.Tile.md)[]

the renderable tiles

#### Defined in

[src/source/terrain_source_cache.ts:104](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L104)

___

### getSourceTile

▸ **getSourceTile**(`tileID`, `searchForDEM?`): [`Tile`](maplibregl.Tile.md)

find the covering raster-dem tile

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the tile to look for |
| `searchForDEM?` | `boolean` | Optinal parameter to search for (parent) souretiles with loaded dem. |

#### Returns

[`Tile`](maplibregl.Tile.md)

- the tile

#### Defined in

[src/source/terrain_source_cache.ts:163](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L163)

___

### getTerrainCoords

▸ **getTerrainCoords**(`tileID`): `Record`<`string`, `OverscaledTileID`\>

Searches for the corresponding current renderable terrain-tiles

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the tile to look for |

#### Returns

`Record`<`string`, `OverscaledTileID`\>

- the tiles that were found

#### Defined in

[src/source/terrain_source_cache.ts:122](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L122)

___

### getTileByID

▸ **getTileByID**(`id`): [`Tile`](maplibregl.Tile.md)

get terrain tile by the TileID key

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | the tile id |

#### Returns

[`Tile`](maplibregl.Tile.md)

- the tile

#### Defined in

[src/source/terrain_source_cache.ts:113](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L113)

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

### off

▸ **off**(`type`, `listener`): [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`TerrainSourceCache`](maplibregl.TerrainSourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### tilesAfterTime

▸ **tilesAfterTime**(`time?`): [`Tile`](maplibregl.Tile.md)[]

get a list of tiles, loaded after a spezific time. This is used to update depth & coords framebuffers.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `time` | `number` | the time |

#### Returns

[`Tile`](maplibregl.Tile.md)[]

- the relevant tiles

#### Defined in

[src/source/terrain_source_cache.ts:184](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L184)

___

### update

▸ **update**(`transform`, `terrain`): `void`

Load Terrain Tiles, create internal render-to-texture tiles, free GPU memory.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `transform` | [`Transform`](maplibregl.Transform.md) | the operation to do |
| `terrain` | [`Terrain`](maplibregl.Terrain.md) | the terrain |

#### Returns

`void`

#### Defined in

[src/source/terrain_source_cache.ts:61](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/terrain_source_cache.ts#L61)
