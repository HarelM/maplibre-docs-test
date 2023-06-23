[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Bucket

# Interface: Bucket

[maplibregl](../modules/maplibregl.md).Bucket

The `Bucket` interface is the single point of knowledge about turning vector
tiles into WebGL buffers.

`Bucket` is an abstract interface. An implementation exists for each style layer type.
Create a bucket via the `StyleLayer#createBucket` method.

The concrete bucket types, using layout options from the style layer,
transform feature geometries into vertex and index data for use by the
vertex shader.  They also (via `ProgramConfiguration`) use feature
properties and the zoom level to populate the attributes needed for
data-driven styling.

Buckets are designed to be built on a worker thread and then serialized and
transferred back to the main thread for rendering.  On the worker side, a
bucket's vertex, index, and attribute data is stored in `bucket.arrays:
ArrayGroup`.  When a bucket's data is serialized and sent back to the main
thread, is gets deserialized (using `new Bucket(serializedBucketData)`, with
the array data now stored in `bucket.buffers: BufferGroup`.  BufferGroups
hold the same data as ArrayGroups, but are tuned for consumption by WebGL.

## Implemented by

- [`CircleBucket`](../classes/maplibregl.CircleBucket.md)
- [`LineBucket`](../classes/maplibregl.LineBucket.md)
- [`SymbolBucket`](../classes/maplibregl.SymbolBucket.md)

## Table of contents

### Methods

- [destroy](maplibregl.Bucket.md#destroy)

## Methods

### destroy

▸ `Private` **destroy**(): `void`

Release the WebGL resources associated with the buffers. Note that because
buckets are shared between layers having the same layout properties, they
must be destroyed in groups (all buckets for a tile, or all symbol buckets).

#### Returns

`void`

#### Defined in

[src/data/bucket.ts:96](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/data/bucket.ts#L96)
