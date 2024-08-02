# ���������� �����

<span class="badge text-bg-primary">����������</span>
<span class="badge text-bg-success">�����������</span>

�� ������ �� ����� ���������� ������� ����� �������  � ������� [DebugText](xref:Stride.Engine.ScriptComponent.DebugText). ��������, �� ������ ������������ ��� ��� ����������� ��������� ��� ������������� ��������.

>[!����������]
>���������� ����� ������������� ����������� ��� ������ ���� � ������ ������.

� ������ `Update` ������ ������� ��������:

```cs
DebugText.Print("My debug text",new Int2(x: 50, y: 50));
```

��� `x` � `y` � ��� ���������� ����������, � ������� ����� ������������ �����.

��������� ������� ������������ ��� ������� ����.

![���������� �����](media/my-debug-text.jpg)

����� ������ ����� �������, �����������:

```cs
DebugText.Visible = false;
```

## ������ ��������

��������� ������ ���������, ��� ��������`MyTexture` ���������. ���� �� ���������, ���� ������� ���������� ����� �MyTexture not loaded�.
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

## �������� �����

* [������� �������](logging.md)
* [�������](../scripts/index.md)