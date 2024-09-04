# Непространственный звук

<span class="badge text-bg-primary">Начинающий</span>
<span class="badge text-bg-success">Программист</span>

**Непространственный звук (Non-spatialized audio)** звучит одинаково на протяжении всей сцены, независимо от положения объектов (например, камеры игрока).Он стерео и движется вдоль одной оси (обычно оси X). В отличие от [пространственного звука](spatialized-audio.md), _volume_, _pitch_ (_frequency_), и других параметров пространственного звука не изменяются. Это полезно, например, для фоновой музыки и звуковых эффектов меню.

![Non-spatialized audio](media/audio-index-non-spatialized-audio.png)

Непространственный звук не требует [аудио излучателей](audio-emitters.md) или [аудио слушателей](audio-listeners.md).

## 1. Импорт звукового файла и включение его в сборку

1. [Импорт звукового файла как аудиоактива](import-audio.md).

2. Убедитесь, что аудиоактив является **корневым активом**. Корневые активы — это активы, которые Stride включает в сборку, чтобы их можно было использовать во время выполнения.

    В **Просмотр активов (Asset View)**, щелкните правой кнопкой мыши по активу и выберите **Включить в сборку как корневой ресурс (Include in build as root asset)**:

    ![Include in build as root asset](media/audio-include-in-build-as-root-asset.png)

   Если в меню указано **Не включать в сборку как корневой ресурс (Do not include in build as root asset)**, опция уже выбрана, и вам не нужно ее менять.

## 2. Создание скрипта для воспроизведения звука

Чтобы воспроизвести непространственный звук во время выполнения, создайте его экземпляр и определите его поведение в коде.
[SoundInstance](xref:Stride.Audio.SoundInstance) управляет звуком во время выполнения с помощью следующих свойств:

| Свойство                                               | Функция                                                                              |
|--------------------------------------------------------|------------------------------------------------------------------------------------------|
| Зацикливание [IsLooping](xref:Stride.Audio.SoundInstance.IsLooping) | Получает или задает зацикливание звука.                                                      |
| Баланс [Pan](xref:Stride.Audio.SoundInstance.Pan)             | Устанавливает баланс между левым и правым динамиками. По умолчанию каждому динамику присвоено значение 0. |
| [Pitch](xref:Stride.Audio.SoundInstance.Pitch)         | Получает или задает высоту звука (частоту).                                                |
| [PlayState](xref:Stride.Audio.SoundInstance.PlayState) | Получает состояние [SoundInstance](xref:Stride.Audio.SoundInstance).                  |
| [Position](xref:Stride.Audio.SoundInstance.Position)   | Получает текущую позицию воспроизведения аудио.                                             |
| [Volume](xref:Stride.Audio.SoundInstance.Volume)       | Устанавливает громкость звука.                                                                  |

Более подробную информацию см. [SoundInstance API documentation](xref:Stride.Audio.SoundInstance).

> [!Note]
Если звук уже воспроизводится, Stride игнорирует все дополнительные вызовы [SoundInstance.Play](xref:Stride.Audio.SoundInstance.Play).
То же самое касается [SoundInstance.Pause](xref:Stride.Audio.SoundInstance.Pause) (когда воспроизведение уже приостановлено) и [SoundInstance.Stop](xref:Stride.Audio.SoundInstance.Stop) (когда воспроизведение уже остановлено).

Например, следующий код:

* создает непространственный звук
* устанавливает зацикливание воспроизведения
* устанавливает громкость
* воспроизводит звук

```cs
public override async Task Execute()
{
    // Загрузка звука
    Sound musicSound = Content.Load<Sound>("MySound");
            
    // Создание непространственного звука
    SoundInstance music = musicSound.CreateInstance();
            
    // Зацикливание
    music.IsLooping = true;

    // Устанавливка громкости
    music.Volume = 0.25f;

    // Воспроизведение
    music.Play();
}
```

### Альтернативный способ: создание скрипта с public переменными

Создайте public переменную для каждого аудиоактива, который вы хотите использовать. Вы можете использовать те же свойства, что перечислены вышe.

Например:

```cs
public class MySoundScript : SyncScript
{
    public Sound MyMusic;

    private SoundInstance musicInstance;
    public bool PlayMusic;

    public override void Start()
    {
        musicInstance = MyMusic.CreateInstance();
    }

    public override void Update()
    {
        // Если музыка не играет, но должна играть, включите ее.
        if (PlayMusic & musicInstance.PlayState != PlayState.Playing)
        {
            musicInstance.Play();
        }

        // Если музыка играет, но не должна, выключите ее.
        else if (!PlayMusic)
        {
            musicInstance.Stop();
        }
    }
}
```
## Добавьте скрипт к объекту Entity

1. В **Просмотре сцены (Scene view)**, выберите объект, к которому вы хотите добавить скрипт:

    ![Select an entity](media/audio-add-audiolistener-component-select-entity.png)

2. В **Сетке свойств (Property Grid)**, нажимите **Добавить компонент (Add component)** и выберите свой скрипт:
 
    ![Click Add component](media/audio-emitters-add-script-component.png)

    Скрипт добавляется к объекту.

3. Если вы добавили **public переменные** в скрипте, вам необходимо привязать их к аудиоактивам.

    Перетащите актив из **Просмотра активов (Asset View)** в каждую переменную:

    ![Drag and drop an audio asset](media/entity-audio-drag-and-drop-audio-asset-to-script-component.gif)

    В качестве альтернативы нажмите ![Hand icon](~/manual/game-studio/media/hand-icon.png) (**Выбрать актив (Select an asset)**):

    ![Pick up an asset](media/audio-play-script-component-pick-an-asset.png)

    Затем выберите аудиоресурс, который вы хотите использовать:

    ![Select an audio asset](media/audio-play-audioemitter-component-add-select-audio-asset.png)

## Смотрите также

* [Импорт звука](import-audio.md)
* [Глобальные настройки звука](global-audio-settings.md)
* [Пространственный звук](spatialized-audio.md)