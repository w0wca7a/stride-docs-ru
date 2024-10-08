# Аудиоизлучатели / Источники звука

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Программист</span>
<span class="badge text-bg-success">Дизайнер</span>

[Компоненты Audio emitter](xref:Stride.Audio.AudioEmitter) издают звук, используемый для создания [пространственного звука](spatialized-audio.md). Вы можете добавить их к любому объекту.

Высота и громкость звука изменяются по мере того как [аудио слушатель](audio-listeners.md) приближается к источнику звука и удаляется от него.

> [!Note] 
Вам нужен как минимум один [компонент AudioListenerComponent](xref:Stride.Audio.AudioListener) в сцене, чтобы слышать звук от аудиоизлучателей.

## 1. Настройка актива аудиоизлучателя

1. В **Обзоре сцены (Scene view)** выберите объект, который вы хотите сделать источником звука.

    ![Select an entity](media/audio-add-audiolistener-component-select-entity.png)

2. В **Сетке свойств (Property Grid)**, нажимите **Добавить компонент (Add component)** и выберите **Аудиоизлучатель (Audio Emitter)**.

    ![Add AudioEmitter Component](media/audio-add-audioemitter-component-select-entity.png)

    Теперь нам нужно добавить звук к излучателю.

3.  Под **Аудиоизлучателем (Audio Emitter)**, нажимите ![Green plus button](~/manual/game-studio/media/green-plus-icon.png) (**Добавить (Add)**) и укажите название аудио.

    ![Add new sound entry](media/audio-play-audioemitter-component-add-new-entry.png)

4. Из **Просмотра активов (Asset View)**, перетащите аудиоресурс на только что добавленный вами аудиофайл:

    ![Drag and drop an audio asset](media/audio-play-drag-and-drop-audio-asset.gif)

    В качестве альтернативы нажмите ![Hand icon](~/manual/game-studio/media/hand-icon.png) (**Выберите актив (Select an asset)**).

    ![Pick up an asset](media/audio-play-audioemitter-component-pick-an-asset.png)

    Затем выберите аудиоактив:

    ![Select audio  asset](media/audio-play-audioemitter-component-add-select-audio-asset.png)

5. Повторите шаги 3 и 4, чтобы добавить столько аудиоресурсов, сколько вам нужно.

6. Настройте свойства этого аудиоизлучателя.

    ![Audio emitter properties](media/audio-emitter-properties.png)

| Свойство          | Описание
|--------------------|-------------
| Использовать HRTF (Use HRTF)          | Включить функцию передачи, связанную с головой (HRTF). При включении этой функции создается впечатление, что звуки исходят из определенной точки трехмерного пространства, что создает [бинауральный звук](https://ru.wikipedia.org/wiki/%D0%91%D0%B8%D0%BD%D0%B0%D1%83%D1%80%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9_%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82#%D0%9E%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5). Для получения более подробной информации см. [HRTF](hrtf.md).
| Directional factor | How directional the audio is, from 0 (min) to 1 (max). If set to 0, the audio is emitted from all directions. You can control this with a slider or number value. 
| Environment        | The reverb type for the audio, simulating reverberation of real environments (small, medium, large, or outdoors).

## 2. Create a script to play the audio

Now we need to create a script to play and configure the audio asset.

1. In your script, instantiate [AudioEmitterSoundController](xref:Stride.Audio.AudioEmitterSoundController) for each sound you want to use in the script.

   For example, say we have two sounds, **MySound1** and **MySound2**:
   
	```cs
	AudioEmitterComponent audioEmitterComponent = Entity.Get<AudioEmitterComponent>();
	AudioEmitterSoundController mySound1Controller = audioEmitterComponent["MySound1"];
	AudioEmitterSoundController mySound2Controller = audioEmitterComponent["MySound2"];
	```

2. Use the following [AudioEmitterSoundController](xref:Stride.Audio.AudioEmitterSoundController) properties and methods to play and configure the audio:

| Property / method | Description |
|-------    |-------|
| [IsLooping](xref:Stride.Audio.AudioEmitterSoundController.IsLooping) | Loops audio. Has no effect if [PlayAndForget()](xref:Stride.Audio.AudioEmitterSoundController.PlayAndForget) is set to true.|
| [Pitch](xref:Stride.Audio.AudioEmitterSoundController.Pitch)     | Gets or sets sound pitch (frequency). Use with caution for spatialized audio. |
| [PlayState](xref:Stride.Audio.AudioEmitterSoundController.PlayState)	| Gets the current state of the audio emitter sound controller. |
| [Volume](xref:Stride.Audio.AudioEmitterSoundController.Volume)	| Volume of the audio. | 
| [Pause()](xref:Stride.Audio.AudioEmitterSoundController.Pause)	| Pauses audio. |
| [Play()](xref:Stride.Audio.AudioEmitterSoundController.Play)      | Plays audio. |
| [PlayAndForget()](xref:Stride.Audio.AudioEmitterSoundController.PlayAndForget)| Plays audio once, then clears the memory. Useful for short sounds such as gunshots. Overrides [IsLooping](xref:Stride.Audio.AudioEmitterSoundController.IsLooping).|
| [Stop()](xref:Stride.Audio.AudioEmitterSoundController.Stop)	| Stops audio. |

For example:

```cs
mySound1Controller.IsLooping = true;
mySound1Controller.Pitch = 2.0f;
mySound1Controller.Volume = 0.5f;
mySound1Controller.Play();
```

This sound will loop at double the original pitch and half the original volume. For more information, see the [AudioEmitterSoundController Stride API documentation](xref:Stride.Audio.AudioEmitterSoundController).

## 3. Add the script to the audio emitter entity

Game Studio lists the script as a component under **Add component**. Add the script to the audio emitter entity.

1. In the **Scene view**, select an entity you want to be an audio emitter.

    ![Select an entity](media/audio-add-audiolistener-component-select-entity.png)

2. Click **Add component** and select the script.

    ![Add audio script](media/add-sound-script.png)

## Смотрите также
* [Пространственный звук](spatialized-audio.md)
* [Слушатели аудио](audio-listeners.md)
* [Global audio settings](global-audio-settings.md)