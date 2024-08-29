# Запуск игры

<span class="badge text-bg-primary">Начинающий</span>

На этой странице объясняется, как запустить игру с помощью Game Studio или Visual Studio.

## Запуск игры из Game Studio

> [!Note]
> Game Studio не может запускать игры для платформ Windows Store или UWP (Universal Windows Platform). Чтобы запустить игру для этих платформ, используйте Visual Studio (см. ниже).

  1. На **панели инструментов** выберите целевую платформу.

      ![Выбор платформы](media/launch-your-game-game-studio-profiles.png)

      > [!Note]
      > Вы можете выбрать только те платформы, которые вы выбрали в диалоговом окне **Создать новую игру** при создании проекта. Чтобы добавить дополнительные платформы в проект, см. [Добавление или удаление платформы](../platforms/add-or-remove-a-platform.md).

  2. Чтобы запустить игру, нажмите ![Значок запуска](media/launch-your-game-play-icon.png) на панели инструментов или нажмите клавишу **F5**.

      ![Кнопка запуска Game Studio](media/game-studio-toolbar-build-button.png)

  **Окно вывода (Output)** показывает ход сборки. 

  ![Окно вывода](media/output-window.png)

  После завершения сборки ваша игра запустится на выбранной платформе.

## Запуск игры из Visual Studio

1. В Game Studio на панели инструментов нажмите ![Открыть в IDE](media/launch-your-game-ide-icon.png) (**Открыть в IDE (Open in IDE)**) для запуска Visual Studio.

2. На панели инструментов Visual Studio установите соответствующий проект в качестве запускаемого.
         
	![Select build profile in Visual Studio](media/launch-your-game-visual-studio-profiles.png)
   
   Конфигурация стартового проекта обновляется автоматически.
 
   > [!TIP]
   > Вы можете увидеть свои проекты в Solution Explorer справа. Расширения имен файлов проектов идентифицируют платформу (например, *.Android*, *.iOS* и т.д.).

3. Убедитесь, что конфигурация и платформа полностью соответствуют вашим ожиданиям.
  
4. * Чтобы запустить игру без отладки, нажмите **Ctrl + F5**.
   
   * Чтобы запустить игру с отладкой, нажмите **Start** или клавишу **F5**.

      ![Кнопка запуска Visual Studio](media/visual-studio-start-button.png)

## Удаление границ

По умолчанию игра запускается в окне с границами.

| С границами             | Без границ
|---------------------------|-----------------
| ![С границами](media/with-borders.jpg)   | ![Без границ](media/without-borders.jpg) 

Чтобы запустить игру в окне без границ, используйте:

```cs
Game.Window.IsBorderLess = true;
```

Например:

```cs
using Stride.Engine;

namespace MyGame
{
    public class MyScript : StartupScript
    {
        public override void Start()
        {
            base.Start();
            Game.Window.IsBorderLess = true;
        }
    }
}
```