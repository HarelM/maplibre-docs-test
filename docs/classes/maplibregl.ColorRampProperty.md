[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / ColorRampProperty

# Class: ColorRampProperty

[maplibregl](../modules/maplibregl.md).ColorRampProperty

An implementation of `Property` for `heatmap-color` and `line-gradient`. Interpolation is a no-op, and
evaluation returns a boolean value in order to indicate its presence, but the real
evaluation happens in StyleLayer classes.

## Implements

- [`Property`](../interfaces/maplibregl.Property.md)<`Color`, `boolean`\>
