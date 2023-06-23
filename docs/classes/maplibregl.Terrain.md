[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Terrain

# Class: Terrain

[maplibregl](../modules/maplibregl.md).Terrain

This is the main class which handles most of the 3D Terrain logic. It has the following topics:
   1) loads raster-dem tiles via the internal sourceCache this.sourceCache
   2) creates a depth-framebuffer, which is used to calculate the visibility of coordinates
   3) creates a coords-framebuffer, which is used the get to tile-coordinate for a screen-pixel
   4) stores all render-to-texture tiles in the this.sourceCache._tiles
   5) calculates the elevation for a specific tile-coordinate
   6) creates a terrain-mesh

   A note about the GPU resource-usage:
   Framebuffers:
      - one for the depth & coords framebuffer with the size of the map-div.
      - one for rendering a tile to texture with the size of tileSize (= 512x512).
   Textures:
      - one texture for an empty raster-dem tile with size 1x1
      - one texture for an empty depth-buffer, when terrain is disabled with size 1x1
      - one texture for an each loaded raster-dem with size of the source.tileSize
      - one texture for the coords-framebuffer with the size of the map-div.
      - one texture for the depth-framebuffer with the size of the map-div.
      - one texture for the encoded tile-coords with the size 2*tileSize (=1024x1024)
      - finally for each render-to-texture tile (= this._tiles) a set of textures
        for each render stack (The stack-concept is documented in painter.ts).
        Normally there exists 1-3 Textures per tile, depending on the stylesheet.
        Each Textures has the size 2*tileSize (= 1024x1024). Also there exists a
        cache of the last 150 newest rendered tiles.

## Table of contents

### Methods

- [getCoordsTexture](maplibregl.Terrain.md#getcoordstexture)
- [getDEMElevation](maplibregl.Terrain.md#getdemelevation)
- [getElevation](maplibregl.Terrain.md#getelevation)
- [getFramebuffer](maplibregl.Terrain.md#getframebuffer)
- [getMeshFrameDelta](maplibregl.Terrain.md#getmeshframedelta)
- [getMinMaxElevation](maplibregl.Terrain.md#getminmaxelevation)
- [getTerrainData](maplibregl.Terrain.md#getterraindata)
- [getTerrainMesh](maplibregl.Terrain.md#getterrainmesh)
- [pointCoordinate](maplibregl.Terrain.md#pointcoordinate)

## Methods

### getCoordsTexture

▸ **getCoordsTexture**(): `Texture`

create coords texture, needed to grab coordinates from canvas
encode coords coordinate into 4 bytes:
  - 8 lower bits for x
  - 8 lower bits for y
  - 4 higher bits for x
  - 4 higher bits for y
  - 8 bits for coordsIndex (1 .. 255) (= number of terraintile), is later setted in draw_terrain uniform value

#### Returns

`Texture`

- the texture

#### Defined in

[src/render/terrain.ts:257](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L257)

___

### getDEMElevation

▸ **getDEMElevation**(`tileID`, `x`, `y`, `extent?`): `number`

get the elevation-value from original dem-data for a given tile-coordinate

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | `undefined` | the tile to get elevation for |
| `x` | `number` | `undefined` | between 0 .. EXTENT |
| `y` | `number` | `undefined` | between 0 .. EXTENT |
| `extent` | `number` | `EXTENT` | optional, default 8192 |

#### Returns

`number`

- the elevation

#### Defined in

[src/render/terrain.ts:129](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L129)

___

### getElevation

▸ **getElevation**(`tileID`, `x`, `y`, `extent?`): `number`

get the Elevation for given coordinate in respect of exaggeration.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | `undefined` | the tile id |
| `x` | `number` | `undefined` | between 0 .. EXTENT |
| `y` | `number` | `undefined` | between 0 .. EXTENT |
| `extent` | `number` | `EXTENT` | optional, default 8192 |

#### Returns

`number`

- the elevation

#### Defined in

[src/render/terrain.ts:154](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L154)

___

### getFramebuffer

▸ **getFramebuffer**(`texture`): `Framebuffer`

get a framebuffer as big as the map-div, which will be used to render depth & coords into a texture

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `texture` | `string` | the texture |

#### Returns

`Framebuffer`

the frame buffer

#### Defined in

[src/render/terrain.ts:219](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L219)

___

### getMeshFrameDelta

▸ **getMeshFrameDelta**(`zoom`): `number`

Calculates a height of the frame around the terrain-mesh to avoid stiching between
tile boundaries in different zoomlevels.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `zoom` | `number` | current zoomlevel |

#### Returns

`number`

the elevation delta in meters

#### Defined in

[src/render/terrain.ts:353](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L353)

___

### getMinMaxElevation

▸ **getMinMaxElevation**(`tileID`): `Object`

Get the minimum and maximum elevation contained in a tile. This includes any
exaggeration included in the terrain.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | Id of the tile to be used as a source for the min/max elevation |

#### Returns

`Object`

Minimum and maximum elevation found in the tile, including the terrain's
exaggeration

| Name | Type |
| :------ | :------ |
| `maxElevation` | `number` |
| `minElevation` | `number` |

#### Defined in

[src/render/terrain.ts:366](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L366)

___

### getTerrainData

▸ **getTerrainData**(`tileID`): `TerrainData`

returns a Terrain Object for a tile. Unless the tile corresponds to data (e.g. tile is loading), return a flat dem object

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tileID` | `OverscaledTileID` | the tile to get the terrain for |

#### Returns

`TerrainData`

the terrain data to use in the program

#### Defined in

[src/render/terrain.ts:163](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L163)

___

### getTerrainMesh

▸ **getTerrainMesh**(): `TerrainMesh`

create a regular mesh which will be used by all terrain-tiles

#### Returns

`TerrainMesh`

- the created regular mesh

#### Defined in

[src/render/terrain.ts:305](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L305)

___

### pointCoordinate

▸ **pointCoordinate**(`p`): [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

Reads a pixel from the coords-framebuffer and translate this to mercator.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `p` | `Point` | Screen-Coordinate |

#### Returns

[`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

mercator coordinate for a screen pixel

#### Defined in

[src/render/terrain.ts:279](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/terrain.ts#L279)
