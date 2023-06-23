[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / LineAtlas

# Class: LineAtlas

[maplibregl](../modules/maplibregl.md).LineAtlas

A LineAtlas lets us reuse rendered dashed lines
by writing many of them to a texture and then fetching their positions
using .getDash.

**`Param`**

**`Param`**

## Table of contents

### Methods

- [getDash](maplibregl.LineAtlas.md#getdash)

## Methods

### getDash

▸ `Private` **getDash**(`dasharray`, `round`): `any`

Get or create a dash line pattern.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `dasharray` | `number`[] |  |
| `round` | `boolean` | whether to add circle caps in between dash segments |

#### Returns

`any`

position of dash texture in { y, height, width }

#### Defined in

[src/render/line_atlas.ts:42](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/line_atlas.ts#L42)
