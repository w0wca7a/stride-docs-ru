﻿# Свойства аудио-актива
После выбора аудио-актива в **Просмотре активов (Asset View)** вы можете настроить его свойства в **Таблице свойств (Property grid)**.
![Свойства аудио-актива](media/audio-asset-properties.png)

| Свойство | Описание
|----------|----------
| **Источник (Source)** | Исходный аудиофайл (обратите внимание, что Stride никогда не изменяет исходные файлы)
| **Коэффициент сжатия (Compression ratio)** | Установите степень сжатия от «1» (без сжатия) до «40» (максимум). Большее сжатие оптимизирует использование памяти, но снижает качество звука. Stride сжимает аудиофайлы с помощью кодека с открытым исходным кодом [Opus/Celt](https://en.wikipedia.org/wiki/CELT).
|**Частота дискретизации (Sample rate)** | Скорость, с которой Stride [производит ресэмпл](https://ru.wikipedia.org/wiki/Частота_дискретизации) исходного файла. Чем выше частота дискретизации, тем выше качество звука. Наиболее используемые частоты дискретизации: 44.1 kГц (44,100 Гц), 48 kГц, 88.2 kГц, and 96 kГц. Обратите внимание, что высокая частота дискретизации не улучшает качество аудиофайлов низкого качества.       
| **Пространственный (Spatialized)**  | Имитация 3D-аудио (см. [пространственный звук](spatialized-audio.md))
| **Транслировать с диска (Stream from disk)** | Потоковая передача полезна для больших аудиофайлов, так как она экономит память. Для получения дополнительной информации см. [Аудиопоток](stream-audio.md).

## Смотрите также

* [Импорт звуковых файлов](import-audio.md)
* [Глобальные звуковые настройки](global-audio-settings.md)
* [Пространственный звук](spatialized-audio.md)
* [Непространственный звук](non-spatialized-audio.md)