# Содержание документации

## Обновления контента

Если вы хотите внести свой вклад и обновить веб-сайт, следуйте инструкциям ниже.

Небольшие обновления можно выполнять непосредственно в веб-интерфейсе GitHub, для более крупных обновлений требуется локальная среда разработки, которая описана в разделе [Установка](installation.md).

Для внесения изменений вы можете использовать любой текстовый редактор. Если вы используете **Visual Studio**, вы можете открыть файл решения `Stride.Docs.sln` в корне репозитория и начать вносить обновления непосредственно из этой IDE.

Вы всегда можете [создать проблему](https://github.com/stride3d/stride-docs/issues) чтобы обсудить ваши изменения, прежде чем вы начнете над ними работать. 

### Небольшие обновления

Создание проблемы не требуется для небольших обновлений, но рекомендуется сообщить другим, над чем вы работаете. Если вы не уверены, является ли ваше обновление небольшим или нет, сначала создайте проблему.

#### Что это такое небольшое обновление?

Мы можем определить небольшие обновления как изменения в содержимом веб-сайта:

- Обновление содержимого существующей страницы (руководство, примеры или примечание к выпуску и т. д.)
- Добавление [нового руководства](#creating-new-manual-page) или [примера](#creating-new-tutorial-page) или любой новый контент
- Исправление опечатки

#### Шаги

> [!ПРИМЕЧАНИЕ]
> В этом руководстве предполагается, что вы уже знакомы с обновлением файлов на GitHub.

Для следующих инструкций используйте [GitHub репозиторий документации по Stride](https://github.com/stride3d/stride-docs):

[!INCLUDE [небольшие обновления](../../includes/small-update-instructions.md)]

### Основные обновления

[Создание проблемы](https://github.com/stride3d/stride-docs/issues) **требуется** для крупных обновлений, чтобы другие могли комментировать ваши изменения и оставлять отзывы.

Крупные обновления можно определить как значительные изменения в дизайне веб-сайта, при которых полезно предварительно просмотреть влияние ваших изменений, чтобы убедиться, что они достигают желаемого результата. Это может включать в себя:

- Обновление версии Docfx
- Изменение макетов
- Обновление элементов дизайна

Начните с настройки локальной среды разработки, как описано в разделе [Installation](installation.md). После внесения и тестирования изменений локально вам следует создать запрос на включение, чтобы объединить ваши изменения в ветвь `master`.

При отправке запроса на включение, особенно в случае существенных изменений, рекомендуется включать **скриншоты** или ссылку на локальное развертывание. Такой подход помогает сопровождающим более эффективно визуализировать и оценивать предлагаемые вами изменения. Если вы предпочитаете использовать инфраструктуру GitHub для своих демонстраций, обратитесь к нашему [Руководству по развертыванию на страницах GitHub](deployment-azure.md#deployment-to-github-pages) для получения инструкций по развертыванию с помощью действий GitHub.
## Руководство

Эти страницы содержат информацию о том, как использовать Stride — игровой движок на C# с открытым исходным кодом.
> [!ВАЖНО]
> **Примечание по SEO.** Убедитесь, что имя файла содержит важные ключевые слова, связанные с содержанием статьи. Это очень важно, поскольку имя файла определяет URL-адрес страницы контента, который играет важную роль в поисковой оптимизации (SEO).
### Создание новой страницы руководства

1. Создайте новый файл в папке `manual`, в уже существующих папках (например, анимация, аудио и т. д.) или создайте новую папку в папке `manual`.
   - Если вы создали новую папку, убедитесь, что вы также создали в этой папке файл `index.md`.
1. Используйте любую существующую страницу в качестве шаблона для новой страницы.
1. Обновите файл `toc.yml` (или `toc.md`) в папке `manual`, чтобы включить новую страницу или папку. Файл `toc.yml` содержит оглавление страниц руководства, которое отображается в левой части страниц руководства. Эти страницы также включаются в дополнительно создаваемый PDF-файл.

### Соглашение об именовании

Обратите внимание на существующие страницы и папки на предмет соглашения об именах.

### Медиа

Вы можете заметить, что существующие папки могут иметь папку `media`. Эта папка содержит изображения и видео, используемые на страницах руководства. Вы можете использовать эту папку или создать новую в своей папке. Если возможно, убедитесь, что изображения имеют формат `.webp`, а видео — формат `.mp4`.

## Руководство

На этих страницах содержатся руководства по использованию игрового движка Stride с открытым исходным кодом на C#.

### Создание новой страницы руководства

1. Create a new tutorial folder in the `tutorial` folder.
1. Create a new `index.md` file in this folder. Observe existing tutorials for the content of this file.
1. Create markdown files for each step of the tutorial. Observe existing tutorials structure for the content of these files.
1. Update `toc.yml` file in the `tutorial` folder to include the new tutorial folder. The `toc.yml` file contains the table of contents for the tutorial pages, which is displayed on the left side of the tutorial pages.

### Naming Convention

Observe existing pages and folders for the naming convention.

### Media

You can observe that existing tutorials have a `media` folder. This folder contains images. If possible make sure that images are `.webp` format. The videos should be uploaded to YouTube and embedded in the tutorial pages.

## Other Sections

In addition to the Manual and Tutorial sections mentioned above, the same principles apply to both existing and new sections. Follow the established formats and conventions to ensure consistency and clarity throughout the documentation.

## Shortcodes and Includes

Docfx supports additional markdown syntax to enrich content. These syntaxes are specific to Docfx and **may not render** correctly on other platforms, like GitHub.

For more information, read the Docfx documentation on [markdown, shortcodes and includes](https://dotnet.github.io/docfx/docs/markdown.html?tabs=linux%2Cdotnet). Some commonly used features include:

- **Alert**: These are block quotes that render with distinct colors and icons, highlighting the importance or nature of the content
- **Video**: Embed video content directly into your documentation
- **Image**: Insert images to enhance the visual aspect of the documentation
- **Math Expressions**: Integrate mathematical notations and expressions
- **Mermaid Diagrams**: Embed [mermaid diagrams](https://mermaid.js.org/) for flowcharts and other graphical representations
- **Include Markdown Files**: Include content from other markdown files seamlessly
- **Code Snippet**: Insert code snippets for better clarity and demonstration
- **Tabs**: Organize content into tabbed sections for improved readability

## Web Assets

Our main web assets include:

- `template/partials/affix.tmpl.partial` - Currently not functioning
- `template/partials/footer.tmpl.partial` - Currently not functioning
- `template/public/main.css` - Contains minor Bootstrap CSS overrides
- `template/public/main.js`:
   - Sets the top navigation icons, such as GitHub, Discord, Twitter
   - Injects the Stride Docs version selection above the filter in the side navigation
   - Injects the Stride Docs language selection into the top navigation
- `docfx.json` - The HTML footer is included in the `_appFooter` section

## Стиль

### Настройка Bootstrap

We utilize the `modern` template provided by Docfx, which employs the [Bootstrap](https://getbootstrap.com/) framework, version **5.3**. This includes the dark theme, enabled by Docfx.
Мы используем шаблон `modern`, предоставленный Docfx, в котором используется платформа [Bootstrap](https://getbootstrap.com/), версия **5.3**. Сюда входит темная тема, включенная Docfx.
> [!ВАЖНО]
> Прежде чем интегрировать любые пользовательские стили, отдайте приоритет использованию встроенного стиля Bootstrap. Вы должны быть знакомы с [утилитами Bootstrap](https://getbootstrap.com/docs/5.3/utilities/api/), которые помогут вам удовлетворить большинство требований к стилю.

### Рекомендации CSS

Наша цель — написать минимальный CSS-код, чтобы сделать веб-сайт легким, максимально используя платформу Bootstrap.

## Отправка изменений

[!INCLUDE [submitting-changes](../../includes/submitting-changes.md)]