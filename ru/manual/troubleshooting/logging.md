# ������� �������

<span class="badge text-bg-primary">�����������</span>
<span class="badge text-bg-success">�����������</span>

�� ������ **����� ������** ���������� � ����� ���� �� ����� �� ������, ��������� [Log](xref:Stride.Engine.ScriptComponent.Log).

� ������� �� [��������������](profiling.md), ������� ������������� ��������� ����������, �� ������ ��������� ����������� ��������� ������� � ����������, ����� ��� ����� �����������. ��������, �� ������ ������� ��������� �������, ������� �����������, ����� �������� ��������� ������������ ��������. ��� ������� ��� ������������ ����, ��� �������� ���� ����.

>[!����������]
>������� ������� ��������� ��� ������ ���� � ������ ������..

����� �� ����������� ������� ������� � ���������� ���� � ������ �������, Stride ��������� ������� �� ������ ���� ��� ����������� ���������� �������. ��������� ����� �������� ��������� � ����������� �� ������.
��� ������ (��������, �������, ����������� ��������� �������) ������������ � �������. ����� ������� ������� ������� (��������, **��������������**, **������** � �.�.), � ����� ��������� �������.

![������� ������� � �������](media/logging-in-console.png)

������� ���������� ��������� ������� ���� �������, � �� ������ ���� ����������� �������. ��������, ��� ����� ���������� ��������� �� @'Stride.Core.Serialization.Contents.ContentManager'.

���� �� ���������� ���� �� Visual Studio, ��������� ������� ������������ � ���� **Output** Visual Studio.

![���� ������ �������](media/log-output-in-visual-studio.png)

## ������ �������

���������� ����� ������� ��������� �������, ������������ ��� ������ ������� �����������.

| ������� ������� | ����| ��������
|-----------|-------|-----
| Debug | �����| ��������� ���������� ��� ����������� ����� �������
| Verbose | �����| ��������� ����������
| Info |�������| ����� ����������
| Warning | ������ | �������������� ������, ������� ����� ������� ��������
| Error | ������� |������
| Fatal | ������� | ��������� ������, ���������� � ���� ����

�� ��������� � ������� ������������ ��������� ��� ������ **Info** � ����. ��� ��������, ��� ��������� **Debug** ��� **Verbose** �� ������������. ����� �������� ���, ��. **Set the minimum level** below.

## ����� ��������� �������

� �������, ���������� ���, ������� �� ������ �������, ��������:

```cs
Log.Debug("My log message");
```

�� ������ �������� `Debug` �������, ������� �� ������ ������������ ��� ��������� ������� (��. ���� **������ �������** ).

�� ������ ���������� ��� � ���������� `if`  ��� ������ ��������� ��� ������������ �������� (��. ���� **������ ��������** ).

## ��������� ������ �������

�� ������ ���������� ����������� ������� ������� ��� �����������. ��������, ���� �� ������ ������ ������ ���������, ������� �������� ����������, ��� **Warning** ��� ����, �����������:

```cs
Log.ActivateLog(LogMessageType.Warning);
```

>[!����������]
>��� �� ���������� ���������. ������������� ���� ������� ������� ������� ����������� ������ � ���� �������, � ������� �� ��� ����������..

### ��������� ������ ������� �� ����� ����������

```cs
((Game)Game).ConsoleLogLevel = LogMessageType.myLogLevel;
```

### ���������� ������������� �������

```cs
GlobalLogger.GetLogger("RouterClient").ActivateLog(LogMessageType.Debug, LogMessageType.Fatal, false); 
// Disables logging of the RouterClient module
```

### ��������� ������� ������� � �������

```cs
((Game)Game).ConsoleLogMode = ConsoleLogMode.None;
```

### �������� ����� �������

����� ��������� ����� ������� � ��������� ����, �������� ���� ��� � �����`Start` :

```cs
var fileWriter = new TextWriterLogListener(new FileStream("myLogFile.txt", FileMode.Create));
GlobalLogger.GlobalMessageLogged += fileWriter;
```

��� ������� ���� � ����� Debug ������ �������. (�������� *MyGame\MyGame\Bin\Windows\Debug\myLogFile.txt*).

## ������ ��������

��������� ������ ���������, ��� �������� `MyTexture` ���������. ��� �������� �������� � ������� ������������ ���������� ��������� (`Log.Debug`). ���� �� �����������, � ������� �������������� ��������� �� ������. (`Log.Error`).

```cs
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Stride.Core.Diagnostics;
using Stride.Core.Mathematics;
using Stride.Input;
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
            Log.ActivateLog(LogMessageType.Debug);
            Log.Debug("Start loading MyTexture");

            myTexture = Content.Load<Texture>("MyTexture");
            if (myTexture == null)
            {
                Log.Error("MyTexture not loaded");
            }
            else
            {
                Log.Debug("MyTexture loaded successfully");
            }
        }
    }
}
```

## �������� �����

* [���������� �����](debug-text.md)
* [��������������](profiling.md)
* [��������](../scripts/index.md)