# Глобальные звуковые настройки

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Программист</span>

Глобальные настройки звука применяются ко всему аудио в вашем проекте. 

Вы можете управлять глобальными настройками звука, перейдя в **properties** в классе [AudioEngine](xref:Stride.Audio.AudioEngine):

| Свойство | Функция |
|--- | --- |
| [MasterVolume](xref:Stride.Audio.AudioEngine.MasterVolume) | Устанавливает общую громкость. |
| [PauseAudio](xref:Stride.Audio.AudioEngine.PauseAudio) | Пристанавливает воспроизведение всех звуков. |
| [ResumeAudio](xref:Stride.Audio.AudioEngine.ResumeAudio) | Возобновляет воспроизведение всех звуков. |

Вы также можете управлять звуками по отдельности с помощью [SoundInstance API](xref:Stride.Audio.SoundInstance).

## Смотрите также
* [Пространственный звук](spatialized-audio.md)
* [Непространственный звук](non-spatialized-audio.md)
* [Документация SoundInstance API](xref:Stride.Audio.SoundInstance)