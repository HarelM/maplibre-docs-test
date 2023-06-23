[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / ProgramConfiguration

# Class: ProgramConfiguration

[maplibregl](../modules/maplibregl.md).ProgramConfiguration

ProgramConfiguration contains the logic for binding style layer properties and tile
layer feature data into GL program uniforms and vertex attributes.

Non-data-driven property values are bound to shader uniforms. Data-driven property
values are bound to vertex attributes. In order to support a uniform GLSL syntax over
both, [Mapbox GL Shaders](https://github.com/mapbox/mapbox-gl-shaders) defines a `#pragma`
abstraction, which ProgramConfiguration is responsible for implementing. At runtime,
it examines the attributes of a particular layer, combines this with fixed knowledge
about how layers of the particular type are implemented, and determines which uniforms
and vertex attributes will be required. It can then substitute the appropriate text
into the shader source code, create and link a program, and bind the uniforms and
vertex attributes in preparation for drawing.

When a vector tile is parsed, this same configuration information is used to
populate the attribute buffers needed for data-driven styling using the zoom
level and feature property data.
