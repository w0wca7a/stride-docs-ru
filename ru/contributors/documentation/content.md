# ���������� ������������

## ���������� ��������

���� �� ������ ������ ���� ����� � �������� ���-����, �������� ����������� ����.

��������� ���������� ����� ��������� ��������������� � ���-���������� GitHub, ��� ����� ������� ���������� ��������� ��������� ����� ����������, ������� ������� � ������� [���������](installation.md).

��� �������� ��������� �� ������ ������������ ����� ��������� ��������. ���� �� ����������� **Visual Studio**, �� ������ ������� ���� ������� `Stride.Docs.sln` � ����� ����������� � ������ ������� ���������� ��������������� �� ���� IDE.

�� ������ ������ [������� ��������](https://github.com/stride3d/stride-docs/issues) ����� �������� ���� ���������, ������ ��� �� ������� ��� ���� ��������. 

### ��������� ����������

�������� �������� �� ��������� ��� ��������� ����������, �� ������������� �������� ������, ��� ��� �� ���������. ���� �� �� �������, �������� �� ���� ���������� ��������� ��� ���, ������� �������� ��������.

#### ��� ��� ����� ��������� ����������?

�� ����� ���������� ��������� ���������� ��� ��������� � ���������� ���-�����:

- ���������� ����������� ������������ �������� (�����������, ������� ��� ���������� � ������� � �. �.)
- ���������� [������ �����������](#creating-new-manual-page) ��� [�������](#creating-new-tutorial-page) ��� ����� ����� �������
- ����������� ��������

#### ����

> [!����������]
> � ���� ����������� ��������������, ��� �� ��� ������� � ����������� ������ �� GitHub.

��� ��������� ���������� ����������� [GitHub ����������� ������������ �� Stride](https://github.com/stride3d/stride-docs):

[!INCLUDE [��������� ����������](../../includes/small-update-instructions.md)]

### �������� ����������

[�������� ��������](https://github.com/stride3d/stride-docs/issues) **���������** ��� ������� ����������, ����� ������ ����� �������������� ���� ��������� � ��������� ������.

������� ���������� ����� ���������� ��� ������������ ��������� � ������� ���-�����, ��� ������� ������� �������������� ����������� ������� ����� ���������, ����� ���������, ��� ��� ��������� ��������� ����������. ��� ����� �������� � ����:

- ���������� ������ Docfx
- ��������� �������
- ���������� ��������� �������

������� � ��������� ��������� ����� ����������, ��� ������� � ������� [Installation](installation.md). ����� �������� � ������������ ��������� �������� ��� ������� ������� ������ �� ���������, ����� ���������� ���� ��������� � ����� `master`.

��� �������� ������� �� ���������, �������� � ������ ������������ ���������, ������������� �������� **���������** ��� ������ �� ��������� �������������. ����� ������ �������� �������������� ����� ���������� ��������������� � ��������� ������������ ���� ���������. ���� �� ������������� ������������ �������������� GitHub ��� ����� ������������, ���������� � ������ [����������� �� ������������� �� ��������� GitHub](deployment-azure.md#deployment-to-github-pages) ��� ��������� ���������� �� ������������� � ������� �������� GitHub.
## �����������

��� �������� �������� ���������� � ���, ��� ������������ Stride � ������� ������ �� C# � �������� �������� �����.
> [!�����]
> **���������� �� SEO.** ���������, ��� ��� ����� �������� ������ �������� �����, ��������� � ����������� ������. ��� ����� �����, ��������� ��� ����� ���������� URL-����� �������� ��������, ������� ������ ������ ���� � ��������� ����������� (SEO).
### �������� ����� �������� �����������

1. �������� ����� ���� � ����� `manual`, � ��� ������������ ������ (��������, ��������, ����� � �. �.) ��� �������� ����� ����� � ����� `manual`.
   - ���� �� ������� ����� �����, ���������, ��� �� ����� ������� � ���� ����� ���� `index.md`.
1. ����������� ����� ������������ �������� � �������� ������� ��� ����� ��������.
1. �������� ���� `toc.yml` (��� `toc.md`) � ����� `manual`, ����� �������� ����� �������� ��� �����. ���� `toc.yml` �������� ���������� ������� �����������, ������� ������������ � ����� ����� ������� �����������. ��� �������� ����� ���������� � ������������� ����������� PDF-����.

### ���������� �� ����������

�������� �������� �� ������������ �������� � ����� �� ������� ���������� �� ������.

### �����

�� ������ ��������, ��� ������������ ����� ����� ����� ����� `media`. ��� ����� �������� ����������� � �����, ������������ �� ��������� �����������. �� ������ ������������ ��� ����� ��� ������� ����� � ����� �����. ���� ��������, ���������, ��� ����������� ����� ������ `.webp`, � ����� � ������ `.mp4`.

## �����������

�� ���� ��������� ���������� ����������� �� ������������� �������� ������ Stride � �������� �������� ����� �� C#.

### �������� ����� �������� �����������

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

## �����

### ��������� Bootstrap

We utilize the `modern` template provided by Docfx, which employs the [Bootstrap](https://getbootstrap.com/) framework, version **5.3**. This includes the dark theme, enabled by Docfx.
�� ���������� ������ `modern`, ��������������� Docfx, � ������� ������������ ��������� [Bootstrap](https://getbootstrap.com/), ������ **5.3**. ���� ������ ������ ����, ���������� Docfx.
> [!�����]
> ������ ��� ������������� ����� ���������������� �����, ������� ��������� ������������� ����������� ����� Bootstrap. �� ������ ���� ������� � [��������� Bootstrap](https://getbootstrap.com/docs/5.3/utilities/api/), ������� ������� ��� ������������� ����������� ���������� � �����.

### ������������ CSS

���� ���� � �������� ����������� CSS-���, ����� ������� ���-���� ������, ����������� ��������� ��������� Bootstrap.

## �������� ���������

[!INCLUDE [submitting-changes](../../includes/submitting-changes.md)]