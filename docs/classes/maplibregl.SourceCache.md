[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / SourceCache

# Class: SourceCache

[maplibregl](../modules/maplibregl.md).SourceCache

`SourceCache` is responsible for

 - creating an instance of `Source`
 - forwarding events from `Source`
 - caching tiles loaded from an instance of `Source`
 - loading the tiles needed to render a given viewport
 - unloading the cached tiles not needed to render a given viewport

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`SourceCache`**

## Table of contents

### Methods

- [\_addTile](maplibregl.SourceCache.md#_addtile)
- [\_backfillDEM](maplibregl.SourceCache.md#_backfilldem)
- [\_removeTile](maplibregl.SourceCache.md#_removetile)
- [\_retainLoadedChildren](maplibregl.SourceCache.md#_retainloadedchildren)
- [clearTiles](maplibregl.SourceCache.md#cleartiles)
- [findLoadedParent](maplibregl.SourceCache.md#findloadedparent)
- [getFeatureState](maplibregl.SourceCache.md#getfeaturestate)
- [getIds](maplibregl.SourceCache.md#getids)
- [getTile](maplibregl.SourceCache.md#gettile)
- [getTileByID](maplibregl.SourceCache.md#gettilebyid)
- [listens](maplibregl.SourceCache.md#listens)
- [loaded](maplibregl.SourceCache.md#loaded)
- [off](maplibregl.SourceCache.md#off)
- [on](maplibregl.SourceCache.md#on)
- [once](maplibregl.SourceCache.md#once)
- [reloadTilesForDependencies](maplibregl.SourceCache.md#reloadtilesfordependencies)
- [removeFeatureState](maplibregl.SourceCache.md#removefeaturestate)
- [setDependencies](maplibregl.SourceCache.md#setdependencies)
- [setEventedParent](maplibregl.SourceCache.md#seteventedparent)
- [setFeatureState](maplibregl.SourceCache.md#setfeaturestate)
- [tilesIn](maplibregl.SourceCache.md#tilesin)
- [update](maplibregl.SourceCache.md#update)
- [updateCacheSize](maplibregl.SourceCache.md#updatecachesize)

## Methods

### \_addTile

▸ `Private` **_addTile**(`tileID`): [`Tile`](maplibregl.Tile.md)

Add a tile, given its coordinate, to the pyramid.

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileID` | `OverscaledTileID` |

#### Returns

[`Tile`](maplibregl.Tile.md)

#### Defined in

[src/source/source_cache.ts:806](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L806)

___

### \_backfillDEM

▸ `Private` **_backfillDEM**(`tile`): `void`

For raster terrain source, backfill DEM to eliminate visible tile boundaries

#### Parameters

| Name | Type |
| :------ | :------ |
| `tile` | [`Tile`](maplibregl.Tile.md) |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:303](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L303)

___

### \_removeTile

▸ `Private` **_removeTile**(`id`): `void`

Remove a tile, given its id, from the pyramid

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:859](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L859)

___

### \_retainLoadedChildren

▸ `Private` **_retainLoadedChildren**(`idealTiles`, `zoom`, `maxCoveringZoom`, `retain`): `void`

For a given set of tiles, retain children that are loaded and have a zoom
between `zoom` (exclusive) and `maxCoveringZoom` (inclusive)

#### Parameters

| Name | Type |
| :------ | :------ |
| `idealTiles` | `Object` |
| `zoom` | `number` |
| `maxCoveringZoom` | `number` |
| `retain` | `Object` |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:361](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L361)

___

### clearTiles

▸ **clearTiles**(): `void`

Remove all tiles from this pyramid

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:886](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L886)

___

### findLoadedParent

▸ `Private` **findLoadedParent**(`tileID`, `minCoveringZoom`): [`Tile`](maplibregl.Tile.md)

Find a loaded parent of the given tile (up to minCoveringZoom)

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileID` | `OverscaledTileID` |
| `minCoveringZoom` | `number` |

#### Returns

[`Tile`](maplibregl.Tile.md)

#### Defined in

[src/source/source_cache.ts:411](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L411)

___

### getFeatureState

▸ `Private` **getFeatureState**(`sourceLayer`, `featureId`): `any`

Get the entire state object for a feature

#### Parameters

| Name | Type |
| :------ | :------ |
| `sourceLayer` | `string` |
| `featureId` | `string` \| `number` |

#### Returns

`any`

#### Defined in

[src/source/source_cache.ts:1013](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L1013)

___

### getIds

▸ `Private` **getIds**(): `string`[]

Return all tile ids ordered with z-order, and cast to numbers

#### Returns

`string`[]

#### Defined in

[src/source/source_cache.ts:213](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L213)

___

### getTile

▸ `Private` **getTile**(`tileID`): [`Tile`](maplibregl.Tile.md)

Get a specific tile by TileID

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileID` | `OverscaledTileID` |

#### Returns

[`Tile`](maplibregl.Tile.md)

#### Defined in

[src/source/source_cache.ts:344](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L344)

___

### getTileByID

▸ `Private` **getTileByID**(`id`): [`Tile`](maplibregl.Tile.md)

Get a specific tile by id

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |

#### Returns

[`Tile`](maplibregl.Tile.md)

#### Defined in

[src/source/source_cache.ts:352](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L352)

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

### loaded

▸ `Private` **loaded**(): `boolean`

Return true if no tile data is pending, tiles will not change unless
an additional API call is received.

#### Returns

`boolean`

#### Defined in

[src/source/source_cache.ts:143](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L143)

___

### off

▸ **off**(`type`, `listener`): [`SourceCache`](maplibregl.SourceCache.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`SourceCache`](maplibregl.SourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`SourceCache`](maplibregl.SourceCache.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`SourceCache`](maplibregl.SourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`SourceCache`](maplibregl.SourceCache.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`SourceCache`](maplibregl.SourceCache.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### reloadTilesForDependencies

▸ `Private` **reloadTilesForDependencies**(`namespaces`, `keys`): `void`

Reloads all tiles that depend on the given keys.

#### Parameters

| Name | Type |
| :------ | :------ |
| `namespaces` | `string`[] |
| `keys` | `string`[] |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:1034](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L1034)

___

### removeFeatureState

▸ `Private` **removeFeatureState**(`sourceLayer?`, `featureId?`, `key?`): `void`

Resets the value of a particular state key for a feature

#### Parameters

| Name | Type |
| :------ | :------ |
| `sourceLayer?` | `string` |
| `featureId?` | `string` \| `number` |
| `key?` | `string` |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:1004](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L1004)

___

### setDependencies

▸ `Private` **setDependencies**(`tileKey`, `namespace`, `dependencies`): `void`

Sets the set of keys that the tile depends on. This allows tiles to
be reloaded when their dependencies change.

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileKey` | `string` |
| `namespace` | `string` |
| `dependencies` | `string`[] |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:1023](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L1023)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`SourceCache`](maplibregl.SourceCache.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`SourceCache`](maplibregl.SourceCache.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setFeatureState

▸ `Private` **setFeatureState**(`sourceLayer`, `featureId`, `state`): `void`

Set the value of a particular state for a feature

#### Parameters

| Name | Type |
| :------ | :------ |
| `sourceLayer` | `string` |
| `featureId` | `string` \| `number` |
| `state` | `any` |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:995](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L995)

___

### tilesIn

▸ `Private` **tilesIn**(`pointQueryGeometry`, `maxPitchScaleFactor`, `has3DLayer`): `any`[]

Search through our current tiles and attempt to find the tiles that
cover the given bounds.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `pointQueryGeometry` | `Point`[] | coordinates of the corners of bounding rectangle |
| `maxPitchScaleFactor` | `number` | - |
| `has3DLayer` | `boolean` | - |

#### Returns

`any`[]

result items have {tile, minX, maxX, minY, maxY}, where min/max bounding values are the given bounds transformed in into the coordinate space of this tile.

#### Defined in

[src/source/source_cache.ts:903](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L903)

___

### update

▸ `Private` **update**(`transform`, `terrain?`): `void`

Removes tiles that are outside the viewport and adds new tiles that
are inside the viewport.

#### Parameters

| Name | Type |
| :------ | :------ |
| `transform` | [`Transform`](maplibregl.Transform.md) |
| `terrain?` | [`Terrain`](maplibregl.Terrain.md) |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:509](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L509)

___

### updateCacheSize

▸ `Private` **updateCacheSize**(`transform`): `void`

Resizes the tile cache based on the current viewport's size
or the maxTileCacheSize option passed during map creation

Larger viewports use more tiles and need larger caches. Larger viewports
are more likely to be found on devices with more memory and on pages where
the map is more important.

#### Parameters

| Name | Type |
| :------ | :------ |
| `transform` | [`Transform`](maplibregl.Transform.md) |

#### Returns

`void`

#### Defined in

[src/source/source_cache.ts:448](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source_cache.ts#L448)
