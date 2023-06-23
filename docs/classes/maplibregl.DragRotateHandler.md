[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / DragRotateHandler

# Class: DragRotateHandler

[maplibregl](../modules/maplibregl.md).DragRotateHandler

The `DragRotateHandler` allows the user to rotate the map by clicking and
dragging the cursor while holding the right mouse button or `ctrl` key.

## Table of contents

### Constructors

- [constructor](maplibregl.DragRotateHandler.md#constructor)

### Methods

- [disable](maplibregl.DragRotateHandler.md#disable)
- [enable](maplibregl.DragRotateHandler.md#enable)
- [isActive](maplibregl.DragRotateHandler.md#isactive)
- [isEnabled](maplibregl.DragRotateHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new DragRotateHandler**(`options?`, `mouseRotate`, `mousePitch`)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` |  |
| `options.pitchWithRotate` | `boolean` | Control the map pitch in addition to the bearing |
| `mouseRotate` | `MouseRotateHandler` | - |
| `mousePitch` | `MousePitchHandler` | - |

#### Defined in

[src/ui/handler/shim/drag_rotate.ts:20](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_rotate.ts#L20)

## Methods

### disable

▸ **disable**(): `void`

Disables the "drag to rotate" interaction.

**`Example`**

```ts
map.dragRotate.disable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/drag_rotate.ts:45](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_rotate.ts#L45)

___

### enable

▸ **enable**(): `void`

Enables the "drag to rotate" interaction.

**`Example`**

```ts
map.dragRotate.enable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/drag_rotate.ts:34](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_rotate.ts#L34)

___

### isActive

▸ **isActive**(): `boolean`

Returns a Boolean indicating whether the "drag to rotate" interaction is active, i.e. currently being used.

#### Returns

`boolean`

`true` if the "drag to rotate" interaction is active.

#### Defined in

[src/ui/handler/shim/drag_rotate.ts:64](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_rotate.ts#L64)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "drag to rotate" interaction is enabled.

#### Returns

`boolean`

`true` if the "drag to rotate" interaction is enabled.

#### Defined in

[src/ui/handler/shim/drag_rotate.ts:55](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_rotate.ts#L55)
