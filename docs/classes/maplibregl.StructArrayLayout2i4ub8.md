[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / StructArrayLayout2i4ub8

# Class: StructArrayLayout2i4ub8

[maplibregl](../modules/maplibregl.md).StructArrayLayout2i4ub8

Implementation of the StructArray layout:
[0]: Int16[2]
[4]: Uint8[4]

## Hierarchy

- [`StructArray`](maplibregl.StructArray.md)

  ↳ **`StructArrayLayout2i4ub8`**

## Table of contents

### Methods

- [\_trim](maplibregl.StructArrayLayout2i4ub8.md#_trim)
- [clear](maplibregl.StructArrayLayout2i4ub8.md#clear)
- [reserve](maplibregl.StructArrayLayout2i4ub8.md#reserve)
- [resize](maplibregl.StructArrayLayout2i4ub8.md#resize)
- [serialize](maplibregl.StructArrayLayout2i4ub8.md#serialize)

## Methods

### \_trim

▸ **_trim**(): `void`

Resize the array to discard unused capacity.

#### Returns

`void`

#### Inherited from

[StructArray](maplibregl.StructArray.md).[_trim](maplibregl.StructArray.md#_trim)

#### Defined in

[src/util/struct_array.ts:138](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L138)

___

### clear

▸ **clear**(): `void`

Resets the the length of the array to 0 without de-allocating capcacity.

#### Returns

`void`

#### Inherited from

[StructArray](maplibregl.StructArray.md).[clear](maplibregl.StructArray.md#clear)

#### Defined in

[src/util/struct_array.ts:149](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L149)

___

### reserve

▸ **reserve**(`n`): `void`

Indicate a planned increase in size, so that any necessary allocation may
be done once, ahead of time.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `n` | `number` | The expected size of the array. |

#### Returns

`void`

#### Inherited from

[StructArray](maplibregl.StructArray.md).[reserve](maplibregl.StructArray.md#reserve)

#### Defined in

[src/util/struct_array.ts:169](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L169)

___

### resize

▸ **resize**(`n`): `void`

Resize the array.
If `n` is greater than the current length then additional elements with undefined values are added.
If `n` is less than the current length then the array will be reduced to the first `n` elements.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `n` | `number` | The new size of the array. |

#### Returns

`void`

#### Inherited from

[StructArray](maplibregl.StructArray.md).[resize](maplibregl.StructArray.md#resize)

#### Defined in

[src/util/struct_array.ts:159](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L159)

___

### serialize

▸ `Static` `Private` **serialize**(`array`, `transferables?`): `SerializedStructArray`

Serialize a StructArray instance.  Serializes both the raw data and the
metadata needed to reconstruct the StructArray base class during
deserialization.

#### Parameters

| Name | Type |
| :------ | :------ |
| `array` | [`StructArray`](maplibregl.StructArray.md) |
| `transferables?` | `Transferable`[] |

#### Returns

`SerializedStructArray`

#### Inherited from

[StructArray](maplibregl.StructArray.md).[serialize](maplibregl.StructArray.md#serialize)

#### Defined in

[src/util/struct_array.ts:111](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L111)