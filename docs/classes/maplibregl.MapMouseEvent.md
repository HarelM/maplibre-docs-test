[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / MapMouseEvent

# Class: MapMouseEvent

[maplibregl](../modules/maplibregl.md).MapMouseEvent

`MapMouseEvent` is the event type for mouse-related map events.

**`Example`**

```ts
// The `click` event is an example of a `MapMouseEvent`.
// Set up an event listener on the map.
map.on('click', function(e) {
  // The event object (e) contains information like the
  // coordinates of the point on the map that was clicked.
  console.log('A click event has occurred at ' + e.lngLat);
});
```

## Hierarchy

- `Event`

  ↳ **`MapMouseEvent`**

## Implements

- `MapLibreEvent`<`MouseEvent`\>

## Table of contents

### Accessors

- [defaultPrevented](maplibregl.MapMouseEvent.md#defaultprevented)

### Constructors

- [constructor](maplibregl.MapMouseEvent.md#constructor)

### Methods

- [preventDefault](maplibregl.MapMouseEvent.md#preventdefault)

### Properties

- [lngLat](maplibregl.MapMouseEvent.md#lnglat)
- [originalEvent](maplibregl.MapMouseEvent.md#originalevent)
- [point](maplibregl.MapMouseEvent.md#point)
- [target](maplibregl.MapMouseEvent.md#target)
- [type](maplibregl.MapMouseEvent.md#type)

## Accessors

### defaultPrevented

• `get` **defaultPrevented**(): `boolean`

`true` if `preventDefault` has been called.

#### Returns

`boolean`

#### Defined in

[src/ui/events.ts:119](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L119)

## Constructors

### constructor

• `Private` **new MapMouseEvent**(`type`, `map`, `originalEvent`, `data?`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `type` | `string` |
| `map` | [`Map`](maplibregl.Map.md) |
| `originalEvent` | `MouseEvent` |
| `data` | `any` |

#### Overrides

Event.constructor

#### Defined in

[src/ui/events.ts:128](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L128)

## Methods

### preventDefault

▸ **preventDefault**(): `void`

Prevents subsequent default processing of the event by the map.

Calling this method will prevent the following default map behaviors:

  * On `mousedown` events, the behavior of [DragPanHandler](maplibregl.DragPanHandler.md)
  * On `mousedown` events, the behavior of [DragRotateHandler](maplibregl.DragRotateHandler.md)
  * On `mousedown` events, the behavior of [BoxZoomHandler](maplibregl.BoxZoomHandler.md)
  * On `dblclick` events, the behavior of [DoubleClickZoomHandler](maplibregl.DoubleClickZoomHandler.md)

#### Returns

`void`

#### Defined in

[src/ui/events.ts:111](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L111)

## Properties

### lngLat

• **lngLat**: [`LngLat`](maplibregl.LngLat.md)

The geographic location on the map of the mouse cursor.

#### Defined in

[src/ui/events.ts:98](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L98)

___

### originalEvent

• **originalEvent**: `MouseEvent`

The DOM event which caused the map event.

#### Implementation of

MapLibreEvent.originalEvent

#### Defined in

[src/ui/events.ts:88](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L88)

___

### point

• **point**: `Point`

The pixel coordinates of the mouse cursor, relative to the map and measured from the top left corner.

#### Defined in

[src/ui/events.ts:93](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L93)

___

### target

• **target**: [`Map`](maplibregl.Map.md)

The `Map` object that fired the event.

#### Implementation of

MapLibreEvent.target

#### Defined in

[src/ui/events.ts:83](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L83)

___

### type

• **type**: ``"click"`` \| ``"contextmenu"`` \| ``"dblclick"`` \| ``"mousedown"`` \| ``"mouseenter"`` \| ``"mouseleave"`` \| ``"mousemove"`` \| ``"mouseout"`` \| ``"mouseover"`` \| ``"mouseup"``

The event type (one of Map.event:mousedown,
Map.event:mouseup,
Map.event:click,
Map.event:dblclick,
Map.event:mousemove,
Map.event:mouseover,
Map.event:mouseenter,
Map.event:mouseleave,
Map.event:mouseout,
Map.event:contextmenu).

#### Implementation of

MapLibreEvent.type

#### Overrides

Event.type

#### Defined in

[src/ui/events.ts:78](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L78)
