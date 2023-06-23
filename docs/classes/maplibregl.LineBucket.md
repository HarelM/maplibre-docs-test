[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / LineBucket

# Class: LineBucket

[maplibregl](../modules/maplibregl.md).LineBucket

## Implements

- [`Bucket`](../interfaces/maplibregl.Bucket.md)

## Table of contents

### Methods

- [addCurrentVertex](maplibregl.LineBucket.md#addcurrentvertex)

## Methods

### addCurrentVertex

▸ `Private` **addCurrentVertex**(`p`, `normal`, `endLeft`, `endRight`, `segment`, `round?`): `void`

Add two vertices to the buffers.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `p` | `Point` | `undefined` | the line vertex to add buffer vertices for |
| `normal` | `Point` | `undefined` | vertex normal |
| `endLeft` | `number` | `undefined` | extrude to shift the left vertex along the line |
| `endRight` | `number` | `undefined` | extrude to shift the left vertex along the line |
| `segment` | `Segment` | `undefined` | the segment object to add the vertex to |
| `round` | `boolean` | `false` | whether this is a round cap |

#### Returns

`void`

#### Defined in

[src/data/bucket/line_bucket.ts:514](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/data/bucket/line_bucket.ts#L514)
