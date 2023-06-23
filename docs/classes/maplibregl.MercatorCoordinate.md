[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / MercatorCoordinate

# Class: MercatorCoordinate

[maplibregl](../modules/maplibregl.md).MercatorCoordinate

A `MercatorCoordinate` object represents a projected three dimensional position.

`MercatorCoordinate` uses the web mercator projection ([EPSG:3857](https://epsg.io/3857)) with slightly different units:
- the size of 1 unit is the width of the projected world instead of the "mercator meter"
- the origin of the coordinate space is at the north-west corner instead of the middle

For example, `MercatorCoordinate(0, 0, 0)` is the north-west corner of the mercator world and
`MercatorCoordinate(1, 1, 0)` is the south-east corner. If you are familiar with
[vector tiles](https://github.com/mapbox/vector-tile-spec) it may be helpful to think
of the coordinate space as the `0/0/0` tile with an extent of `1`.

The `z` dimension of `MercatorCoordinate` is conformal. A cube in the mercator coordinate space would be rendered as a cube.

**`Param`**

The x component of the position.

**`Param`**

The y component of the position.

**`Param`**

The z component of the position.

**`Example`**

```ts
var nullIsland = new maplibregl.MercatorCoordinate(0.5, 0.5, 0);
```

**`See`**

[Add a custom style layer](https://maplibre.org/maplibre-gl-js-docs/example/custom-style-layer/)

## Implements

- `IMercatorCoordinate`

## Table of contents

### Methods

- [meterInMercatorCoordinateUnits](maplibregl.MercatorCoordinate.md#meterinmercatorcoordinateunits)
- [toAltitude](maplibregl.MercatorCoordinate.md#toaltitude)
- [toLngLat](maplibregl.MercatorCoordinate.md#tolnglat)
- [fromLngLat](maplibregl.MercatorCoordinate.md#fromlnglat)

## Methods

### meterInMercatorCoordinateUnits

▸ **meterInMercatorCoordinateUnits**(): `number`

Returns the distance of 1 meter in `MercatorCoordinate` units at this latitude.

For coordinates in real world units using meters, this naturally provides the scale
to transform into `MercatorCoordinate`s.

#### Returns

`number`

Distance of 1 meter in `MercatorCoordinate` units.

#### Implementation of

IMercatorCoordinate.meterInMercatorCoordinateUnits

#### Defined in

[src/geo/mercator_coordinate.ts:142](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/mercator_coordinate.ts#L142)

___

### toAltitude

▸ **toAltitude**(): `number`

Returns the altitude in meters of the coordinate.

**`Example`**

```ts
var coord = new maplibregl.MercatorCoordinate(0, 0, 0.02);
coord.toAltitude(); // 6914.281956295339
```

#### Returns

`number`

The altitude in meters.

#### Implementation of

IMercatorCoordinate.toAltitude

#### Defined in

[src/geo/mercator_coordinate.ts:130](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/mercator_coordinate.ts#L130)

___

### toLngLat

▸ **toLngLat**(): [`LngLat`](maplibregl.LngLat.md)

Returns the `LngLat` for the coordinate.

**`Example`**

```ts
var coord = new maplibregl.MercatorCoordinate(0.5, 0.5, 0);
var lngLat = coord.toLngLat(); // LngLat(0, 0)
```

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The `LngLat` object.

#### Implementation of

IMercatorCoordinate.toLngLat

#### Defined in

[src/geo/mercator_coordinate.ts:116](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/mercator_coordinate.ts#L116)

___

### fromLngLat

▸ `Static` **fromLngLat**(`lngLatLike`, `altitude?`): [`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

Project a `LngLat` to a `MercatorCoordinate`.

**`Example`**

```ts
var coord = maplibregl.MercatorCoordinate.fromLngLat({ lng: 0, lat: 0}, 0);
coord; // MercatorCoordinate(0.5, 0.5, 0)
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `lngLatLike` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | `undefined` | The location to project. |
| `altitude` | `number` | `0` | The altitude in meters of the position. |

#### Returns

[`MercatorCoordinate`](maplibregl.MercatorCoordinate.md)

The projected mercator coordinate.

#### Defined in

[src/geo/mercator_coordinate.ts:99](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/mercator_coordinate.ts#L99)
