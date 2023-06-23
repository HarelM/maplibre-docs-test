[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / DoubleClickZoomHandler

# Class: DoubleClickZoomHandler

[maplibregl](../modules/maplibregl.md).DoubleClickZoomHandler

The `DoubleClickZoomHandler` allows the user to zoom the map at a point by
double clicking or double tapping.

## Table of contents

### Constructors

- [constructor](maplibregl.DoubleClickZoomHandler.md#constructor)

### Methods

- [disable](maplibregl.DoubleClickZoomHandler.md#disable)
- [enable](maplibregl.DoubleClickZoomHandler.md#enable)
- [isActive](maplibregl.DoubleClickZoomHandler.md#isactive)
- [isEnabled](maplibregl.DoubleClickZoomHandler.md#isenabled)

## Constructors

### constructor

• `Private` **new DoubleClickZoomHandler**(`clickZoom`, `TapZoom`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `clickZoom` | `ClickZoomHandler` |
| `TapZoom` | `TapZoomHandler` |

#### Defined in

[src/ui/handler/shim/dblclick_zoom.ts:16](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/dblclick_zoom.ts#L16)

## Methods

### disable

▸ **disable**(): `void`

Disables the "double click to zoom" interaction.

**`Example`**

```ts
map.doubleClickZoom.disable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/dblclick_zoom.ts:38](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/dblclick_zoom.ts#L38)

___

### enable

▸ **enable**(): `void`

Enables the "double click to zoom" interaction.

**`Example`**

```ts
map.doubleClickZoom.enable();
```

#### Returns

`void`

#### Defined in

[src/ui/handler/shim/dblclick_zoom.ts:27](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/dblclick_zoom.ts#L27)

___

### isActive

▸ **isActive**(): `boolean`

Returns a Boolean indicating whether the "double click to zoom" interaction is active, i.e. currently being used.

#### Returns

`boolean`

`true` if the "double click to zoom" interaction is active.

#### Defined in

[src/ui/handler/shim/dblclick_zoom.ts:57](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/dblclick_zoom.ts#L57)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "double click to zoom" interaction is enabled.

#### Returns

`boolean`

`true` if the "double click to zoom" interaction is enabled.

#### Defined in

[src/ui/handler/shim/dblclick_zoom.ts:48](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/shim/dblclick_zoom.ts#L48)
