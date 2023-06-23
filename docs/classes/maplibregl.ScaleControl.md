[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / ScaleControl

# Class: ScaleControl

[maplibregl](../modules/maplibregl.md).ScaleControl

A `ScaleControl` control displays the ratio of a distance on the map to the corresponding distance on the ground.

**`Implements`**

**`Param`**

**`Param`**

The maximum length of the scale control in pixels.

**`Param`**

Unit of the distance (`'imperial'`, `'metric'` or `'nautical'`).

**`Example`**

```ts
var scale = new maplibregl.ScaleControl({
    maxWidth: 80,
    unit: 'imperial'
});
map.addControl(scale);

scale.setUnit('metric');
```

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)

## Table of contents

### Methods

- [setUnit](maplibregl.ScaleControl.md#setunit)

## Methods

### setUnit

▸ **setUnit**(`unit`): `void`

Set the scale's unit of the distance

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `unit` | `Unit` | Unit of the distance (`'imperial'`, `'metric'` or `'nautical'`). |

#### Returns

`void`

#### Defined in

[src/ui/control/scale_control.ts:73](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/control/scale_control.ts#L73)
