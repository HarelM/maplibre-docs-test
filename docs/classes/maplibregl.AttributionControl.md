[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / AttributionControl

# Class: AttributionControl

[maplibregl](../modules/maplibregl.md).AttributionControl

An `AttributionControl` control presents the map's attribution information. By default, the attribution control is expanded (regardless of map width).

**`Implements`**

**`Param`**

**`Param`**

If `true`, the attribution control will always collapse when moving the map. If `false`, force the expanded attribution control. The default is a responsive attribution that collapses when the user moves the map on maps less than 640 pixels wide.  **Attribution should not be collapsed if it can comfortably fit on the map. `compact` should only be used to modify default attribution when map size makes it impossible to fit default attribution and when the automatic compact resizing for default settings are not sufficient.**

**`Param`**

String or strings to show in addition to any other attributions.

**`Example`**

```ts
var map = new maplibregl.Map({attributionControl: false})
    .addControl(new maplibregl.AttributionControl({
        compact: true
    }));
```

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)
