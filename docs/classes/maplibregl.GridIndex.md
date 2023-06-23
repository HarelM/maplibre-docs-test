[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / GridIndex

# Class: GridIndex<T\>

[maplibregl](../modules/maplibregl.md).GridIndex

GridIndex is a data structure for testing the intersection of
circles and rectangles in a 2d plane.
It is optimized for rapid insertion and querying.
GridIndex splits the plane into a set of "cells" and keeps track
of which geometries intersect with each cell. At query time,
full geometry comparisons are only done for items that share
at least one cell. As long as the geometries are relatively
uniformly distributed across the plane, this greatly reduces
the number of comparisons necessary.

## Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends `GridKey` |
