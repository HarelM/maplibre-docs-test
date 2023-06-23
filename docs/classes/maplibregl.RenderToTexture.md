[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / RenderToTexture

# Class: RenderToTexture

[maplibregl](../modules/maplibregl.md).RenderToTexture

RenderToTexture

## Table of contents

### Methods

- [renderLayer](maplibregl.RenderToTexture.md#renderlayer)

## Methods

### renderLayer

▸ **renderLayer**(`layer`): `boolean`

due that switching textures is relatively slow, the render
layer-by-layer context is not practicable. To bypass this problem
this lines of code stack all layers and later render all at once.
Because of the stylesheet possibility to mixing render-to-texture layers
and 'live'-layers (f.e. symbols) it is necessary to create more stacks. For example
a symbol-layer is in between of fill-layers.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layer` | `StyleLayer` | the layer to render |

#### Returns

`boolean`

if true layer is rendered to texture, otherwise false

#### Defined in

[src/render/render_to_texture.ts:114](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/render/render_to_texture.ts#L114)
