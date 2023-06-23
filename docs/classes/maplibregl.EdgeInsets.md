[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / EdgeInsets

# Class: EdgeInsets

[maplibregl](../modules/maplibregl.md).EdgeInsets

An `EdgeInset` object represents screen space padding applied to the edges of the viewport.
This shifts the apprent center or the vanishing point of the map. This is useful for adding floating UI elements
on top of the map and having the vanishing point shift as UI elements resize.

**`Param`**

**`Param`**

**`Param`**

**`Param`**

## Table of contents

### Methods

- [getCenter](maplibregl.EdgeInsets.md#getcenter)
- [interpolate](maplibregl.EdgeInsets.md#interpolate)
- [toJSON](maplibregl.EdgeInsets.md#tojson)

## Methods

### getCenter

▸ **getCenter**(`width`, `height`): `Point`

Utility method that computes the new apprent center or vanishing point after applying insets.
This is in pixels and with the top left being (0.0) and +y being downwards.

**`Memberof`**

EdgeInsets

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `width` | `number` | the width |
| `height` | `number` | the height |

#### Returns

`Point`

the point

#### Defined in

[src/geo/edge_insets.ts:63](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/edge_insets.ts#L63)

___

### interpolate

▸ **interpolate**(`start`, `target`, `t`): [`EdgeInsets`](maplibregl.EdgeInsets.md)

Interpolates the inset in-place.
This maintains the current inset value for any inset not present in `target`.

**`Memberof`**

EdgeInsets

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `start` | [`EdgeInsets`](maplibregl.EdgeInsets.md) \| [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | interpolation start |
| `target` | [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | interpolation target |
| `t` | `number` | interpolation step/weight |

#### Returns

[`EdgeInsets`](maplibregl.EdgeInsets.md)

the insets

#### Defined in

[src/geo/edge_insets.ts:45](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/edge_insets.ts#L45)

___

### toJSON

▸ **toJSON**(): [`PaddingOptions`](../modules/maplibregl.md#paddingoptions)

Returns the current state as json, useful when you want to have a
read-only representation of the inset.

**`Memberof`**

EdgeInsets

#### Returns

[`PaddingOptions`](../modules/maplibregl.md#paddingoptions)

state as json

#### Defined in

[src/geo/edge_insets.ts:89](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/geo/edge_insets.ts#L89)
