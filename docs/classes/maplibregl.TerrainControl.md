[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TerrainControl

# Class: TerrainControl

[maplibregl](../modules/maplibregl.md).TerrainControl

A `TerrainControl` control contains a button for turning the terrain on and off.

**`Implements`**

**`Param`**

**`Param`**

The ID of the raster-dem source to use.

**`Param`**

**`Example`**

```ts
var map = new maplibregl.Map({TerrainControl: false})
    .addControl(new maplibregl.TerrainControl({
        source: "terrain"
    }));
```

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)
