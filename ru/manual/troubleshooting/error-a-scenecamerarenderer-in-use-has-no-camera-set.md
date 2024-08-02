# Ошибка: "A SceneCameraRenderer in use has no camera assigned to its [Slot]. Make sure a camera is enabled and assigned to the [Slot]."

>[!Примечание]
>В более ранних версиях Stride сообщение об ошибке выглядело так:"A SceneCameraRenderer in use has no camera set. Make sure the camera component to use is enabled and has its [Slot] property correctly set."

Эта ошибка означает, что нет камеры, доступной для использования рендерером сцены. Это может иметь несколько возможных причин:

* нет включенной [камеры](../graphics/cameras/index.md)
* камера установлена ​​в неправильном [слоте камеры](../graphics/cameras/camera-slots.md)
* несколько включенных камер назначены на один и тот же слот камеры

## Исправление

Если вы создаете компоненты камеры в Game Studio, убедитесь, что:

* слоты камеры установлены в слот **Main**  (см. [Графика — Слоты для камер](../graphics/cameras/camera-slots.md))
* включена только начальная камера

Если вы создаете компоненты камеры в коде, убедитесь, что вы извлекаете правильный слот из графического компоновщика. Используйте:

```cs
var camera = new CameraComponent();
camera.Slot = SceneSystem.GraphicsCompositor.Cameras[0].ToSlotId();
```

Чтобы изменить камеру во время выполнения, переключите свойство ``Enabled`` .

> [!Примечание]
> Убедитесь, что вы:
>
> * всегда имеете хотя бы одну включенную камеру
>
> * не включайте и не назначайте одновременно несколько камер одному и тому же слоту

## Смотрите также

* [Графика — Слоты для камер](../graphics/cameras/camera-slots.md)
* [Графика — Камеры](../graphics/cameras/index.md)