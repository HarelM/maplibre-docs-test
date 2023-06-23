[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / MapTouchEvent

# Class: MapTouchEvent

[maplibregl](../modules/maplibregl.md).MapTouchEvent

`MapTouchEvent` is the event type for touch-related map events.

## Hierarchy

- `Event`

  ↳ **`MapTouchEvent`**

## Implements

- `MapLibreEvent`<`TouchEvent`\>

## Table of contents

### Accessors

- [defaultPrevented](maplibregl.MapTouchEvent.md#defaultprevented)

### Constructors

- [constructor](maplibregl.MapTouchEvent.md#constructor)

### Methods

- [preventDefault](maplibregl.MapTouchEvent.md#preventdefault)

### Properties

- [lngLat](maplibregl.MapTouchEvent.md#lnglat)
- [lngLats](maplibregl.MapTouchEvent.md#lnglats)
- [originalEvent](maplibregl.MapTouchEvent.md#originalevent)
- [point](maplibregl.MapTouchEvent.md#point)
- [points](maplibregl.MapTouchEvent.md#points)
- [target](maplibregl.MapTouchEvent.md#target)
- [type](maplibregl.MapTouchEvent.md#type)

## Accessors

### defaultPrevented

• `get` **defaultPrevented**(): `boolean`

`true` if `preventDefault` has been called.

#### Returns

`boolean`

#### Defined in

[src/ui/events.ts:197](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L197)

## Constructors

### constructor

• `Private` **new MapTouchEvent**(`type`, `map`, `originalEvent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `type` | `string` |
| `map` | [`Map`](maplibregl.Map.md) |
| `originalEvent` | `TouchEvent` |

#### Overrides

Event.constructor

#### Defined in

[src/ui/events.ts:206](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L206)

## Methods

### preventDefault

▸ **preventDefault**(): `void`

Prevents subsequent default processing of the event by the map.

Calling this method will prevent the following default map behaviors:

  * On `touchstart` events, the behavior of [DragPanHandler](maplibregl.DragPanHandler.md)
  * On `touchstart` events, the behavior of TouchZoomRotateHandler

#### Returns

`void`

#### Defined in

[src/ui/events.ts:189](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L189)

## Properties

### lngLat

• **lngLat**: [`LngLat`](maplibregl.LngLat.md)

The geographic location on the map of the center of the touch event points.

#### Defined in

[src/ui/events.ts:160](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L160)

___

### lngLats

• **lngLats**: [`LngLat`](maplibregl.LngLat.md)[]

The geographical locations on the map corresponding to a
[touch event's `touches`](https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/touches) property.

#### Defined in

[src/ui/events.ts:178](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L178)

___

### originalEvent

• **originalEvent**: `TouchEvent`

The DOM event which caused the map event.

#### Implementation of

MapLibreEvent.originalEvent

#### Defined in

[src/ui/events.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L155)

___

### point

• **point**: `Point`

The pixel coordinates of the center of the touch event points, relative to the map and measured from the top left
corner.

#### Defined in

[src/ui/events.ts:166](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L166)

___

### points

• **points**: `Point`[]

The array of pixel coordinates corresponding to a
[touch event's `touches`](https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/touches) property.

#### Defined in

[src/ui/events.ts:172](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L172)

___

### target

• **target**: [`Map`](maplibregl.Map.md)

The `Map` object that fired the event.

#### Implementation of

MapLibreEvent.target

#### Defined in

[src/ui/events.ts:150](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L150)

___

### type

• **type**: ``"touchcancel"`` \| ``"touchend"`` \| ``"touchmove"`` \| ``"touchstart"``

The event type.

#### Implementation of

MapLibreEvent.type

#### Overrides

Event.type

#### Defined in

[src/ui/events.ts:145](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L145)
