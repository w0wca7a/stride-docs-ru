# Пользовательские аудиоданные

<span class="badge text-bg-primary">Продвинутый</span>
<span class="badge text-bg-success">Программист</span>

Вы можете генерировать звук, используя свой собственный механизм. Для этого создадим подкласс [DynamicSoundSource](xref:Stride.Audio.DynamicSoundSource).
Пример того, как это реализовать, см. [исходный код CompressedSoundSource ](https://github.com/Stride3d/stride/blob/master/sources/engine/Stride.Audio/CompressedSoundSource.cs).

## Пример кода

Чтобы воспроизвести пользовательский [DynamicSoundSource](xref:Stride.Audio.DynamicSoundSource) во время выполнения используйте:

```
int sampleRate = 48000;
bool mono = false;
bool spatialized = false;
DynamicSoundSource myCustomSource = new MyCustomSource(...);
AudioListener listener = Audio.AudioEngine.DefaultListener;
AudioEngine audioEngine = Audio.AudioEngine;
SoundInstance myCustomInstance = new SoundInstance(audioEngine, listener, myCustomSource, sampleRate, mono, spatialized);
await myCustomInstance.ReadyToPlay();
myCustomInstance.Play();
```

## Смотрите также
* [Глобальные звуковые настройки](global-audio-settings.md)
