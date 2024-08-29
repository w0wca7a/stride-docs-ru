# Материалы частиц

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Художник</span>
<span class="badge text-bg-success">Программист</span>

**Материалы** определяют, как должна отображаться развернутая форма. Они определяют цвет, текстуру и другие параметры.

**Материалы частиц** являются упрощенной версией [материалов, используемых для моделей](../graphics/materials/index.md). В настоящее время существует только один тип материала — динамический эмиссионный материал.

## Динамический эмиссионный материал

Этот материал использует полупрозрачный эмиссионный цвет RGBA for the pixel shading. In HDR rendering mode, the values are used as intensity, and can be higher than 1.

![media/particles-reference-materials-1.png](media/particles-reference-materials-1.png)

| Property            | Description  
|---------------------|------------
| Alpha-Add           | Translucent rendering supports alpha-blending, additive blending or anything in-between. With this parameter you can control how much alpha-blended (0) or additive (1) the particles should be.
| Culling             | There are options for no culling, front face culling and back face culling. Camera-facing particles always have their front face towards the camera.
| Emissive            | The emissive RGBA color for the particle. See [Material maps](../graphics/materials/material-maps.md) for a full description.
| UV coords           | For particles which use texture sampling uv coordinates animation can be specified. The two currently existing types are specified below.
### UV Coords — Flipbook

The flipbook animation considers a texture a sequence of frames and displays it one frame at a time, like a flipbook.

This image is an example of a 4x4 flipbook animation texture of an explosion:

![media/particles-reference-materials-4.png](media/particles-reference-materials-4.png)

The flipbook animation has the following properties:

![media/particles-reference-materials-2.png](media/particles-reference-materials-2.png)

| Property            | Description    
|---------------------|------------
| X divisions         | The number of columns to split the texture into
| Y divisions         | The number of rows to split the texture into
| Starting frame      | The frame to start the animation at. The top-left frame is 0 and increases by 1 from left to right before moving down.
| Animation speed     | The total number of frames to show over the particle lifetime. If Speed = X x Y, then the animation shows **all** frames over the particle lifetime. The speed is relative; particles with longer lifespans have slower animation. 

### UV Coords — Scrolling

The scrolling animation defines a starting rectangle for the billboard or quad, which moves across the texture to its end position. This creates a scrolling or a scaling effect of the texture across the quad's surface.

The texture coordinates can go below 0 or above 1. How the texture is sampled depends on the addressing mode defined in the [material maps](../graphics/materials/material-maps.md). For more information, see the [MSDN documentation](http://tinyurl.com/TextureAddressingModes).

The scrolling animation has the following properties:

![media/particles-reference-materials-3.png](media/particles-reference-materials-3.png)

| Property            | Description
|---------------------|-------------
| Start frame         | The initial rectangle for texture sampling when the particle first spawns
| End frame           | The last rectangle for texture sampling when the particle disappears

## Смотрите также

* [Создание частиц](create-particles.md)
* [Излучатели (Emitters)](emitters.md)
* [Формы](shapes.md)
* [Спаунеры (Spawners)](spawners.md)
* [Инициализаторы](initializers.md)
* [Апдейтеры (Updaters)](updaters.md)