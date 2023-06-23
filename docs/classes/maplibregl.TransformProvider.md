[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TransformProvider

# Class: TransformProvider

[maplibregl](../modules/maplibregl.md).TransformProvider

Shared utilities for the Handler classes to access the correct camera state.
If Camera.transformCameraUpdate is specified, the "desired state" of camera may differ from the state used for rendering.
The handlers need the "desired state" to track accumulated changes.
