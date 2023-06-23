[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / PlacedSymbolArray

# Class: PlacedSymbolArray

[maplibregl](../modules/maplibregl.md).PlacedSymbolArray

## Hierarchy

- [`StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48`](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md)

  ↳ **`PlacedSymbolArray`**

## Table of contents

### Methods

- [\_trim](maplibregl.PlacedSymbolArray.md#_trim)
- [clear](maplibregl.PlacedSymbolArray.md#clear)
- [get](maplibregl.PlacedSymbolArray.md#get)
- [reserve](maplibregl.PlacedSymbolArray.md#reserve)
- [resize](maplibregl.PlacedSymbolArray.md#resize)
- [serialize](maplibregl.PlacedSymbolArray.md#serialize)

## Methods

### \_trim

▸ **_trim**(): `void`

Resize the array to discard unused capacity.

#### Returns

`void`

#### Inherited from

[StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md).[_trim](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md#_trim)

#### Defined in

[src/util/struct_array.ts:138](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L138)

___

### clear

▸ **clear**(): `void`

Resets the the length of the array to 0 without de-allocating capcacity.

#### Returns

`void`

#### Inherited from

[StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md).[clear](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md#clear)

#### Defined in

[src/util/struct_array.ts:149](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L149)

___

### get

▸ `Private` **get**(`index`): `PlacedSymbolStruct`

Return the PlacedSymbolStruct at the given location in the array.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `index` | `number` | The index of the element. |

#### Returns

`PlacedSymbolStruct`

#### Defined in

src/data/array_types.g.ts:922

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

[StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md).[reserve](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md#reserve)

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

[StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md).[resize](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md#resize)

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

[StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md).[serialize](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md#serialize)

#### Defined in

[src/util/struct_array.ts:111](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L111)
