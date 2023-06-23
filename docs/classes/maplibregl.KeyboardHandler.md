[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / KeyboardHandler

# Class: KeyboardHandler

[maplibregl](../modules/maplibregl.md).KeyboardHandler

The `KeyboardHandler` allows the user to zoom, rotate, and pan the map using
the following keyboard shortcuts:

- `=` / `+`: Increase the zoom level by 1.
- `Shift-=` / `Shift-+`: Increase the zoom level by 2.
- `-`: Decrease the zoom level by 1.
- `Shift--`: Decrease the zoom level by 2.
- Arrow keys: Pan by 100 pixels.
- `Shift+⇢`: Increase the rotation by 15 degrees.
- `Shift+⇠`: Decrease the rotation by 15 degrees.
- `Shift+⇡`: Increase the pitch by 10 degrees.
- `Shift+⇣`: Decrease the pitch by 10 degrees.

## Implements

- `Handler`

## Table of contents

### Constructors

- [constructor](maplibregl.KeyboardHandler.md#constructor)

### Methods

- [disable](maplibregl.KeyboardHandler.md#disable)
- [disableRotation](maplibregl.KeyboardHandler.md#disablerotation)
- [enable](maplibregl.KeyboardHandler.md#enable)
- [enableRotation](maplibregl.KeyboardHandler.md#enablerotation)
- [isActive](maplibregl.KeyboardHandler.md#isactive)
- [isEnabled](maplibregl.KeyboardHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new KeyboardHandler**(`map`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `map` | [`Map`](maplibregl.Map.md) |

#### Defined in

[src/ui/handler/keyboard.ts:37](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L37)

## Methods

### disable

▸ **disable**(): `void`

Disables the "keyboard rotate and zoom" interaction.

**`Example`**

```ts
map.keyboard.disable();
```

#### Returns

`void`

#### Implementation of

Handler.disable

#### Defined in

[src/ui/handler/keyboard.ts:152](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L152)

___

### disableRotation

▸ **disableRotation**(): `void`

Disables the "keyboard pan/rotate" interaction, leaving the
"keyboard zoom" interaction enabled.

**`Example`**

```ts
map.keyboard.disableRotation();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/keyboard.ts:186](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L186)

___

### enable

▸ **enable**(): `void`

Enables the "keyboard rotate and zoom" interaction.

**`Example`**

```ts
map.keyboard.enable();
```

#### Returns

`void`

#### Implementation of

Handler.enable

#### Defined in

[src/ui/handler/keyboard.ts:142](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L142)

___

### enableRotation

▸ **enableRotation**(): `void`

Enables the "keyboard pan/rotate" interaction.

**`Example`**

```ts
map.keyboard.enable();
  map.keyboard.enableRotation();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/keyboard.ts:197](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L197)

___

### isActive

▸ **isActive**(): `boolean`

Returns true if the handler is enabled and has detected the start of a
zoom/rotate gesture.

#### Returns

`boolean`

`true` if the handler is enabled and has detected the
start of a zoom/rotate gesture.

#### Implementation of

Handler.isActive

#### Defined in

[src/ui/handler/keyboard.ts:175](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L175)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "keyboard rotate and zoom"
interaction is enabled.

#### Returns

`boolean`

`true` if the "keyboard rotate and zoom"
interaction is enabled.

#### Implementation of

Handler.isEnabled

#### Defined in

[src/ui/handler/keyboard.ts:164](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/keyboard.ts#L164)
