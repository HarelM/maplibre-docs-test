[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / BoxZoomHandler

# Class: BoxZoomHandler

[maplibregl](../modules/maplibregl.md).BoxZoomHandler

The `BoxZoomHandler` allows the user to zoom the map to fit within a bounding box.
The bounding box is defined by clicking and holding `shift` while dragging the cursor.

## Implements

- `Handler`

## Table of contents

### Constructors

- [constructor](maplibregl.BoxZoomHandler.md#constructor)

### Methods

- [disable](maplibregl.BoxZoomHandler.md#disable)
- [enable](maplibregl.BoxZoomHandler.md#enable)
- [isActive](maplibregl.BoxZoomHandler.md#isactive)
- [isEnabled](maplibregl.BoxZoomHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new BoxZoomHandler**(`map`, `options`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `map` | [`Map`](maplibregl.Map.md) |
| `options` | `Object` |
| `options.clickTolerance` | `number` |

#### Defined in

[src/ui/handler/box_zoom.ts:29](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/box_zoom.ts#L29)

## Methods

### disable

▸ **disable**(): `void`

Disables the "box zoom" interaction.

**`Example`**

```ts
map.boxZoom.disable();
```

#### Returns

`void`

#### Implementation of

Handler.disable

#### Defined in

[src/ui/handler/box_zoom.ts:74](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/box_zoom.ts#L74)

___

### enable

▸ **enable**(): `void`

Enables the "box zoom" interaction.

**`Example`**

```ts
map.boxZoom.enable();
```

#### Returns

`void`

#### Implementation of

Handler.enable

#### Defined in

[src/ui/handler/box_zoom.ts:63](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/box_zoom.ts#L63)

___

### isActive

▸ **isActive**(): `boolean`

Returns a Boolean indicating whether the "box zoom" interaction is active, i.e. currently being used.

#### Returns

`boolean`

`true` if the "box zoom" interaction is active.

#### Implementation of

Handler.isActive

#### Defined in

[src/ui/handler/box_zoom.ts:53](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/box_zoom.ts#L53)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "box zoom" interaction is enabled.

#### Returns

`boolean`

`true` if the "box zoom" interaction is enabled.

#### Implementation of

Handler.isEnabled

#### Defined in

[src/ui/handler/box_zoom.ts:44](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/box_zoom.ts#L44)
