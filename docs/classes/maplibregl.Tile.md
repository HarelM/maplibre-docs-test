[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Tile

# Class: Tile

[maplibregl](../modules/maplibregl.md).Tile

A tile object is the combination of a Coordinate, which defines
its place, as well as a unique ID and data tracking for its content

## Table of contents

### Constructors

- [constructor](maplibregl.Tile.md#constructor)

### Methods

- [loadVectorData](maplibregl.Tile.md#loadvectordata)
- [unloadVectorData](maplibregl.Tile.md#unloadvectordata)

## Constructors

### constructor

• `Private` **new Tile**(`tileID`, `size`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `tileID` | `OverscaledTileID` |
| `size` | `number` |

#### Defined in

[src/source/tile.ts:103](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile.ts#L103)

## Methods

### loadVectorData

▸ `Private` **loadVectorData**(`data`, `painter`, `justReloaded?`): `void`

Given a data object with a 'buffers' property, load it into
this tile's elementGroups and buffers properties and set loaded
to true. If the data is null, like in the case of an empty
GeoJSON tile, no-op but still set loaded to true.

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `WorkerTileResult` |
| `painter` | `any` |
| `justReloaded?` | `boolean` |

#### Returns

`void`

#### Defined in

[src/source/tile.ts:156](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile.ts#L156)

___

### unloadVectorData

▸ `Private` **unloadVectorData**(): `void`

Release any data or WebGL resources referenced by this tile.

#### Returns

`void`

#### Defined in

[src/source/tile.ts:231](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/tile.ts#L231)
