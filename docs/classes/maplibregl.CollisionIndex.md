[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / CollisionIndex

# Class: CollisionIndex

[maplibregl](../modules/maplibregl.md).CollisionIndex

A collision index used to prevent symbols from overlapping. It keep tracks of
where previous symbols have been placed and is used to check if a new
symbol overlaps with any previously added symbols.

There are two steps to insertion: first placeCollisionBox/Circles checks if
there's room for a symbol, then insertCollisionBox/Circles actually puts the
symbol in the index. The two step process allows paired symbols to be inserted
together even if they overlap.

## Table of contents

### Methods

- [queryRenderedSymbols](maplibregl.CollisionIndex.md#queryrenderedsymbols)

## Methods

### queryRenderedSymbols

▸ `Private` **queryRenderedSymbols**(`viewportQueryGeometry`): `Object`

Because the geometries in the CollisionIndex are an approximation of the shape of
symbols on the map, we use the CollisionIndex to look up the symbol part of
`queryRenderedFeatures`.

#### Parameters

| Name | Type |
| :------ | :------ |
| `viewportQueryGeometry` | `Point`[] |

#### Returns

`Object`

#### Defined in

[src/symbol/collision_index.ts:288](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/symbol/collision_index.ts#L288)
