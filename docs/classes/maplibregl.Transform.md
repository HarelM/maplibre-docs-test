[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Transform

# Class: Transform

[maplibregl](../modules/maplibregl.md).Transform

A single transform, generally used for a single tile to be
scaled, rotated, and zoomed.

## Table of contents

### Accessors

- [centerPoint](maplibregl.Transform.md#centerpoint)

### Methods

- [calculatePosMatrix](maplibregl.Transform.md#calculateposmatrix)
- [coordinateLocation](maplibregl.Transform.md#coordinatelocation)
- [coordinatePoint](maplibregl.Transform.md#coordinatepoint)
- [coveringTiles](maplibregl.Transform.md#coveringtiles)
- [coveringZoomLevel](maplibregl.Transform.md#coveringzoomlevel)
- [getBounds](maplibregl.Transform.md#getbounds)
- [getCameraPosition](maplibregl.Transform.md#getcameraposition)
- [getElevation](maplibregl.Transform.md#getelevation)
- [getHorizon](maplibregl.Transform.md#gethorizon)
- [getMaxBounds](maplibregl.Transform.md#getmaxbounds)
- [getVisibleUnwrappedCoordinates](maplibregl.Transform.md#getvisibleunwrappedcoordinates)
- [interpolatePadding](maplibregl.Transform.md#interpolatepadding)
- [isPaddingEqual](maplibregl.Transform.md#ispaddingequal)
- [locationCoordinate](maplibregl.Transform.md#locationcoordinate)
- [locationPoint](maplibregl.Transform.md#locationpoint)
- [pointCoordinate](maplibregl.Transform.md#pointcoordinate)
- [pointLocation](maplibregl.Transform.md#pointlocation)
- [recalculateZoom](maplibregl.Transform.md#recalculatezoom)
- [setMaxBounds](maplibregl.Transform.md#setmaxbounds)
- [updateElevation](maplibregl.Transform.md#updateelevation)

## Accessors

### centerPoint

• `get` **centerPoint**(): `Point`

The center of the screen in pixels with the top-left corner being (0,0)
and +y axis pointing downwards. This accounts for padding.

**`Memberof`**

Transform

#### Returns

`Point`

#### Defined in

[src/geo/transform.ts:246](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L246)

## Methods

### calculatePosMatrix

▸ `Private` **calculatePosMatrix**(`unwrappedTileID`, `aligned?`): `mat4`

Calculate the posMatrix that, given a tile coordinate, would be used to display the tile on a map.

#### Parameters

| Name | Type | Default value |
| :------ | :------ | :------ |
| `unwrappedTileID` | `UnwrappedTileID` | `undefined` |
| `aligned` | `boolean` | `false` |

#### Returns

`mat4`

#### Defined in

[src/geo/transform.ts:722](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L722)

___

### coordinateLocation

▸ `Private` **coordinateLocation**(`coord`): [`LngLat`](maplibregl.LngLat.md)

Given a Coordinate, return its geographical position.

#### Parameters

| Name | Type |
| :------ | :------ |
| `coord` | [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md) |

#### Returns

[`LngLat`](maplibregl.LngLat.md)

lnglat

#### Defined in

[src/geo/transform.ts:605](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L605)

___

### coordinatePoint

▸ `Private` **coordinatePoint**(`coord`, `elevation?`, `pixelMatrix?`): `Point`

Given a coordinate, return the screen point that corresponds to it

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `coord` | [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md) | `undefined` |  |
| `elevation` | `number` | `0` | default = 0 |
| `pixelMatrix` | `mat4` | `undefined` | - |

#### Returns

`Point`

screen point

#### Defined in

[src/geo/transform.ts:661](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L661)

___

### coveringTiles

▸ `Private` **coveringTiles**(`options`): `OverscaledTileID`[]

Return all coordinates that could cover this transform for a covering
zoom level.

#### Parameters

| Name | Type |
| :------ | :------ |
| `options` | `Object` |
| `options.maxzoom?` | `number` |
| `options.minzoom?` | `number` |
| `options.renderWorldCopies?` | `boolean` |
| `options.reparseOverscaled?` | `boolean` |
| `options.roundZoom?` | `boolean` |
| `options.terrain?` | [`Terrain`](maplibregl.Terrain.md) |
| `options.tileSize` | `number` |

#### Returns

`OverscaledTileID`[]

OverscaledTileIDs

#### Defined in

[src/geo/transform.ts:336](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L336)

___

### coveringZoomLevel

▸ **coveringZoomLevel**(`options`): `number`

Return a zoom level that will cover all tiles the transform

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `Object` | options |
| `options.roundZoom?` | `boolean` | Target zoom level. If true, the value will be rounded to the closest integer. Otherwise the value will be floored. |
| `options.tileSize` | `number` | Tile size, expressed in screen pixels. |

#### Returns

`number`

zoom level An integer zoom level at which all tiles will be visible.

#### Defined in

[src/geo/transform.ts:283](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L283)

___

### getBounds

▸ **getBounds**(): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns the map's geographical bounds. When the bearing or pitch is non-zero, the visible region is not
an axis-aligned rectangle, and the result is the smallest bounds that encompasses the visible region.

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns a [LngLatBounds](maplibregl.LngLatBounds.md) object describing the map's geographical bounds.

#### Defined in

[src/geo/transform.ts:672](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L672)

___

### getCameraPosition

▸ **getCameraPosition**(): `Object`

get the camera position in LngLat and altitudes in meter

#### Returns

`Object`

An object with lngLat & altitude.

| Name | Type |
| :------ | :------ |
| `altitude` | `number` |
| `lngLat` | [`LngLat`](maplibregl.LngLat.md) |

#### Defined in

[src/geo/transform.ts:513](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L513)

___

### getElevation

▸ **getElevation**(`lnglat`, `terrain`): `number`

get the elevation from terrain for the current zoomlevel.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLat`](maplibregl.LngLat.md) | the location |
| `terrain` | [`Terrain`](maplibregl.Terrain.md) | the terrain |

#### Returns

`number`

elevation in meters

#### Defined in

[src/geo/transform.ts:500](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L500)

___

### getHorizon

▸ **getHorizon**(): `number`

Calculate pixel height of the visible horizon in relation to map-center (e.g. height/2),
multiplied by a static factor to simulate the earth-radius.
The calculated value is the horizontal line from the camera-height to sea-level.

#### Returns

`number`

Horizon above center in pixels.

#### Defined in

[src/geo/transform.ts:698](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L698)

___

### getMaxBounds

▸ **getMaxBounds**(): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns the maximum geographical bounds the map is constrained to, or `null` if none set.

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

[LngLatBounds](maplibregl.LngLatBounds.md)

#### Defined in

[src/geo/transform.ts:685](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L685)

___

### getVisibleUnwrappedCoordinates

▸ `Private` **getVisibleUnwrappedCoordinates**(`tileID`): `UnwrappedTileID`[]

Return any "wrapped" copies of a given tile coordinate that are visible
in the current view.

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileID` | `CanonicalTileID` |

#### Returns

`UnwrappedTileID`[]

#### Defined in

[src/geo/transform.ts:300](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L300)

___

### interpolatePadding

▸ **interpolatePadding**(`start`, `target`, `t`): `void`

Helper method to update edge-insets in place

**`Memberof`**

Transform

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `start` | [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | the starting padding |
| `target` | [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | the target padding |
| `t` | `number` | the step/weight |

#### Returns

`void`

#### Defined in

[src/geo/transform.ts:269](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L269)

___

### isPaddingEqual

▸ **isPaddingEqual**(`padding`): `boolean`

Returns if the padding params match

**`Memberof`**

Transform

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `padding` | [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | the padding to check against |

#### Returns

`boolean`

true if they are equal, false otherwise

#### Defined in

[src/geo/transform.ts:257](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L257)

___

### locationCoordinate

▸ `Private` **locationCoordinate**(`lnglat`): [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

Given a geographical lnglat, return an unrounded
coordinate that represents it at this transform's zoom level.

#### Parameters

| Name | Type |
| :------ | :------ |
| `lnglat` | [`LngLat`](maplibregl.LngLat.md) |

#### Returns

[`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

#### Defined in

[src/geo/transform.ts:595](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L595)

___

### locationPoint

▸ `Private` **locationPoint**(`lnglat`, `terrain?`): `Point`

Given a location, return the screen point that corresponds to it

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLat`](maplibregl.LngLat.md) | location |
| `terrain?` | [`Terrain`](maplibregl.Terrain.md) | optional terrain |

#### Returns

`Point`

screen point

#### Defined in

[src/geo/transform.ts:571](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L571)

___

### pointCoordinate

▸ `Private` **pointCoordinate**(`p`, `terrain?`): [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

Given a Point, return its mercator coordinate.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `p` | `Point` | the point |
| `terrain?` | [`Terrain`](maplibregl.Terrain.md) | optional terrain |

#### Returns

[`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

lnglat

#### Defined in

[src/geo/transform.ts:616](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L616)

___

### pointLocation

▸ `Private` **pointLocation**(`p`, `terrain?`): [`LngLat`](maplibregl.LngLat.md)

Given a point on screen, return its lnglat

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `p` | `Point` | screen point |
| `terrain?` | [`Terrain`](maplibregl.Terrain.md) | optional terrain |

#### Returns

[`LngLat`](maplibregl.LngLat.md)

lnglat location

#### Defined in

[src/geo/transform.ts:584](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L584)

___

### recalculateZoom

▸ **recalculateZoom**(`terrain`): `void`

This method works in combination with freezeElevation activated.
freezeElevtion is enabled during map-panning because during this the camera should sit in constant height.
After panning finished, call this method to recalculate the zoomlevel for the current camera-height in current terrain.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `terrain` | [`Terrain`](maplibregl.Terrain.md) | the terrain |

#### Returns

`void`

#### Defined in

[src/geo/transform.ts:528](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L528)

___

### setMaxBounds

▸ **setMaxBounds**(`bounds?`): `void`

Sets or clears the map's geographical constraints.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bounds?` | [`LngLatBounds`](maplibregl.LngLatBounds.md) | A [LngLatBounds](maplibregl.LngLatBounds.md) object describing the new geographic boundaries of the map. |

#### Returns

`void`

#### Defined in

[src/geo/transform.ts:706](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L706)

___

### updateElevation

▸ **updateElevation**(`terrain?`): `void`

Updates the center-elevation value unless freezeElevation is activated.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `terrain?` | [`Terrain`](maplibregl.Terrain.md) | the terrain |

#### Returns

`void`

#### Defined in

[src/geo/transform.ts:489](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/transform.ts#L489)
