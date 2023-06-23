[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / IControl

# Interface: IControl

[maplibregl](../modules/maplibregl.md).IControl

Interface for interactive controls added to the map. This is a
specification for implementers to model: it is not
an exported method or class.

Controls must implement `onAdd` and `onRemove`, and must own an
element, which is often a `div` element. To use MapLibre GL JS's
default control styling, add the `maplibregl-ctrl` class to your control's
node.

 IControl

**`Example`**

```ts
// Control implemented as ES6 class
class HelloWorldControl {
    onAdd(map) {
        this._map = map;
        this._container = document.createElement('div');
        this._container.className = 'maplibregl-ctrl';
        this._container.textContent = 'Hello, world';
        return this._container;
    }

    onRemove() {
        this._container.parentNode.removeChild(this._container);
        this._map = undefined;
    }
}

// Control implemented as ES5 prototypical class
function HelloWorldControl() { }

HelloWorldControl.prototype.onAdd = function(map) {
    this._map = map;
    this._container = document.createElement('div');
    this._container.className = 'maplibregl-ctrl';
    this._container.textContent = 'Hello, world';
    return this._container;
};

HelloWorldControl.prototype.onRemove = function () {
     this._container.parentNode.removeChild(this._container);
     this._map = undefined;
};
```

## Implemented by

- [`AttributionControl`](../classes/maplibregl.AttributionControl.md)
- [`FullscreenControl`](../classes/maplibregl.FullscreenControl.md)
- [`GeolocateControl`](../classes/maplibregl.GeolocateControl.md)
- [`LogoControl`](../classes/maplibregl.LogoControl.md)
- [`NavigationControl`](../classes/maplibregl.NavigationControl.md)
- [`ScaleControl`](../classes/maplibregl.ScaleControl.md)
- [`TerrainControl`](../classes/maplibregl.TerrainControl.md)

## Table of contents

### Methods

- [onAdd](maplibregl.IControl.md#onadd)
- [onRemove](maplibregl.IControl.md#onremove)

### Properties

- [getDefaultPosition](maplibregl.IControl.md#getdefaultposition)

## Methods

### onAdd

▸ **onAdd**(`map`): `HTMLElement`

Register a control on the map and give it a chance to register event listeners
and resources. This method is called by [addControl](../classes/maplibregl.Map.md#addcontrol)
internally.

**`Function`**

**`Memberof`**

IControl

**`Instance`**

**`Name`**

onAdd

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](../classes/maplibregl.Map.md) | the Map this control will be added to |

#### Returns

`HTMLElement`

The control's container element. This should
be created by the control and returned by onAdd without being attached
to the DOM: the map will insert the control's element into the DOM
as necessary.

#### Defined in

[src/ui/control/control.ts:63](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/control.ts#L63)

___

### onRemove

▸ **onRemove**(`map`): `void`

Unregister a control on the map and give it a chance to detach event listeners
and resources. This method is called by [removeControl](../classes/maplibregl.Map.md#removecontrol)
internally.

**`Function`**

**`Memberof`**

IControl

**`Instance`**

**`Name`**

onRemove

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](../classes/maplibregl.Map.md) | the Map this control will be removed from |

#### Returns

`void`

there is no required return value for this method

#### Defined in

[src/ui/control/control.ts:76](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/control.ts#L76)

## Properties

### getDefaultPosition

• `Optional` `Readonly` **getDefaultPosition**: () => `ControlPosition`

#### Type declaration

▸ (): `ControlPosition`

Optionally provide a default position for this control. If this method
is implemented and [addControl](../classes/maplibregl.Map.md#addcontrol) is called without the `position`
parameter, the value returned by getDefaultPosition will be used as the
control's position.

**`Function`**

**`Memberof`**

IControl

**`Instance`**

**`Name`**

getDefaultPosition

##### Returns

`ControlPosition`

a control position, one of the values valid in addControl.

#### Defined in

[src/ui/control/control.ts:89](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/control.ts#L89)
