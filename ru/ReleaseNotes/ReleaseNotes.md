# Примечания к выпуску Stride 4.2

20 Ноября 2023

Участники Stride рады объявить о выпуске Stride 4.2, который теперь полностью совместим с .NET 8 и использует последние улучшения C# 12. Этот выпуск значительно улучшает производительность, стабильность и удобство для разработчиков.
Огромное спасибо open-source сообществу Stride за ваш самоотверженный вклад. В этом выпуске было внесено X вкладов от более чем Y замечательных участников, каждый из которых сыграл решающую роль в воплощении Stride 4.2 в реальность.

## Что нового в Stride 4.2
Stride 4.2 включает в себя многочисленные усовершенствования и улучшения.

- **[Интеграция с .NET 8](https://devblogs.microsoft.com/dotnet/announcing-dotnet-8/)**: Испытайте мощь и эффективность последней версии .NET при разработке игр. 
  - Полная совместимость с .NET 8 с использованием преимуществ [улучшенной производительности во время выполнения](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-8/).
  - **[Возможности С# 12](https://devblogs.microsoft.com/dotnet/announcing-csharp-12/)**: Используйте передовые возможности языка для написания более лаконичного и удобного в сопровождении кода, повышая эффективность кодирования и сокращая количество шаблонного кода.
- **[Изменена привязка Assimp к Silk.Net.Assimp.](https://github.com/stride3d/stride/pull/1158)**
  - Это изменение позволяет нам удалить большую часть кода C++/CLR, используемого компилятором ресурсов, и приближает нас на один шаг к запуску компилятора ресурсов в системах, отличных от Windows.
- [Миграция NET6+ и другие gettextnet#2](https://github.com/stride3d/gettextnet/pull/2)
  - Обновлен весь gettext.NET до последней стабильной версии NET
- [Enable multiple profiler consumers and add a timeline/tracing profiler #1788](https://github.com/stride3d/stride/pull/1788)
  - Эта функция добавляет профилировщик, выводящий данные в формате chrome://tracing, и изменяет Profiler, чтобы сделать это возможным.
- [Функция: добавлена поддержка типов проектов F# и VB #1821.](https://github.com/stride3d/stride/pull/1821)
  - В настоящее время только для проектов, содержащих только код.
    - [Примеры F#](https://stride3d.github.io/stride-community-toolkit/manual/code-only/examples/basic-examples-fs.html)
    - [Примеры Visual Basic](https://stride3d.github.io/stride-community-toolkit/manual/code-only/examples/basic-examples-vb.html)
- [Диагностический анализатор Stride #1864](https://github.com/stride3d/stride/pull/1864)
  - Реализует анализатор кода для отображения полезных предупреждений в вашей IDE и при компиляции, когда какой-либо из ваших членов или структур несовместим с системой сериализации.
- [OpenVR Обработка пользовательского разрешения, указанного пользователем в настройках VR #2000](https://github.com/stride3d/stride/pull/2000)
- [Редактор - Добавлена динамическая привязка к выбранным объектам #1801](https://github.com/stride3d/stride/pull/1801)
  - Реализует динамическую привязку, используемую при удержании клавиши (по умолчанию: левый Shift) при манипулировании (вращении/перемещении/масштабировании) объекта/сущности. 
  - Добавляет новую настройку горячих клавиш для динамической привязки.
  - Добавляет метод для обработки динамической привязки.
- [Редактор - Пользователь может выбрать, какой стек анимации импортировать в FBX # 1977](https://github.com/stride3d/stride/pull/1977)
  - Это изменение вводит поле, которое пользователи могут редактировать, чтобы контролировать, какую анимацию движок должен импортировать из исходного FBX.
- [Редактор — добавлена возможность автоматического копирования импортированных ресурсов в каталог Ресурсов #1827](https://github.com/stride3d/stride/pull/1827)
  - Мы рекомендуем хранить ресурсы в каталоге ресурсов вашего проекта, чтобы избежать проблем, которые могут возникнуть при совместном использовании проекта или перемещении файлов.  - Всякий раз, когда пользователи импортируют ресурсы, расположенные за пределами каталога ресурсов, им теперь будет отображаться диалоговое окно с вопросом, следует ли скопировать файл в этот каталог.

## Детальнее об изменениях

* Исправлено исключение, вызванное URL-адресом политики конфиденциальности в Crash Reporter от @MeharDT в https://github.com/stride3d/stride/pull/1878
* документация: add acastrodev as a contributor for code by @allcontributors in https://github.com/stride3d/stride/pull/1886
* документация: add SVNMLR as a contributor for design by @allcontributors in https://github.com/stride3d/stride/pull/1887
* документация: add JeromyWalsh as a contributor for code by @allcontributors in https://github.com/stride3d/stride/pull/1888
* документация: add parhamgholami as a contributor for design by @allcontributors in https://github.com/stride3d/stride/pull/1889
* Исправлены отсутствующие форматы текстур OpenGLES. от @Basewq in https://github.com/stride3d/stride/pull/1898
* field typo by @IXLLEGACYIXL in https://github.com/stride3d/stride/pull/1900
* [Editor] Improve Cameracontrol in Editor by @SVNMLR in https://github.com/stride3d/stride/pull/1879
* [XML Comment] Minor updates on EFlags in CollisionFilterGroups.cs by @VaclavElias in https://github.com/stride3d/stride/pull/1910
* Fixes the issue where projects were disappearing from the launcher by @acastrodev in https://github.com/stride3d/stride/pull/1880
* Fix typo in translations generation by @Ethereal77 in https://github.com/stride3d/stride/pull/1916
* Handle importing meshes with duplicate material names by @adrsch in https://github.com/stride3d/stride/pull/1920
* [Native] - Implement some existing C++ methods in C# by @Jklawreszuk in https://github.com/stride3d/stride/pull/1896
* [Launcher] Prevent launcher automatically closing when offline by @Eideren in https://github.com/stride3d/stride/pull/1912
* Small refactoring changes in Stride.GameStudio by @Jklawreszuk in https://github.com/stride3d/stride/pull/1741
* Remove MSBuild.Extras from project by @Jklawreszuk in https://github.com/stride3d/stride/pull/1895
* [Editor] Allow drag and drop of EntityComponent by @Eideren in https://github.com/stride3d/stride/pull/1921
* Add editor settings for the camera speed increase/decrease hotkeys by @adrsch in https://github.com/stride3d/stride/pull/1927
* docs: add adrsch as a contributor for code by @allcontributors in https://github.com/stride3d/stride/pull/1930
* Let the user set the default Bullet gravity vector in PhysicsSettings by @adrsch in https://github.com/stride3d/stride/pull/1928
* Migrate Irony.GrammarExplorer to net 6.0 by @Jklawreszuk in https://github.com/stride3d/stride/pull/1932
* [Core] Enable multiple profiler consumers and add a timeline/tracing profiler by @froce in https://github.com/stride3d/stride/pull/1788
* [Build] Fixed an errors in the build pipeline associated with having a space in the user name by @Fydar in https://github.com/stride3d/stride/pull/1941
* fix(graphics): Stop FastTextRenderer VB clobbering by @froce in https://github.com/stride3d/stride/pull/1954
* Update SSH.NET to 2023.0.0 by @WojciechNagorski in https://github.com/stride3d/stride/pull/1951
* [Build] Fix Android build error by @froce in https://github.com/stride3d/stride/pull/1949
* [Docs] Use XML documentation lists by @Fydar in https://github.com/stride3d/stride/pull/1948
* [Editor] Remove some windows dependencies in editor libraries by @Kryptos-FR in https://github.com/stride3d/stride/pull/1908
* parse numbers in NumericTextBox using CurrentCulture by @Schossi in https://github.com/stride3d/stride/pull/1811
* Xml comments fixing 1 by @VaclavElias in https://github.com/stride3d/stride/pull/1918
* [Presentation] Reduce allocations when parsing number in NumericTextBox by @Kryptos-FR in https://github.com/stride3d/stride/pull/1955
* [Sample] Replace deprecated GetServiceAs calls by @Eideren in https://github.com/stride3d/stride/pull/1943
* Fix compiling assets in Android build by @Basewq in https://github.com/stride3d/stride/pull/1905
* Removed all references to $(SolutionDir) from build artifacts by @JeromyWalsh in https://github.com/stride3d/stride/pull/1894
* [Serialization] Fix diverging rules for editor and runtime serialization of fields and properties by @Eideren in https://github.com/stride3d/stride/pull/1875
* feat(extension): Rename launcher buttons for clarity by @acastrodev in https://github.com/stride3d/stride/pull/1872
* Stride Diagnostics Analyzer by @IXLLEGACYIXL in https://github.com/stride3d/stride/pull/1864
* Fix Building by @MaximilianEmel in https://github.com/stride3d/stride/pull/1956
* [Math] Add a couple of helpers for Vectors by @ch3mbot in https://github.com/stride3d/stride/pull/1769
* Fix #1769 and introduce an optional argument to specify a different r… by @Kryptos-FR in https://github.com/stride3d/stride/pull/1964
* [Github] Update pull request template to ensure users tried out their changes by @Eideren in https://github.com/stride3d/stride/pull/1965
* Fixed small xml docs mistake by @Doprez in https://github.com/stride3d/stride/pull/1976
* Revert "[Editor] Remove some windows dependencies in editor libraries (#1908)" by @Eideren in https://github.com/stride3d/stride/pull/1980
* [AssemblyProcessor] Fixed packing path. by @Basewq in https://github.com/stride3d/stride/pull/1987
* [Core] Make object id more performant by @IXLLEGACYIXL in https://github.com/stride3d/stride/pull/1957
* [Docs] Move bounty paragraph to a more prominent spot by @Eideren in https://github.com/stride3d/stride/pull/1984
* [Readme] Some additional info for building Stride from source by @tebjan in https://github.com/stride3d/stride/pull/1988
* [Docs] Update PropertiesDemo.cs by @Eideren in https://github.com/stride3d/stride/pull/1991
* Fix failing to load data/db/index file on non-Win desktop platforms by @Jklawreszuk in https://github.com/stride3d/stride/pull/1995
* [Shaders] Fixes `EffectValueDescription.DefaultValue` for negative values by @azeno in https://github.com/stride3d/stride/pull/1990
* [Editor] Re-introduce workaround for missing input while navigating by @Eideren in https://github.com/stride3d/stride/pull/1897
* [Build] Fix native library loading picking up invalid files by @Basewq in https://github.com/stride3d/stride/pull/1999
* Fixes OpenXR by @MaximilianEmel in https://github.com/stride3d/stride/pull/1911
* [Breaking] Scoping generic extension methods by @Fydar in https://github.com/stride3d/stride/pull/1959
* Add information about Irony.GrammarExplorer project by @Jklawreszuk in https://github.com/stride3d/stride/pull/2007
* [VR] Remove framecap from VR sample by @Eideren in https://github.com/stride3d/stride/pull/2002
* Bump Newtonsoft.Json from 12.0.3 to 13.0.1 in /sources/metrics/Stride.Metrics by @dependabot in https://github.com/stride3d/stride/pull/1539
* [OpenVR] Handle custom resolution specified by the user through VR settings by @Eideren in https://github.com/stride3d/stride/pull/2000
* Update NuGet libraries to 6.4.2 by @manio143 in https://github.com/stride3d/stride/pull/2017
* Let the user pick which animation stack to import in an fbx by @adrsch in https://github.com/stride3d/stride/pull/1977
* Fixes OpenGL by @MaximilianEmel in https://github.com/stride3d/stride/pull/2023
* Update dotnet 8 by @Doprez in https://github.com/stride3d/stride/pull/1616

## New Contributors
* @adrsch made their first contribution in https://github.com/stride3d/stride/pull/1920
* @froce made their first contribution in https://github.com/stride3d/stride/pull/1788
* @Fydar made their first contribution in https://github.com/stride3d/stride/pull/1941
* @WojciechNagorski made their first contribution in https://github.com/stride3d/stride/pull/1951
* @Schossi made their first contribution in https://github.com/stride3d/stride/pull/1811
* @MaximilianEmel made their first contribution in https://github.com/stride3d/stride/pull/1956
* @ch3mbot made their first contribution in https://github.com/stride3d/stride/pull/1769

## Stride 4.2 Feature Overview

### F# and Visual Basic Integration

A pivotal PR has enabled **F#** and **Visual Basic** support for game development in Stride. This feature is currently limited to a code-only approach. Detailed insights and tutorials will be provided in upcoming blog posts.

We will use the [Stride Community Toolkit [WIP]](https://stride3d.github.io/stride-community-toolkit/), with further details to be covered in a separate post.

Below is a simple example of rendering a capsule using F#:

```fsharp
open Stride.CommunityToolkit.Engine;
open Stride.CommunityToolkit.ProceduralModels;
open Stride.Core.Mathematics;
open Stride.Engine;

let game = new Game()

let Start rootScene =
    game.SetupBase3DScene()
    game.AddProfiler() |> ignore

    let firstBox = game.CreatePrimitive(PrimitiveModelType.Capsule);
    firstBox.Transform.Position <- new Vector3(0f, 2.5f, 0f)
    firstBox.Scene <- rootScene

[<EntryPoint>]
let main argv =
    game.Run(start = Start)
    0
```

![Example basic 3d scene with a capsule](media/ReleaseNotes-4.2/stride-game-engine-example01-basic-3d-scene.webp)

The equivalent Visual Basic example:

```vb
Imports Stride.CommunityToolkit.Engine
Imports Stride.CommunityToolkit.ProceduralModels
Imports Stride.Core.Mathematics
Imports Stride.Engine

Module Program
    Private game As New Game()

    Sub Main()
        GameExtensions.Run(game, Nothing, AddressOf StartGame)
    End Sub

    Private Sub StartGame(rootScene As Scene)
        game.SetupBase3DScene()
        game.AddProfiler()

        Dim entity = game.CreatePrimitive(PrimitiveModelType.Capsule)
        entity.Transform.Position = New Vector3(0, 8, 0)
        entity.Scene = rootScene
    End Sub
End Module

```

These examples showcase how F# and Visual Basic can be utilized in Stride. The Stride Community Toolkit provides a set of helpers and extensions designed to enhance your experience with the Stride Game Engine.

## Fixes
Although there have been [many fixes](**https://github.com/stride3d/stride/pulls?page=2&q=is%3Apr+merged%3A%3E2023-10-10**), we like to point out some of them out
- [Runtime rasterized fonts are broken #1750](https://github.com/stride3d/stride/issues/1750)
- [Game Studio doesnt reload sub projects after changes #1703](https://github.com/stride3d/stride/issues/1703)
- [Changing the comparison project related and not UPath related #1704](https://github.com/stride3d/stride/pull/1704)
- [Translations fix #1717](https://github.com/stride3d/stride/pull/1717)
- [C# Beginner Tutorial Build Errors #1652](https://github.com/stride3d/stride/issues/1652)
- [Can not create "C# Beginner" project #1650](https://github.com/stride3d/stride/issues/1650)

## Also good to know
Although not directly tied to Release 4.2, we have made some other big changes. For instance to our website and documentation. We also had another community meeting to address all those new members.
- [Website and documentation revamped and build process updated](https://www.stride3d.net/blog/announcing-website-update/)
- [Contributor section moved to docs](https://doc.stride3d.net/latest/en/contributors/index.html)
- [Community meeting October 2023](https://www.stride3d.net/blog/community-meeting-october-2023/)

## Acknowledgements
We extend our heartfelt gratitude for all the hard work and donations that have been made. Your generous contributions significantly aid in the continuous development and enhancement of the Stride community and projects. Thank you for your support and belief in our collective efforts.
