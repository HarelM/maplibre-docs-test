[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Painter

# Class: Painter

[maplibregl](../modules/maplibregl.md).Painter

Initialize a new painter object.

**`Param`**

a webgl drawing context

## Table of contents

### Methods

- [isPatternMissing](maplibregl.Painter.md#ispatternmissing)
- [translatePosMatrix](maplibregl.Painter.md#translateposmatrix)

## Methods

### isPatternMissing

▸ `Private` **isPatternMissing**(`image?`): `boolean`

Checks whether a pattern image is needed, and if it is, whether it is not loaded.

#### Parameters

| Name | Type |
| :------ | :------ |
| `image?` | `CrossFaded`<`ResolvedImage`\> |

#### Returns

`boolean`

true if a needed image is missing and rendering needs to be skipped.

#### Defined in

[src/render/painter.ts:565](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/painter.ts#L565)

___

### translatePosMatrix

▸ `Private` **translatePosMatrix**(`matrix`, `tile`, `translate`, `translateAnchor`, `inViewportPixelUnitsUnits?`): `mat4`

Transform a matrix to incorporate the *-translate and *-translate-anchor properties into it.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `matrix` | `mat4` | - |
| `tile` | [`Tile`](maplibregl.Tile.md) | - |
| `translate` | [`number`, `number`] | - |
| `translateAnchor` | ``"map"`` \| ``"viewport"`` | - |
| `inViewportPixelUnitsUnits?` | `boolean` | True when the units accepted by the matrix are in viewport pixels instead of tile units. |

#### Returns

`mat4`

matrix

#### Defined in

[src/render/painter.ts:518](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/painter.ts#L518)
