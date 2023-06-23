[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / FeatureIndexArray

# Class: FeatureIndexArray

[maplibregl](../modules/maplibregl.md).FeatureIndexArray

## Hierarchy

- [`StructArrayLayout1ul2ui8`](maplibregl.StructArrayLayout1ul2ui8.md)

  ↳ **`FeatureIndexArray`**

## Table of contents

### Methods

- [\_trim](maplibregl.FeatureIndexArray.md#_trim)
- [clear](maplibregl.FeatureIndexArray.md#clear)
- [get](maplibregl.FeatureIndexArray.md#get)
- [reserve](maplibregl.FeatureIndexArray.md#reserve)
- [resize](maplibregl.FeatureIndexArray.md#resize)
- [serialize](maplibregl.FeatureIndexArray.md#serialize)

## Methods

### \_trim

▸ **_trim**(): `void`

Resize the array to discard unused capacity.

#### Returns

`void`

#### Inherited from

[StructArrayLayout1ul2ui8](maplibregl.StructArrayLayout1ul2ui8.md).[_trim](maplibregl.StructArrayLayout1ul2ui8.md#_trim)

#### Defined in

[src/util/struct_array.ts:138](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L138)

___

### clear

▸ **clear**(): `void`

Resets the the length of the array to 0 without de-allocating capcacity.

#### Returns

`void`

#### Inherited from

[StructArrayLayout1ul2ui8](maplibregl.StructArrayLayout1ul2ui8.md).[clear](maplibregl.StructArrayLayout1ul2ui8.md#clear)

#### Defined in

[src/util/struct_array.ts:149](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L149)

___

### get

▸ `Private` **get**(`index`): `FeatureIndexStruct`

Return the FeatureIndexStruct at the given location in the array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `index` | `number` | The index of the element. |

#### Returns

`FeatureIndexStruct`

#### Defined in

src/data/array_types.g.ts:1022

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

[StructArrayLayout1ul2ui8](maplibregl.StructArrayLayout1ul2ui8.md).[reserve](maplibregl.StructArrayLayout1ul2ui8.md#reserve)

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

[StructArrayLayout1ul2ui8](maplibregl.StructArrayLayout1ul2ui8.md).[resize](maplibregl.StructArrayLayout1ul2ui8.md#resize)

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

[StructArrayLayout1ul2ui8](maplibregl.StructArrayLayout1ul2ui8.md).[serialize](maplibregl.StructArrayLayout1ul2ui8.md#serialize)

#### Defined in

[src/util/struct_array.ts:111](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L111)
