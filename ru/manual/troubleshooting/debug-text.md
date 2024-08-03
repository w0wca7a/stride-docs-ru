# Отладочный текст

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Программист</span>

Вы можете во время выполнения вывести текст отладки  с помощью [DebugText](xref:Stride.Engine.ScriptComponent.DebugText). Например, вы можете использовать это для отображения сообщения при возникновении проблемы.

>[!Note]
>Отладочный текст автоматически отключается при сборке игры в режиме релиза.

В методе `Update` вашего скрипта добавьте:

```cs
DebugText.Print("My debug text",new Int2(x: 50, y: 50));
```

Где `x` и `y` — это пиксельные координаты, в которых будет отображаться текст.

Сообщение отладки отображается при запуске игры.

![Отладочный текст](media/my-debug-text.jpg)

Чтобы скрыть текст отладки, используйте:

```cs
DebugText.Visible = false;
```

## Пример сценария

Следующий скрипт проверяет, что текстура`MyTexture` загружена. Если не загружена, игра выводит отладочный текст «MyTexture not loaded».
```cs
using Stride.Core.Mathematics;
using Stride.Engine;
using Stride.Graphics;

namespace MyGame
{
    public class Script : SyncScript
    {
		public Texture myTexture;

        public override void Start()
        {
            // Initialization of the script.
            myTexture = Content.Load<Texture>("MyTexture");
        }

        public override void Update()
        {
			if (myTexture == null)
                DebugText.Print("MyTexture not loaded", new Int2(x: 50, y: 50));
        }
    }
}
```

## Смотрите также

* [Ведение журнала](logging.md)
* [Скрипты](../scripts/index.md)