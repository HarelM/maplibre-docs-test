[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / CustomLayerInterface

# Interface: CustomLayerInterface

[maplibregl](../modules/maplibregl.md).CustomLayerInterface

Interface for custom style layers. This is a specification for
implementers to model: it is not an exported method or class.

Custom layers allow a user to render directly into the map's GL context using the map's camera.
These layers can be added between any regular layers using [addLayer](../classes/maplibregl.Map.md#addlayer).

Custom layers must have a unique `id` and must have the `type` of `"custom"`.
They must implement `render` and may implement `prerender`, `onAdd` and `onRemove`.
They can trigger rendering using [triggerRepaint](../classes/maplibregl.Map.md#triggerrepaint)
and they should appropriately handle Map.event:webglcontextlost and
Map.event:webglcontextrestored.

The `renderingMode` property controls whether the layer is treated as a `"2d"` or `"3d"` map layer. Use:
- `"renderingMode": "3d"` to use the depth buffer and share it with other layers
- `"renderingMode": "2d"` to add a layer with no depth. If you need to use the depth buffer for a `"2d"` layer you must use an offscreen
  framebuffer and [prerender](maplibregl.CustomLayerInterface.md#prerender)

 CustomLayerInterface

**`Example`**

```ts
// Custom layer implemented as ES6 class
class NullIslandLayer {
    constructor() {
        this.id = 'null-island';
        this.type = 'custom';
        this.renderingMode = '2d';
    }

    onAdd(map, gl) {
        const vertexSource = `
        uniform mat4 u_matrix;
        void main() {
            gl_Position = u_matrix * vec4(0.5, 0.5, 0.0, 1.0);
            gl_PointSize = 20.0;
        }`;

        const fragmentSource = `
        void main() {
            fragColor = vec4(1.0, 0.0, 0.0, 1.0);
        }`;

        const vertexShader = gl.createShader(gl.VERTEX_SHADER);
        gl.shaderSource(vertexShader, vertexSource);
        gl.compileShader(vertexShader);
        const fragmentShader = gl.createShader(gl.FRAGMENT_SHADER);
        gl.shaderSource(fragmentShader, fragmentSource);
        gl.compileShader(fragmentShader);

        this.program = gl.createProgram();
        gl.attachShader(this.program, vertexShader);
        gl.attachShader(this.program, fragmentShader);
        gl.linkProgram(this.program);
    }

    render(gl, matrix) {
        gl.useProgram(this.program);
        gl.uniformMatrix4fv(gl.getUniformLocation(this.program, "u_matrix"), false, matrix);
        gl.drawArrays(gl.POINTS, 0, 1);
    }
}

map.on('load', function() {
    map.addLayer(new NullIslandLayer());
});
```

## Table of contents

### Methods

- [onAdd](maplibregl.CustomLayerInterface.md#onadd)
- [onRemove](maplibregl.CustomLayerInterface.md#onremove)

### Properties

- [id](maplibregl.CustomLayerInterface.md#id)
- [prerender](maplibregl.CustomLayerInterface.md#prerender)
- [render](maplibregl.CustomLayerInterface.md#render)
- [renderingMode](maplibregl.CustomLayerInterface.md#renderingmode)
- [type](maplibregl.CustomLayerInterface.md#type)

## Methods

### onAdd

▸ `Optional` **onAdd**(`map`, `gl`): `void`

Optional method called when the layer has been added to the Map with [addLayer](../classes/maplibregl.Map.md#addlayer). This
gives the layer a chance to initialize gl resources and register event listeners.

**`Function`**

**`Memberof`**

CustomLayerInterface

**`Instance`**

**`Name`**

onAdd

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](../classes/maplibregl.Map.md) | The Map this custom layer was just added to. |
| `gl` | `WebGLRenderingContext` \| `WebGL2RenderingContext` | The gl context for the map. |

#### Returns

`void`

#### Defined in

[src/style/style_layer/custom_style_layer.ts:144](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L144)

___

### onRemove

▸ `Optional` **onRemove**(`map`, `gl`): `void`

Optional method called when the layer has been removed from the Map with [removeLayer](../classes/maplibregl.Map.md#removelayer). This
gives the layer a chance to clean up gl resources and event listeners.

**`Function`**

**`Memberof`**

CustomLayerInterface

**`Instance`**

**`Name`**

onRemove

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](../classes/maplibregl.Map.md) | The Map this custom layer was just added to. |
| `gl` | `WebGLRenderingContext` \| `WebGL2RenderingContext` | The gl context for the map. |

#### Returns

`void`

#### Defined in

[src/style/style_layer/custom_style_layer.ts:156](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L156)

## Properties

### id

• **id**: `string`

#### Defined in

[src/style/style_layer/custom_style_layer.ts:77](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L77)

___

### prerender

• `Optional` **prerender**: `CustomRenderMethod`

Optional method called during a render frame to allow a layer to prepare resources or render into a texture.

The layer cannot make any assumptions about the current GL state and must bind a framebuffer before rendering.

**`Function`**

**`Memberof`**

CustomLayerInterface

**`Instance`**

**`Name`**

prerender

**`Param`**

The map's gl context.

**`Param`**

The map's camera matrix. It projects spherical mercator
coordinates to gl coordinates. The mercator coordinate `[0, 0]` represents the
top left corner of the mercator world and `[1, 1]` represents the bottom right corner. When
the `renderingMode` is `"3d"`, the z coordinate is conformal. A box with identical x, y, and z
lengths in mercator units would be rendered as a cube. [MercatorCoordinate](../classes/maplibregl.MercatorCoordinate.md).fromLngLat
can be used to project a `LngLat` to a mercator coordinate.

#### Defined in

[src/style/style_layer/custom_style_layer.ts:132](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L132)

___

### render

• **render**: `CustomRenderMethod`

Called during a render frame allowing the layer to draw into the GL context.

The layer can assume blending and depth state is set to allow the layer to properly
blend and clip other layers. The layer cannot make any other assumptions about the
current GL state.

If the layer needs to render to a texture, it should implement the `prerender` method
to do this and only use the `render` method for drawing directly into the main framebuffer.

The blend function is set to `gl.blendFunc(gl.ONE, gl.ONE_MINUS_SRC_ALPHA)`. This expects
colors to be provided in premultiplied alpha form where the `r`, `g` and `b` values are already
multiplied by the `a` value. If you are unable to provide colors in premultiplied form you
may want to change the blend function to
`gl.blendFuncSeparate(gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA)`.

**`Function`**

**`Memberof`**

CustomLayerInterface

**`Instance`**

**`Name`**

render

**`Param`**

The map's gl context.

**`Param`**

The map's camera matrix. It projects spherical mercator
coordinates to gl coordinates. The spherical mercator coordinate `[0, 0]` represents the
top left corner of the mercator world and `[1, 1]` represents the bottom right corner. When
the `renderingMode` is `"3d"`, the z coordinate is conformal. A box with identical x, y, and z
lengths in mercator units would be rendered as a cube. [MercatorCoordinate](../classes/maplibregl.MercatorCoordinate.md).fromLngLat
can be used to project a `LngLat` to a mercator coordinate.

#### Defined in

[src/style/style_layer/custom_style_layer.ts:114](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L114)

___

### renderingMode

• `Optional` **renderingMode**: ``"2d"`` \| ``"3d"``

#### Defined in

[src/style/style_layer/custom_style_layer.ts:85](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L85)

___

### type

• **type**: ``"custom"``

#### Defined in

[src/style/style_layer/custom_style_layer.ts:81](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/style/style_layer/custom_style_layer.ts#L81)
