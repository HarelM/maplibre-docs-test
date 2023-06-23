[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TwoFingersTouchZoomRotateHandler

# Class: TwoFingersTouchZoomRotateHandler

[maplibregl](../modules/maplibregl.md).TwoFingersTouchZoomRotateHandler

The `TwoFingersTouchZoomRotateHandler` allows the user to zoom and rotate the map by
pinching on a touchscreen.

They can zoom with one finger by double tapping and dragging. On the second tap,
hold the finger down and drag up or down to zoom in or out.

## Table of contents

### Constructors

- [constructor](maplibregl.TwoFingersTouchZoomRotateHandler.md#constructor)

### Methods

- [disable](maplibregl.TwoFingersTouchZoomRotateHandler.md#disable)
- [disableRotation](maplibregl.TwoFingersTouchZoomRotateHandler.md#disablerotation)
- [enable](maplibregl.TwoFingersTouchZoomRotateHandler.md#enable)
- [enableRotation](maplibregl.TwoFingersTouchZoomRotateHandler.md#enablerotation)
- [isActive](maplibregl.TwoFingersTouchZoomRotateHandler.md#isactive)
- [isEnabled](maplibregl.TwoFingersTouchZoomRotateHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new TwoFingersTouchZoomRotateHandler**(`el`, `touchZoom`, `touchRotate`, `tapDragZoom`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `el` | `HTMLElement` |
| `touchZoom` | `TwoFingersTouchZoomHandler` |
| `touchRotate` | `TwoFingersTouchRotateHandler` |
| `tapDragZoom` | `TapDragZoomHandler` |

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:23](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L23)

## Methods

### disable

▸ **disable**(): `void`

Disables the "pinch to rotate and zoom" interaction.

**`Example`**

```ts
map.touchZoomRotate.disable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:56](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L56)

___

### disableRotation

▸ **disableRotation**(): `void`

Disables the "pinch to rotate" interaction, leaving the "pinch to zoom"
interaction enabled.

**`Example`**

```ts
map.touchZoomRotate.disableRotation();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:90](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L90)

___

### enable

▸ **enable**(`options?`): `void`

Enables the "pinch to rotate and zoom" interaction.

**`Example`**

```ts
map.touchZoomRotate.enable();
```

**`Example`**

```ts
map.touchZoomRotate.enable({ around: 'center' });
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `boolean` \| `AroundCenterOptions` | Options object. |

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:43](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L43)

___

### enableRotation

▸ **enableRotation**(): `void`

Enables the "pinch to rotate" interaction.

**`Example`**

```ts
map.touchZoomRotate.enable();
  map.touchZoomRotate.enableRotation();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:102](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L102)

___

### isActive

▸ **isActive**(): `boolean`

Returns true if the handler is enabled and has detected the start of a zoom/rotate gesture.

#### Returns

`boolean`

//eslint-disable-line

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L79)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "pinch to rotate and zoom" interaction is enabled.

#### Returns

`boolean`

`true` if the "pinch to rotate and zoom" interaction is enabled.

#### Defined in

[src/ui/handler/shim/two_fingers_touch.ts:68](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/two_fingers_touch.ts#L68)
