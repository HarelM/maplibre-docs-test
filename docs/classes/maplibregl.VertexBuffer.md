[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / VertexBuffer

# Class: VertexBuffer

[maplibregl](../modules/maplibregl.md).VertexBuffer

The `VertexBuffer` class turns a `StructArray` into a WebGL buffer. Each member of the StructArray's
Struct type is converted to a WebGL attribute.

## Table of contents

### Constructors

- [constructor](maplibregl.VertexBuffer.md#constructor)

### Methods

- [destroy](maplibregl.VertexBuffer.md#destroy)
- [setVertexAttribPointers](maplibregl.VertexBuffer.md#setvertexattribpointers)

## Constructors

### constructor

• `Private` **new VertexBuffer**(`context`, `array`, `attributes`, `dynamicDraw?`)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | `Context` | - |
| `array` | [`StructArray`](maplibregl.StructArray.md) | - |
| `attributes` | readonly `StructArrayMember`[] | - |
| `dynamicDraw?` | `boolean` | Whether this buffer will be repeatedly updated. |

#### Defined in

[src/gl/vertex_buffer.ts:42](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/gl/vertex_buffer.ts#L42)

## Methods

### destroy

▸ **destroy**(): `void`

Destroy the GL buffer bound to the given WebGL context

#### Returns

`void`

#### Defined in

[src/gl/vertex_buffer.ts:107](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/gl/vertex_buffer.ts#L107)

___

### setVertexAttribPointers

▸ **setVertexAttribPointers**(`gl`, `program`, `vertexOffset?`): `void`

Set the attribute pointers in a WebGL context

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `gl` | `WebGLRenderingContext` \| `WebGL2RenderingContext` | The WebGL context |
| `program` | `Program`<`any`\> | The active WebGL program |
| `vertexOffset?` | `number` | Index of the starting vertex of the segment |

#### Returns

`void`

#### Defined in

[src/gl/vertex_buffer.ts:86](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/gl/vertex_buffer.ts#L86)
