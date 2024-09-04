# Установка аудиоустройства

<span class="badge text-bg-primary">Продвинутый</span>
<span class="badge text-bg-success">Программист</span>

Вы можете указать, какое аудиоустройство будет использовать Stride. Например, вы можете получить доступ к аудиоустройству Oculus Rift из своего конструктора игры.

Если устройство не указано, Stride использует звуковое устройство системы по умолчанию.

## Пример кода

Этот код настраивает устройство Oculus Rift во время выполнения:

```cs
namespace OculusRenderer
{
    public class OculusGame : Game
    {
        public OculusGame()
        {
            var deviceName = OculusOvr.GetAudioDeviceFullName();
            var deviceUuid = new AudioDevice { Name = deviceName };
            Audio.RequestedAudioDevice = deviceUuid;
        }
    }
}
```

## Смотрите также
* [Глобальные звуковые настройки](global-audio-settings.md)