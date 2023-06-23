[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / LngLat

# Class: LngLat

[maplibregl](../modules/maplibregl.md).LngLat

A `LngLat` object represents a given longitude and latitude coordinate, measured in degrees.
These coordinates are based on the [WGS84 (EPSG:4326) standard](https://en.wikipedia.org/wiki/World_Geodetic_System#WGS84).

MapLibre GL JS uses longitude, latitude coordinate order (as opposed to latitude, longitude) to match the
[GeoJSON specification](https://tools.ietf.org/html/rfc7946).

Note that any MapLibre GL JS method that accepts a `LngLat` object as an argument or option
can also accept an `Array` of two numbers and will perform an implicit conversion.
This flexible type is documented as [LngLatLike](../modules/maplibregl.md#lnglatlike).

**`Param`**

Longitude, measured in degrees.

**`Param`**

Latitude, measured in degrees.

**`Example`**

```ts
var ll = new maplibregl.LngLat(-123.9749, 40.7736);
ll.lng; // = -123.9749
```

**`See`**

 - [Get coordinates of the mouse pointer](https://maplibre.org/maplibre-gl-js-docs/example/mouse-position/)
 - [Display a popup](https://maplibre.org/maplibre-gl-js-docs/example/popup/)
 - [Create a timeline animation](https://maplibre.org/maplibre-gl-js-docs/example/timeline-animation/)

## Table of contents

### Methods

- [distanceTo](maplibregl.LngLat.md#distanceto)
- [toArray](maplibregl.LngLat.md#toarray)
- [toString](maplibregl.LngLat.md#tostring)
- [wrap](maplibregl.LngLat.md#wrap)
- [convert](maplibregl.LngLat.md#convert)

## Methods

### distanceTo

▸ **distanceTo**(`lngLat`): `number`

Returns the approximate distance between a pair of coordinates in meters
Uses the Haversine Formula (from R.W. Sinnott, "Virtues of the Haversine", Sky and Telescope, vol. 68, no. 2, 1984, p. 159)

**`Example`**

```ts
var new_york = new maplibregl.LngLat(-74.0060, 40.7128);
var los_angeles = new maplibregl.LngLat(-118.2437, 34.0522);
new_york.distanceTo(los_angeles); // = 3935751.690893987, "true distance" using a non-spherical approximation is ~3966km
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lngLat` | [`LngLat`](maplibregl.LngLat.md) | coordinates to compute the distance to |

#### Returns

`number`

Distance in meters between the two coordinates.

#### Defined in

[src/geo/lng_lat.ts:93](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat.ts#L93)

___

### toArray

▸ **toArray**(): [`number`, `number`]

Returns the coordinates represented as an array of two numbers.

**`Example`**

```ts
var ll = new maplibregl.LngLat(-73.9749, 40.7736);
ll.toArray(); // = [-73.9749, 40.7736]
```

#### Returns

[`number`, `number`]

The coordinates represented as an array of longitude and latitude.

#### Defined in

[src/geo/lng_lat.ts:66](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat.ts#L66)

___

### toString

▸ **toString**(): `string`

Returns the coordinates represent as a string.

**`Example`**

```ts
var ll = new maplibregl.LngLat(-73.9749, 40.7736);
ll.toString(); // = "LngLat(-73.9749, 40.7736)"
```

#### Returns

`string`

The coordinates represented as a string of the format `'LngLat(lng, lat)'`.

#### Defined in

[src/geo/lng_lat.ts:78](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat.ts#L78)

___

### wrap

▸ **wrap**(): [`LngLat`](maplibregl.LngLat.md)

Returns a new `LngLat` object whose longitude is wrapped to the range (-180, 180).

**`Example`**

```ts
var ll = new maplibregl.LngLat(286.0251, 40.7736);
var wrapped = ll.wrap();
wrapped.lng; // = -73.9749
```

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The wrapped `LngLat` object.

#### Defined in

[src/geo/lng_lat.ts:54](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat.ts#L54)

___

### convert

▸ `Static` **convert**(`input`): [`LngLat`](maplibregl.LngLat.md)

Converts an array of two numbers or an object with `lng` and `lat` or `lon` and `lat` properties
to a `LngLat` object.

If a `LngLat` object is passed in, the function returns it unchanged.

**`Example`**

```ts
var arr = [-73.9749, 40.7736];
var ll = maplibregl.LngLat.convert(arr);
ll;   // = LngLat {lng: -73.9749, lat: 40.7736}
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | An array of two numbers or object to convert, or a `LngLat` object to return. |

#### Returns

[`LngLat`](maplibregl.LngLat.md)

A new `LngLat` object, if a conversion occurred, or the original `LngLat` object.

#### Defined in

[src/geo/lng_lat.ts:116](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat.ts#L116)
