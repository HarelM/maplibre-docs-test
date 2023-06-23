[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / ScrollZoomHandler

# Class: ScrollZoomHandler

[maplibregl](../modules/maplibregl.md).ScrollZoomHandler

The `ScrollZoomHandler` allows the user to zoom the map by scrolling.

## Implements

- `Handler`

## Table of contents

### Constructors

- [constructor](maplibregl.ScrollZoomHandler.md#constructor)

### Methods

- [disable](maplibregl.ScrollZoomHandler.md#disable)
- [enable](maplibregl.ScrollZoomHandler.md#enable)
- [isEnabled](maplibregl.ScrollZoomHandler.md#isenabled)
- [setWheelZoomRate](maplibregl.ScrollZoomHandler.md#setwheelzoomrate)
- [setZoomRate](maplibregl.ScrollZoomHandler.md#setzoomrate)

## Constructors

### constructor

• `Private` **new ScrollZoomHandler**(`map`, `triggerRenderFrame`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `map` | [`Map`](maplibregl.Map.md) |
| `triggerRenderFrame` | () => `void` |

#### Defined in

[src/ui/handler/scroll_zoom.ts:66](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L66)

## Methods

### disable

▸ **disable**(): `void`

Disables the "scroll to zoom" interaction.

**`Example`**

```ts
map.scrollZoom.disable();
```

#### Returns

`void`

#### Implementation of

Handler.disable

#### Defined in

[src/ui/handler/scroll_zoom.ts:145](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L145)

___

### enable

▸ **enable**(`options?`): `void`

Enables the "scroll to zoom" interaction.

**`Example`**

```ts
map.scrollZoom.enable();
```

**`Example`**

```ts
map.scrollZoom.enable({ around: 'center' })
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `boolean` \| `AroundCenterOptions` | Options object. |

#### Returns

`void`

#### Implementation of

Handler.enable

#### Defined in

[src/ui/handler/scroll_zoom.ts:133](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L133)

___

### isEnabled

▸ **isEnabled**(): `boolean`

Returns a Boolean indicating whether the "scroll to zoom" interaction is enabled.

#### Returns

`boolean`

`true` if the "scroll to zoom" interaction is enabled.

#### Implementation of

Handler.isEnabled

#### Defined in

[src/ui/handler/scroll_zoom.ts:105](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L105)

___

### setWheelZoomRate

▸ **setWheelZoomRate**(`wheelZoomRate?`): `void`

Set the zoom rate of a mouse wheel

**`Example`**

```ts
// Slow down zoom of mouse wheel
map.scrollZoom.setWheelZoomRate(1/600);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `wheelZoomRate?` | `number` | The rate used to scale mouse wheel movement to a zoom value. |

#### Returns

`void`

#### Defined in

[src/ui/handler/scroll_zoom.ts:96](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L96)

___

### setZoomRate

▸ **setZoomRate**(`zoomRate?`): `void`

Set the zoom rate of a trackpad

**`Example`**

```ts
// Speed up trackpad zoom
map.scrollZoom.setZoomRate(1/25);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `zoomRate?` | `number` | The rate used to scale trackpad movement to a zoom value. |

#### Returns

`void`

#### Defined in

[src/ui/handler/scroll_zoom.ts:85](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/handler/scroll_zoom.ts#L85)
