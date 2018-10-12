# <a name="onenote-javascript-api-overview"></a>Обзор API JavaScript для OneNote

Область применения: OneNote Online

Ниже приведены ссылки на высокоуровневые объекты OneNote, доступные в API. Каждая ссылка на страницу объекта содержит описание свойств, связей и методов, доступных для объекта. Чтобы узнать больше, перейдите по ссылкам ниже. 
    
- [Application](/javascript/api/onenote/onenote.application): объект верхнего уровня, используемый для доступа ко всем глобально адресуемым объектам OneNote, таким как активная записная книжка и активный раздел.

- [Notebook](/javascript/api/onenote/onenote.notebook): записная книжка. Записные книжки содержат группы разделов и разделы.
    - [NotebookCollection](/javascript/api/onenote/onenote.notebookcollection): представляет коллекцию записных книжек.

- [SectionGroup](/javascript/api/onenote/onenote.sectiongroup): группа разделов. Группы разделов содержат разделы и группы разделов.
    - [SectionGroupCollection](/javascript/api/onenote/onenote.sectiongroupcollection): коллекция групп разделов.

- [Section](/javascript/api/onenote/onenote.section): раздел. Разделы содержат страницы.
    - [SectionCollection](/javascript/api/onenote/onenote.sectioncollection): коллекция разделов.

- [Page](/javascript/api/onenote/onenote.page): страница. Страницы содержат объекты PageContent.
    - [PageCollection](/javascript/api/onenote/onenote.pagecollection): коллекция страниц.

- [PageContent](/javascript/api/onenote/onenote.pagecontent): область верхнего уровня на странице, содержащая контент, например типов Outline или Image. Объекту PageContent можно назначить позицию на странице.
    - [PageContentCollection](/javascript/api/onenote/onenote.pagecontentcollection): коллекция объектов PageContent, представляющая содержимое страницы.

- [Outline](/javascript/api/onenote/onenote.outline): контейнер для объектов Paragraph. Объект Outline — прямой потомок объекта PageContent.

- [Image](/javascript/api/onenote/onenote.image): объект Image. Объект Image может быть прямым потомком объекта PageContent или объекта Paragraph.

- [Paragraph](/javascript/api/onenote/onenote.paragraph): Контейнер для содержимого, отображаемого на странице. Объект Paragraph — прямой потомок объекта Outline.
    - [ParagraphCollection](/javascript/api/onenote/onenote.paragraphcollection): коллекция объектов Paragraph в объекте Outline.

- [RichText](/javascript/api/onenote/onenote.richtext): объект RichText.

- [Table](/javascript/api/onenote/onenote.table): контейнер для объектов TableRow.

- [TableRow](/javascript/api/onenote/onenote.tablerow): контейнер для объектов TableCell.
    - [TableRowCollection](/javascript/api/onenote/onenote.tablerowcollection): Коллекция объектов TableRow в объекте Table.
 
- [TableCell](/javascript/api/onenote/onenote.tablecell): контейнер для объектов Paragraph.
    - [TableCellCollection](/javascript/api/onenote/onenote.tablecellcollection): коллекция объектов TableCell в объекте TableRow.

## <a name="onenote-javascript-api-reference"></a>Справочник по API JavaScript для OneNote

Подробные сведения об API JavaScript для OneNote  см. в [Справочная документация по API JavaScript для OneNote](/javascript/api/onenote).

## <a name="see-also"></a>См. также

- [Обзор создания кода с помощью API JavaScript для OneNote](https://docs.microsoft.com/office/dev/add-ins/onenote/onenote-add-ins-programming-overview)
- [Создание первой надстройки OneNote](https://docs.microsoft.com/office/dev/add-ins/onenote/onenote-add-ins-getting-started)
- [Пример надстройки Rubric Grader](https://github.com/OfficeDev/OneNote-Add-in-Rubric-Grader)
- [Обзор платформы надстроек Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)