# Передаточная функция, связанная с головой (HRTF)

**Передаточная функция, связанная с головой (HRTF)** — это усовершенствованный способ обработки звука, при котором создается впечатление, что звук исходит из определенной точки трехмерного пространства, что позволяет синтезировать бинауральный звук. Обеспечивает более реалистичный звук, чем стандартный [пространственный звук](spatialized-audio.md). Например, с помощью HRTF игрок может слышать, находится ли персонаж выше или ниже него. Это особенно полезно для [VR приложений](../virtual-reality/index.md), так как это увеличивает погружение.

Для использования HRTF игрокам не нужно специальное оборудование. Однако эффект работает гораздо лучше с наушниками, чем с динамиками.

Это видео демонстрирует эффект звука HRTF:

<p>
<video class="embed-responsive-item" poster="media/hrtf-first-frame.jpg" controls>
   <source src="media/hrtf.mp4" type="video/mp4">
</video>
</p>

>[!Note]
>На данный момент HRTF можно использовать только в Windows 10.

## Включение HRTF

Чтобы использовать HRTF, сначала включите его глобальное изменение в активе **Game Settings**, затем включите HRTF для тех объектов, с которыми вы хотите его использовать.

### 1. Включение глобальной настройки HRTF

1. В **Solution explorer** (нижняя левая панель по умолчанию), select the **Assets folder**.

    ![Select Assets folder asset](../game-studio/media/select-asset-folder.png)

2. In the **Asset View** (the bottom pane by default), select the **GameSettings** asset.

    ![Select Game Settings asset](../game-studio/media/select-game-settings-asset.png)

3. In the **Property Grid** (the right-hand pane by default), under **Audio settings**, select **HRTF support**.

    ![Audio settings](../game-studio/media/audio-settings.png)

For more information about the Game Settings asset, see [Game settings](../game-studio/game-settings.md).

### 2. Enable HRTF on the entities

1. Select the entity with the [audio emitter](audio-emitters.md) that contains the sound you want to enable for HRTF.

2. In the **Property Grid** (on the right by default), under **Audio emitter**, select **Use HRTF**.

    ![Audio emitter properties](media/audio-emitter-properties.png)

    Sounds emitted from this entity will use HRTF.

    >[!Note]
    >The HRTF option applies to every sound emitted from this audio emitter.
    
For more information about audio emitters, including the properties you can change, see [Audio emitters](audio-emitters.md).

### See also

* [Head-related transfer function (Wikipedia)](https://en.wikipedia.org/wiki/Head-related_transfer_function)
* [Spatialized audio](spatialized-audio.md)
* [Audio emitters](audio-emitters.md)
* [Audio listeners](audio-listeners.md)
* [Game settings](../game-studio/game-settings.md)