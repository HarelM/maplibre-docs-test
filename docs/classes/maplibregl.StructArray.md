[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / StructArray

# Class: StructArray

[maplibregl](../modules/maplibregl.md).StructArray

`StructArray` provides an abstraction over `ArrayBuffer` and `TypedArray`
making it behave like an array of typed structs.

Conceptually, a StructArray is comprised of elements, i.e., instances of its
associated struct type. Each particular struct type, together with an
alignment size, determines the memory layout of a StructArray whose elements
are of that type.  Thus, for each such layout that we need, we have
a corresponding StructArrayLayout class, inheriting from StructArray and
implementing `emplaceBack()` and `_refreshViews()`.

In some cases, where we need to access particular elements of a StructArray,
we implement a more specific subclass that inherits from one of the
StructArrayLayouts and adds a `get(i): T` accessor that returns a structured
object whose properties are proxies into the underlying memory space for the
i-th element.  This affords the convience of working with (seemingly) plain
Javascript objects without the overhead of serializing/deserializing them
into ArrayBuffers for efficient web worker transfer.

## Hierarchy

- **`StructArray`**

  ↳ [`StructArrayLayout4i8`](maplibregl.StructArrayLayout4i8.md)

  ↳ [`StructArrayLayout6i1ul2ui20`](maplibregl.StructArrayLayout6i1ul2ui20.md)

  ↳ [`StructArrayLayout3ui6`](maplibregl.StructArrayLayout3ui6.md)

  ↳ [`StructArrayLayout2ui4`](maplibregl.StructArrayLayout2ui4.md)

  ↳ [`StructArrayLayout1ui2`](maplibregl.StructArrayLayout1ui2.md)

  ↳ [`StructArrayLayout3i6`](maplibregl.StructArrayLayout3i6.md)

  ↳ [`StructArrayLayout1f4`](maplibregl.StructArrayLayout1f4.md)

  ↳ [`StructArrayLayout8i15ui1ul4f68`](maplibregl.StructArrayLayout8i15ui1ul4f68.md)

  ↳ [`StructArrayLayout1ul2ui8`](maplibregl.StructArrayLayout1ul2ui8.md)

  ↳ [`StructArrayLayout4i4ui4i24`](maplibregl.StructArrayLayout4i4ui4i24.md)

  ↳ [`StructArrayLayout3f12`](maplibregl.StructArrayLayout3f12.md)

  ↳ [`StructArrayLayout1ul4`](maplibregl.StructArrayLayout1ul4.md)

  ↳ [`StructArrayLayout2ub2f12`](maplibregl.StructArrayLayout2ub2f12.md)

  ↳ [`StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48`](maplibregl.StructArrayLayout2i2ui3ul3ui2f3ub1ul1i48.md)

  ↳ [`StructArrayLayout2i4`](maplibregl.StructArrayLayout2i4.md)

  ↳ [`StructArrayLayout2i4i12`](maplibregl.StructArrayLayout2i4i12.md)

  ↳ [`StructArrayLayout2i4ub8`](maplibregl.StructArrayLayout2i4ub8.md)

  ↳ [`StructArrayLayout2f8`](maplibregl.StructArrayLayout2f8.md)

## Table of contents

### Methods

- [\_refreshViews](maplibregl.StructArray.md#_refreshviews)
- [\_trim](maplibregl.StructArray.md#_trim)
- [clear](maplibregl.StructArray.md#clear)
- [reserve](maplibregl.StructArray.md#reserve)
- [resize](maplibregl.StructArray.md#resize)
- [serialize](maplibregl.StructArray.md#serialize)

## Methods

### \_refreshViews

▸ **_refreshViews**(): `void`

Create TypedArray views for the current ArrayBuffer.

#### Returns

`void`

#### Defined in

[src/util/struct_array.ts:183](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L183)

___

### \_trim

▸ **_trim**(): `void`

Resize the array to discard unused capacity.

#### Returns

`void`

#### Defined in

[src/util/struct_array.ts:138](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L138)

___

### clear

▸ **clear**(): `void`

Resets the the length of the array to 0 without de-allocating capcacity.

#### Returns

`void`

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

#### Defined in

[src/util/struct_array.ts:111](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/struct_array.ts#L111)
