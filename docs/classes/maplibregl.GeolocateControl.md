[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / GeolocateControl

# Class: GeolocateControl

[maplibregl](../modules/maplibregl.md).GeolocateControl

A `GeolocateControl` control provides a button that uses the browser's geolocation
API to locate the user on the map.

Not all browsers support geolocation,
and some users may disable the feature. Geolocation support for modern
browsers including Chrome requires sites to be served over HTTPS. If
geolocation support is not available, the GeolocateControl will show
as disabled.

The zoom level applied will depend on the accuracy of the geolocation provided by the device.

The GeolocateControl has two modes. If `trackUserLocation` is `false` (default) the control acts as a button, which when pressed will set the map's camera to target the user location. If the user moves, the map won't update. This is most suited for the desktop. If `trackUserLocation` is `true` the control acts as a toggle button that when active the user's location is actively monitored for changes. In this mode the GeolocateControl has three interaction states:
* active - the map's camera automatically updates as the user's location changes, keeping the location dot in the center. Initial state and upon clicking the `GeolocateControl` button.
* passive - the user's location dot automatically updates, but the map's camera does not. Occurs upon the user initiating a map movement.
* disabled - occurs if Geolocation is not available, disabled or denied.

These interaction states can't be controlled programmatically, rather they are set based on user interactions.

**`Implements`**

**`Param`**

**`Param`**

false, timeout: 6000}] A Geolocation API [PositionOptions](https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions) object.

**`Param`**

15}] A [fitBounds](maplibregl.Map.md#fitbounds) options object to use when the map is panned and zoomed to the user's location. The default is to use a `maxZoom` of 15 to limit how far the map will zoom in for very accurate locations.

**`Param`**

If `true` the Geolocate Control becomes a toggle button and when active the map will receive updates to the user's location as it changes.

**`Param`**

By default, if showUserLocation is `true`, a transparent circle will be drawn around the user location indicating the accuracy (95% confidence level) of the user's location. Set to `false` to disable. Always disabled when showUserLocation is `false`.

**`Param`**

By default a dot will be shown on the map at the user's location. Set to `false` to disable.

**`Example`**

```ts
map.addControl(new maplibregl.GeolocateControl({
    positionOptions: {
        enableHighAccuracy: true
    },
    trackUserLocation: true
}));
```

**`See`**

[Locate the user](https://maplibre.org/maplibre-gl-js-docs/example/locate-user/)

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`GeolocateControl`**

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)

## Table of contents

### Methods

- [\_isOutOfMapMaxBounds](maplibregl.GeolocateControl.md#_isoutofmapmaxbounds)
- [\_onSuccess](maplibregl.GeolocateControl.md#_onsuccess)
- [\_updateCamera](maplibregl.GeolocateControl.md#_updatecamera)
- [\_updateMarker](maplibregl.GeolocateControl.md#_updatemarker)
- [listens](maplibregl.GeolocateControl.md#listens)
- [off](maplibregl.GeolocateControl.md#off)
- [on](maplibregl.GeolocateControl.md#on)
- [once](maplibregl.GeolocateControl.md#once)
- [setEventedParent](maplibregl.GeolocateControl.md#seteventedparent)
- [trigger](maplibregl.GeolocateControl.md#trigger)

## Methods

### \_isOutOfMapMaxBounds

▸ `Private` **_isOutOfMapMaxBounds**(`position`): `boolean`

Check if the Geolocation API Position is outside the map's maxbounds.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `position` | `GeolocationPosition` | the Geolocation API Position |

#### Returns

`boolean`

Returns `true` if position is outside the map's maxbounds, otherwise returns `false`.

#### Defined in

[src/ui/control/geolocate_control.ts:131](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/geolocate_control.ts#L131)

___

### \_onSuccess

▸ `Private` **_onSuccess**(`position`): `void`

When the Geolocation API returns a new location, update the GeolocateControl.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `position` | `GeolocationPosition` | the Geolocation API Position |

#### Returns

`void`

#### Defined in

[src/ui/control/geolocate_control.ts:177](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/geolocate_control.ts#L177)

___

### \_updateCamera

▸ `Private` **_updateCamera**(`position`): `void`

Update the camera location to center on the current position

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `position` | `GeolocationPosition` | the Geolocation API Position |

#### Returns

`void`

#### Defined in

[src/ui/control/geolocate_control.ts:245](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/geolocate_control.ts#L245)

___

### \_updateMarker

▸ `Private` **_updateMarker**(`position?`): `void`

Update the user location dot Marker to the current position

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `position?` | `GeolocationPosition` | the Geolocation API Position |

#### Returns

`void`

#### Defined in

[src/ui/control/geolocate_control.ts:263](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/geolocate_control.ts#L263)

___

### listens

▸ `Private` **listens**(`type`): `any`

Returns a true if this instance of Evented or any forwardeed instances of Evented have a listener for the specified type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type |

#### Returns

`any`

`true` if there is at least one registered listener for specified event type, `false` otherwise

#### Inherited from

[Evented](maplibregl.Evented.md).[listens](maplibregl.Evented.md#listens)

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### off

▸ **off**(`type`, `listener`): [`GeolocateControl`](maplibregl.GeolocateControl.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`GeolocateControl`](maplibregl.GeolocateControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`GeolocateControl`](maplibregl.GeolocateControl.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`GeolocateControl`](maplibregl.GeolocateControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`GeolocateControl`](maplibregl.GeolocateControl.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`GeolocateControl`](maplibregl.GeolocateControl.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`GeolocateControl`](maplibregl.GeolocateControl.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`GeolocateControl`](maplibregl.GeolocateControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### trigger

▸ **trigger**(): `boolean`

Programmatically request and move the map to the user's location.

**`Example`**

```ts
// Initialize the geolocate control.
var geolocate = new maplibregl.GeolocateControl({
 positionOptions: {
   enableHighAccuracy: true
 },
 trackUserLocation: true
});
// Add the control to the map.
map.addControl(geolocate);
map.on('load', function() {
  geolocate.trigger();
});
```

#### Returns

`boolean`

Returns `false` if called before control was added to a map, otherwise returns `true`.

#### Defined in

[src/ui/control/geolocate_control.ts:425](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/geolocate_control.ts#L425)
