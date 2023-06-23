[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / DragPanHandler

# Class: DragPanHandler

[maplibregl](../modules/maplibregl.md).DragPanHandler

The `DragPanHandler` allows the user to pan the map by clicking and dragging
the cursor.

## Table of contents

### Constructors

- [constructor](maplibregl.DragPanHandler.md#constructor)

### Methods

- [disable](maplibregl.DragPanHandler.md#disable)
- [enable](maplibregl.DragPanHandler.md#enable)
- [isActive](maplibregl.DragPanHandler.md#isactive)
- [isEnabled](maplibregl.DragPanHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new DragPanHandler**(`el`, `mousePan`, `touchPan`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `el` | `HTMLElement` |
| `mousePan` | `MousePanHandler` |
| `touchPan` | `TouchPanHandler` |

#### Defined in

[src/ui/handler/shim/drag_pan.ts:25](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_pan.ts#L25)

## Methods

### disable

▸ **disable**(): `void`

Disables the "drag to pan" interaction.

**`Example`**

```ts
map.dragPan.disable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/drag_pan.ts:63](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_pan.ts#L63)

___

### enable

▸ **enable**(`options?`): `void`

Enables the "drag to pan" interaction.

**`Example`**

```ts
map.dragPan.enable();
```

**`Example`**

```ts
map.dragPan.enable({
     linearity: 0.3,
     easing: bezier(0, 0, 0.3, 1),
     maxSpeed: 1400,
     deceleration: 2500,
  });
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `boolean` \| `DragPanOptions` | Options object |

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/drag_pan.ts:50](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_pan.ts#L50)

___

### isActive

▸ **isActive**(): `boolean`

Returns a Boolean indicating whether the "drag to pan" interaction is active, i.e. currently being used.

#### Returns

`boolean`

`true` if the "drag to pan" interaction is active.

#### Defined in

[src/ui/handler/shim/drag_pan.ts:83](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_pan.ts#L83)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "drag to pan" interaction is enabled.

#### Returns

`boolean`

`true` if the "drag to pan" interaction is enabled.

#### Defined in

[src/ui/handler/shim/drag_pan.ts:74](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/drag_pan.ts#L74)
