[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / NavigationControl

# Class: NavigationControl

[maplibregl](../modules/maplibregl.md).NavigationControl

A `NavigationControl` control contains zoom buttons and a compass.

**`Implements`**

**`Param`**

**`Param`**

If `true` the compass button is included.

**`Param`**

If `true` the zoom-in and zoom-out buttons are included.

**`Param`**

If `true` the pitch is visualized by rotating X-axis of compass.

**`Example`**

```ts
var nav = new maplibregl.NavigationControl();
map.addControl(nav, 'top-left');
```

**`See`**

 - [Display map navigation controls](https://maplibre.org/maplibre-gl-js-docs/example/navigation/)
 - [Add a third party vector tile source](https://maplibre.org/maplibre-gl-js-docs/example/third-party/)

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)
