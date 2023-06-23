[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / LngLatBounds

# Class: LngLatBounds

[maplibregl](../modules/maplibregl.md).LngLatBounds

A `LngLatBounds` object represents a geographical bounding box,
defined by its southwest and northeast points in longitude and latitude.

If no arguments are provided to the constructor, a `null` bounding box is created.

Note that any Mapbox GL method that accepts a `LngLatBounds` object as an argument or option
can also accept an `Array` of two [LngLatLike](../modules/maplibregl.md#lnglatlike) constructs and will perform an implicit conversion.
This flexible type is documented as [LngLatBoundsLike](../modules/maplibregl.md#lnglatboundslike).

**`Param`**

The southwest corner of the bounding box.

**`Param`**

The northeast corner of the bounding box.

**`Example`**

```ts
var sw = new maplibregl.LngLat(-73.9876, 40.7661);
var ne = new maplibregl.LngLat(-73.9397, 40.8002);
var llb = new maplibregl.LngLatBounds(sw, ne);
```

## Table of contents

### Constructors

- [constructor](maplibregl.LngLatBounds.md#constructor)

### Methods

- [contains](maplibregl.LngLatBounds.md#contains)
- [extend](maplibregl.LngLatBounds.md#extend)
- [getCenter](maplibregl.LngLatBounds.md#getcenter)
- [getEast](maplibregl.LngLatBounds.md#geteast)
- [getNorth](maplibregl.LngLatBounds.md#getnorth)
- [getNorthEast](maplibregl.LngLatBounds.md#getnortheast)
- [getNorthWest](maplibregl.LngLatBounds.md#getnorthwest)
- [getSouth](maplibregl.LngLatBounds.md#getsouth)
- [getSouthEast](maplibregl.LngLatBounds.md#getsoutheast)
- [getSouthWest](maplibregl.LngLatBounds.md#getsouthwest)
- [getWest](maplibregl.LngLatBounds.md#getwest)
- [isEmpty](maplibregl.LngLatBounds.md#isempty)
- [setNorthEast](maplibregl.LngLatBounds.md#setnortheast)
- [setSouthWest](maplibregl.LngLatBounds.md#setsouthwest)
- [toArray](maplibregl.LngLatBounds.md#toarray)
- [toString](maplibregl.LngLatBounds.md#tostring)
- [convert](maplibregl.LngLatBounds.md#convert)
- [fromLngLat](maplibregl.LngLatBounds.md#fromlnglat)

## Constructors

### constructor

• **new LngLatBounds**(`sw?`, `ne?`)

**`Example`**

```ts
var sw = new maplibregl.LngLat(-73.9876, 40.7661);
var ne = new maplibregl.LngLat(-73.9397, 40.8002);
var llb = new maplibregl.LngLatBounds(sw, ne);
OR
var llb = new maplibregl.LngLatBounds([-73.9876, 40.7661, -73.9397, 40.8002]);
OR
var llb = new maplibregl.LngLatBounds([sw, ne]);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `sw?` | [`number`, `number`, `number`, `number`] \| [`LngLatLike`](../modules/maplibregl.md#lnglatlike) \| [[`LngLatLike`](../modules/maplibregl.md#lnglatlike), [`LngLatLike`](../modules/maplibregl.md#lnglatlike)] | The southwest corner of the bounding box. OR array of 4 numbers in the order of west, south, east, north OR array of 2 LngLatLike: [sw,ne] |
| `ne?` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | The northeast corner of the bounding box. |

#### Defined in

[src/geo/lng_lat_bounds.ts:39](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L39)

## Methods

### contains

▸ **contains**(`lnglat`): `boolean`

Check if the point is within the bounding box.

**`Example`**

```ts
var llb = new maplibregl.LngLatBounds(
  new maplibregl.LngLat(-73.9876, 40.7661),
  new maplibregl.LngLat(-73.9397, 40.8002)
);

var ll = new maplibregl.LngLat(-73.9567, 40.7789);

console.log(llb.contains(ll)); // = true
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | geographic point to check against. |

#### Returns

`boolean`

True if the point is within the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:246](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L246)

___

### extend

▸ **extend**(`obj`): `any`

Extend the bounds to include a given LngLatLike or LngLatBoundsLike.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `obj` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) \| [`LngLatBoundsLike`](../modules/maplibregl.md#lnglatboundslike) | object to extend to |

#### Returns

`any`

`this`

#### Defined in

[src/geo/lng_lat_bounds.ts:82](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L82)

___

### getCenter

▸ **getCenter**(): [`LngLat`](maplibregl.LngLat.md)

Returns the geographical coordinate equidistant from the bounding box's corners.

**`Example`**

```ts
var llb = new maplibregl.LngLatBounds([-73.9876, 40.7661], [-73.9397, 40.8002]);
llb.getCenter(); // = LngLat {lng: -73.96365, lat: 40.78315}
```

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The bounding box's center.

#### Defined in

[src/geo/lng_lat_bounds.ts:136](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L136)

___

### getEast

▸ **getEast**(): `number`

Returns the east edge of the bounding box.

#### Returns

`number`

The east edge of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:187](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L187)

___

### getNorth

▸ **getNorth**(): `number`

Returns the north edge of the bounding box.

#### Returns

`number`

The north edge of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:194](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L194)

___

### getNorthEast

▸ **getNorthEast**(): [`LngLat`](maplibregl.LngLat.md)

Returns the northeast corner of the bounding box.

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The northeast corner of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:152](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L152)

___

### getNorthWest

▸ **getNorthWest**(): [`LngLat`](maplibregl.LngLat.md)

Returns the northwest corner of the bounding box.

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The northwest corner of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:159](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L159)

___

### getSouth

▸ **getSouth**(): `number`

Returns the south edge of the bounding box.

#### Returns

`number`

The south edge of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:180](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L180)

___

### getSouthEast

▸ **getSouthEast**(): [`LngLat`](maplibregl.LngLat.md)

Returns the southeast corner of the bounding box.

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The southeast corner of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:166](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L166)

___

### getSouthWest

▸ **getSouthWest**(): [`LngLat`](maplibregl.LngLat.md)

Returns the southwest corner of the bounding box.

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The southwest corner of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:145](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L145)

___

### getWest

▸ **getWest**(): `number`

Returns the west edge of the bounding box.

#### Returns

`number`

The west edge of the bounding box.

#### Defined in

[src/geo/lng_lat_bounds.ts:173](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L173)

___

### isEmpty

▸ **isEmpty**(): `boolean`

Check if the bounding box is an empty/`null`-type box.

#### Returns

`boolean`

True if bounds have been defined, otherwise false.

#### Defined in

[src/geo/lng_lat_bounds.ts:227](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L227)

___

### setNorthEast

▸ **setNorthEast**(`ne`): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Set the northeast corner of the bounding box

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `ne` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | a [LngLatLike](../modules/maplibregl.md#lnglatlike) object describing the northeast corner of the bounding box. |

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

`this`

#### Defined in

[src/geo/lng_lat_bounds.ts:60](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L60)

___

### setSouthWest

▸ **setSouthWest**(`sw`): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Set the southwest corner of the bounding box

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `sw` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | a [LngLatLike](../modules/maplibregl.md#lnglatlike) object describing the southwest corner of the bounding box. |

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

`this`

#### Defined in

[src/geo/lng_lat_bounds.ts:71](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L71)

___

### toArray

▸ **toArray**(): [`number`, `number`][]

Returns the bounding box represented as an array.

**`Example`**

```ts
var llb = new maplibregl.LngLatBounds([-73.9876, 40.7661], [-73.9397, 40.8002]);
llb.toArray(); // = [[-73.9876, 40.7661], [-73.9397, 40.8002]]
```

#### Returns

[`number`, `number`][]

The bounding box represented as an array, consisting of the
southwest and northeast coordinates of the bounding represented as arrays of numbers.

#### Defined in

[src/geo/lng_lat_bounds.ts:205](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L205)

___

### toString

▸ **toString**(): `string`

Return the bounding box represented as a string.

**`Example`**

```ts
var llb = new maplibregl.LngLatBounds([-73.9876, 40.7661], [-73.9397, 40.8002]);
llb.toString(); // = "LngLatBounds(LngLat(-73.9876, 40.7661), LngLat(-73.9397, 40.8002))"
```

#### Returns

`string`

The bounding box represents as a string of the format
`'LngLatBounds(LngLat(lng, lat), LngLat(lng, lat))'`.

#### Defined in

[src/geo/lng_lat_bounds.ts:218](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L218)

___

### convert

▸ `Static` **convert**(`input`): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Converts an array to a `LngLatBounds` object.

If a `LngLatBounds` object is passed in, the function returns it unchanged.

Internally, the function calls `LngLat#convert` to convert arrays to `LngLat` values.

**`Example`**

```ts
var arr = [[-73.9876, 40.7661], [-73.9397, 40.8002]];
var llb = maplibregl.LngLatBounds.convert(arr);
llb;   // = LngLatBounds {_sw: LngLat {lng: -73.9876, lat: 40.7661}, _ne: LngLat {lng: -73.9397, lat: 40.8002}}
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | [`LngLatBoundsLike`](../modules/maplibregl.md#lnglatboundslike) | An array of two coordinates to convert, or a `LngLatBounds` object to return. |

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

A new `LngLatBounds` object, if a conversion occurred, or the original `LngLatBounds` object.

#### Defined in

[src/geo/lng_lat_bounds.ts:272](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L272)

___

### fromLngLat

▸ `Static` **fromLngLat**(`center`, `radius?`): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns a `LngLatBounds` from the coordinates extended by a given `radius`. The returned `LngLatBounds` completely contains the `radius`.

**`Example`**

```ts
var center = new maplibregl.LngLat(-73.9749, 40.7736);
maplibregl.LngLatBounds.fromLngLat(100).toArray(); // = [[-73.97501862141328, 40.77351016847229], [-73.97478137858673, 40.77368983152771]]
```

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `center` | [`LngLat`](maplibregl.LngLat.md) | `undefined` | center coordinates of the new bounds. |
| `radius?` | `number` | `0` | Distance in meters from the coordinates to extend the bounds. |

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

A new `LngLatBounds` object representing the coordinates extended by the `radius`.

#### Defined in

[src/geo/lng_lat_bounds.ts:288](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/lng_lat_bounds.ts#L288)
