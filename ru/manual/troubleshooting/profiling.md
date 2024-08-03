# Профилирование

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Программист</span>

Вы можете **профилировать** свой проект, чтобы проверить его производительность во время выполнения и найти проблемы. Используйте скрипт Stride **Game Profiler** или внешний инструмент профилирования, например Performance Profiler в Visual Studio.

![Профилирование](media/profiling.png)

## Профилирование с помощью скрипта Stride **Game Profiler**

Скрипт **Game Profiler** показывает, как изменяются показатели производительности во время выполнения. Это помогает выявить узкие места и найти их причину.

![Профилировщик во время выполнения](media/profiling-profiler-at-runtime.jpg)

Чтобы использовать скрипт:

1. In the **Asset View**, click ![Add new asset button](media/profiling-add-new-asset-button.png) and select **Scripts > Game Profiler**.

    ![Добавить скрипт Game Profiler](media/profiling-add-game-profiler-script.png)

2. Откроется **Диалоговое окно Новый скрипт**. Оставьте информацию по умолчанию и нажмите **Создать скрипт**.

    ![Новый скрипт](media/create-profiler-script.png)

    Game Studio adds the GameProfiler script to your project.

3. Add the script to an entity. For instructions, see [Use scripts](../scripts/use-a-script.md).

4. Select the entity that contains the **GameProfiler**.

5. In the **Property Grid** (on the right by default), enable the **Game Profiler** component.

    ![Enable component](media/enable-profiler-component.png)

    >[!Tip]
    >You can also enable and disable the profiler at runtime with **Left Ctrl + Left Shift + P**.

6. Run the game.

    The Game Profiler shows profiling results as your game runs.

    >[!Note]
    >Game Profiler disables VSync. This gives you the true profiling values, ignoring sync time.

### Game Profiler properties

To change the Game Profiler properties, select the **GameProfiler** entity and use the **Property Grid**.

![Profiler properties](media/profiler-properties.png)

| Property | Description
| -------- | --------
| Filter | The kind of information the profiler displays (FPS only, CPU, or GPU). At runtime, change with **F1**.
| Sort by | Sort the result pages by: <br><p>**Name**: the profile key (the thing being profiled) <br><p>**Time**: the key that uses the most time <br><p>At runtime, toggle with **F2**.
| Refresh interval (ms) | How frequently the profiler gets and displays new results. At runtime, control with **- / +**.
| Display page | The results page displayed. At runtime, jump to a page with the **number keys**, or move forward and backwards with **F3** and **F4**.
| Text color | The color of the profiler text
| Priority | See [Scheduling and priorities](../scripts/scheduling-and-priorities.md)

### Understanding the Game Profiler results

The top row displays information about basic performance.

![FPS profiling](media/fps-profiling.png)

* `Displaying`: the kind of information the profiler displays (FPS only, CPU, or GPU)
* `Frame`: the current frame
* `Update`: the average time (ms) taken to update the game since the profiler last refreshed
* `Draw`: the average time (ms) taken to render the frame since the profiler last refreshed
* `FPS`: the average number of frames rendered per second

If you select **CPU** as the display mode, the profiler displays:

![CPU profiling](media/fps-cpu.png)

* `Total`: the amount of memory currently used
* `Peak`: the peak memory use since the game started
* `Allocations`: the amount of memory allocated or freed since the profiler last refreshed
* `Gen0`, `Gen1`, `Gen1`: the number of garbage collections per each generation of object (`Gen0` is the most recent generation)

If you select **GPU** as the display mode, the profiler displays:

![GPU profiling](media/fps-gpu.png)

* `Device`: the graphics device (manufacturer's description)
* `Platform`: the currently used backend (eg DirectX, OpenGL, Vulkan, etc)
* `Profile`: the feature level for your game, set in **Game Settings > Rendering** (see [Game settings](../game-studio/game-settings.md))
* `Resolution`: the game resolution
* `Drawn triangles`: the number of triangles drawn per frame
* `Draw calls`: the number of draw calls per frame
* `Buffer memory`: the amount of memory allocated to buffers 
* `Texture memory`: the amount of memory allocated to textures

In the **GPU** and **CPU** modes, the profiler displays information about the parts of the code being profiled, including active scripts.

![Profiler columns](media/profiler-columns.png)

>[!Note]
>Each value describes the events per frame since the last profiler refresh.

Column  | Description
--------|--------
`TOTAL` | The total time taken to execute the code in one frame
`AVG/CALL` | Average time taken to execute a single call of the code
`MIN/CALL` | The shortest amount of time taken to execute a single call of the code
`MAX/CALL` | The longest amount of time taken to execute a single call of the code
`CALLS` | The number of times the code was executed in one frame
`MARKS` | The number of times per frame marked code is executed. This column is only displayed if marked code is executed
`PROFILE KEY / EXTRA INFO` | The part of the code (such as a function or script) being profiled. This column also displays additional information, such as the number of entities affected.

### Game Profiler runtime controls

You can change the Game Profiler settings at runtime using keyboard shortcuts.

Action  | Control
--------|--------
Left Ctrl + Left Shift + P  | Enable/disable the profiler
F1 | Toggle between CPU, GPU, and FPS-only results
F2 | Toggle between sorting by profile key and time
- / +  | Slow down / speed up the refresh time
F3 / F4 | Page back / page forward
Number keys | Jump to a page

### Use the Game Profiler in code

* Enable profiling:

    ```cs
    GameProfiler.EnableProfiling();
    ```

* Enable profiling only for the profiler keys you specify:

    ```cs
    GameProfiler.EnableProfiling(true, {mykey1,mykey2});
    ```

* Enable the profiling except for the profiler keys you specify:

    ```cs
    GameProfiler.EnableProfiling(false, {mykey1,mykey2});
    ```

* To access the prolifing key of a script, use [ProfilingKey](xref:Stride.Engine.ScriptComponent.ProfilingKey).

## Use external profiling tools

Instead of using the Stride Game Profiler, you can use external profiling tools to profile your project.

| Profiler | Type | Platforms
| ---- | ---- | -----
| [Visual Studio profiler](https://msdn.microsoft.com/en-us/library/mt210448.aspx) | Visual Studio feature | Desktop and mobile 
| [Xamarin Profiler](https://www.xamarin.com/profiler) | Standalone tool distributed with Xamarin Studio | Mobile 
| [RenderDoc](https://renderdoc.org/builds) | Standalone | Desktop and mobile

### Use the Visual Studio profiler

Visual Studio has powerful in-built profiling tools that can identify common performance issues.

1. In Visual Studio, open your project solution (`.sln`) file.

2. To open the profiler, press **Alt + F2**, or in the task bar click **Analyze > Performance Profiler**.

    ![Launch Visual Studio profiler](media/profiling-profiling-in-visual-studio-start-profiler.png)

3. In the **Profiler** window, select the profiling tools you want to run.

    ![Launch Visual Studio profiler](media/profiling-profiling-in-visual-studio-gpu-cpu-profiling-launch.png)

    You can run multiple profiling tools at once.

4. To launch the profiler, in the Performance Profiler tab, at the bottom, click **Start**.
   
   ![Profiler Start button](media/profiler-start-button.png)
    
    Visual Studio runs your application and begins profiling.

For more information about the Visual Studio profiler, see the [MSDN documentation](https://msdn.microsoft.com/en-us/library/mt210448.aspx).

### Использование RenderDoc

Render Doc — это бесплатный автономный графический отладчик с лицензией MIT, который позволяет быстро и легко захватывать отдельные кадры и проводить подробный анализ любого приложения с использованием Vulkan, D3D11, Open GL и Open GL ES или D3D12 в Windows 7–10, Linux, Android или Nintendo Switch™.

1. Загрузить [Render Doc](https://renderdoc.org/builds).

2. Необязательно: Этот шаг необязателен и необходим только в том случае, если вы хотите иметь маркеры прохода рендеринга с именем, следующим за Graphics Compositor:

   2.1. В своем исполняемом проекте (Windows) найдите `game.Run();` и вставьте следующий код непосредственно перед ним:

   ```cs
   game.GraphicsDeviceManager.DeviceCreationFlags |= DeviceCreationFlags.Debug;
   ```
   >[!Note]
   >Если у вас возникло исключение `SharpDXException` типа`DXGI_ERROR_SDK_COMPONENT_MISSING`, пожалуйста, следуйте инструкциям https://docs.microsoft.com/en-us/windows/uwp/gaming/use-the-directx-runtime-and-visual-studio-graphics-diagnostic-features

   2.2. Также убедитесь, что профилировщик включен, вызвав этот код из любого игрового скрипта:

    ```cs
    GameProfiler.EnableProfiling();
    ```

3. Необязательно: Добавьте ссылку на пакет`Stride.Graphics.RenderDocPlugin`.

   Затем вы можете использовать класс @'Stride.Graphics.RenderDocManager' для запуска захвата:
   
   ```cs
   var renderDocManager = new RenderDocManager();
   renderDocManager.StartCapture(GraphicsDevice, IntPtr.Zero);
   // Some rendering code...
   renderDocManager.EndFrameCapture(GraphicsDevice, IntPtr.Zero);
   ```

## Распространенные узкие места

Поскольку центральный процессор и графический процессор обрабатывают разные типы данных, обычно легко определить, какой из компонентов является узким местом.

Большинство проблем с графическим процессором возникают, когда приложение использует ресурсоемкие методы рендеринга, такие как постэффекты, освещение, тени и тесселяция. Чтобы определить проблему, отключите функции рендеринга.

Если вместо этого вы обнаружите узкое место в работе процессора, уменьшите сложность сцены.

Для графики:

* уменьшите разрешение вашей игры
* уменьшите качество ваших [пост-эффектов](../graphics/post-effects/index.md)
* уменьшите количество источников света и размер [карт теней](../graphics/lights-and-shadows/shadows.md)
* уменьшите размеры карты теней
* используйте методы отбраковки для уменьшения количества визуализируемых объектов и вершин

Для текстур:

* используйте [сжатые текстуры](../graphics/textures/compression.md) on slower devices
* используйте спрайт-листы, а не отдельные изображения
* используйте атласы текстур, а не отдельные текстуры

## Смотрите также

* [Профилирование](profiling.md)
