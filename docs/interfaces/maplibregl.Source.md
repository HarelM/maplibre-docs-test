[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Source

# Interface: Source

[maplibregl](../modules/maplibregl.md).Source

The `Source` interface must be implemented by each source type, including "core" types (`vector`, `raster`,
`video`, etc.) and all custom, third-party types.

**`Param`**

The id for the source. Must not be used by any existing source.

**`Param`**

Source options, specific to the source type (except for `options.type`, which is always
required).

**`Param`**

The source type, matching the value of `name` used in Style#addSourceType.

**`Param`**

A [Dispatcher](../classes/maplibregl.Dispatcher.md) instance, which can be used to send messages to the workers.

**`Fires`**

data with `{dataType: 'source', sourceDataType: 'metadata'}` to indicate that any necessary metadata
has been loaded so that it's okay to call `loadTile`; and with `{dataType: 'source', sourceDataType: 'content'}`
to indicate that the source data has changed, so that any current caches should be flushed.

## Implemented by

- [`GeoJSONSource`](../classes/maplibregl.GeoJSONSource.md)
- [`ImageSource`](../classes/maplibregl.ImageSource.md)
- [`VectorTileSource`](../classes/maplibregl.VectorTileSource.md)

## Table of contents

### Methods

- [serialize](maplibregl.Source.md#serialize)

## Methods

### serialize

▸ `Private` **serialize**(): `any`

#### Returns

`any`

A plain (stringifiable) JS object representing the current state of the source.
Creating a source using the returned object as the `options` should result in a Source that is
equivalent to this one.

#### Defined in

[src/source/source.ts:71](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/source.ts#L71)
