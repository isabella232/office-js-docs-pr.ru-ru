---
title: Разработка надстроек Office
description: Общие сведения о разработке надстроек Office.
ms.date: 10/14/2020
localization_priority: Priority
ms.openlocfilehash: 4f65284730e1211b0628139b7f22c55deb7a6fec
ms.sourcegitcommit: 42e6cfe51d99d4f3f05a3245829d764b28c46bbb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48741094"
---
# <a name="develop-office-add-ins"></a>Разработка надстроек Office

> [!TIP]
> Перед прочтением этой статьи ознакомьтесь с [обзором платформы надстроек Office](../overview/office-add-ins.md).

Все надстройки Office построены на базе платформы надстроек Office. Для каждой создаваемой надстройки следует понять важные принципы, такие как доступность клиентского приложения и платформы, шаблоны программирования API JavaScript для Office, настройку параметров и возможностей надстройки в файле манифеста, способ разработки пользовательского интерфейса и т. д. Эти основные принципы разработки рассматриваются ниже в разделе документации **Жизненный цикл разработки** > **Разработка**. Ознакомьтесь с этими сведениями перед изучением документации для клиентского приложения, надстройку для которого вы создаете (например, [Excel](../excel/index.yml)).

## <a name="creating-an-office-add-in"></a>Создание надстройки Office

Надстройку Office можно создать с помощью генератора Yeoman для надстроек Office или Visual Studio.

### <a name="yeoman-generator-for-office-add-ins"></a>Генератор Yeoman для надстроек Office

[Генератор Yeoman для надстроек Office](https://github.com/officedev/generator-office) можно использовать для создания проекта надстройки Office Node.js, которым можно управлять с помощью Visual Studio Code или любого другого редактора. В генераторе можно создавать надстройки Office для любой из следующих целей.

- Excel
- OneNote
- Outlook
- PowerPoint
- Project
- Word
- Пользовательские функции Excel

Проект можно создать с помощью HTML, CSS и JavaScript или с помощью Angular или React. Для любой платформы можно также выбирать между JavaScript и Typescript. Дополнительные сведения о создании надстроек с помощью генератора Yeoman см. в статье [Разработка надстроек Office с помощью Visual Studio Code](../develop/develop-add-ins-vscode.md).

### <a name="visual-studio"></a>Visual Studio

С помощью Visual Studio можно создавать надстройки Office для Excel, Outlook, Word и PowerPoint. Проект надстройки Office создается в рамках решения Visual Studio и использует HTML, CSS и JavaScript. Дополнительные сведения о создании надстроек с помощью Visual Studio см. в статье [Разработка надстроек Office с помощью Visual Studio](../develop/develop-add-ins-visual-studio.md).

[!include[Yeoman vs Visual Studio comparison](../includes/yeoman-generator-recommendation.md)]

## <a name="understanding-the-two-parts-of-an-office-add-in"></a>Общие сведения о двух частях надстройки Office

Надстройка Office состоит из двух частей:

- Манифест надстройки (XML-файл), определяющий параметры и возможности надстройки.

- Веб-приложение, определяющее пользовательский интерфейс и функции компонентов надстройки, таких как области задач, контентные надстройки и диалоговые окна.

Веб-приложение использует API JavaScript для Office, чтобы взаимодействовать с содержимым документа Office, в котором запущена надстройка. Надстройка также может выполнять другие типовые действия веб-приложений, например вызовы внешних веб-служб, упрощение проверки подлинности пользователей и т. д.

### <a name="defining-an-add-ins-settings-and-capabilities"></a>Определение параметров и возможностей надстройки

Манифест надстройки Office (XML-файл), определяющий параметры и возможности надстройки. Вы можете настроить манифест, чтобы указать следующие элементы:

- метаданные, описывающие надстройку (например, ИД, версия, описание, отображаемое имя, региональные параметры по умолчанию);
- приложения Office, в которых будет запускаться надстройка;
- разрешения, требующиеся для надстройки;
- способ интеграции надстройки с Office, включая создаваемые ею элементы пользовательского интерфейса (например, настраиваемые вкладки и кнопки на ленте);
- расположение изображений, используемых надстройкой для фирменной символики и значков команд;
- размеры надстройки (например, размеры для контентных надстроек, запрошенная высота для надстроек Outlook);
- правила, определяющие, когда надстройка активируется в контексте сообщения или встречи (только для надстроек Outlook).

Дополнительные сведения о манифесте см. в статье [XML-манифест надстроек Office](add-in-manifests.md).

### <a name="interacting-with-content-in-an-office-document"></a>Взаимодействие с содержимым в документе Office

Надстройка Office может использовать API JavaScript для Office, чтобы взаимодействовать с содержимым документа Office, в котором запущена надстройка.

#### <a name="accessing-the-office-javascript-api-library"></a>Доступ к библиотеке API JavaScript для Office

[!include[information about accessing the Office JS API library](../includes/office-js-access-library.md)]

#### <a name="api-models"></a>Модели API

[!include[information about the Office JS API models](../includes/office-js-api-models.md)]

#### <a name="api-requirement-sets"></a>Наборы обязательных элементов API

[!include[information about the Office JS API requirement sets](../includes/office-js-requirement-sets.md)]

#### <a name="exploring-apis-with-script-lab"></a>Изучение API с помощью Script Lab

Script Lab — это надстройка, позволяющая изучать API JavaScript для Office и выполнять фрагменты кода при работе в программах Office, таких как Excel или Word. Она доступна бесплатно в [AppSource](https://appsource.microsoft.com/product/office/WA104380862) и является полезным инструментом для добавления в набор средств разработки при создании прототипов и проверке нужных функций в надстройке. В Script Lab можно получить доступ к библиотеке встроенных примеров, чтобы быстро испытать API или использовать пример в качестве отправной точки для собственного кода.

В следующем 1-минутном видео показана надстройка Script Lab в действии.

[![Ознакомительное видео, демонстрирующее работу Script Lab в Excel, Word и PowerPoint.](../images/screenshot-wide-youtube.png 'Ознакомительное видео о Script Lab')](https://aka.ms/scriptlabvideo)

Дополнительные сведения о Script Lab см. в статье [Изучение API JavaScript для Office с помощью Script Lab](../overview/explore-with-script-lab.md).

## <a name="extending-the-office-ui"></a>Расширение пользовательского интерфейса Office

Надстройка Office может расширить пользовательский интерфейс Office с помощью команд надстройки и контейнеров HTML, таких как области задач, контентные надстройки и диалоговые окна.

- [Команды надстроек](../design/add-in-commands.md) можно использовать для добавления настраиваемых вкладок, кнопок и меню на стандартную ленту в Office или для расширения стандартного контекстного меню, отображающегося при щелчке правой кнопкой мыши по тексту в документе Office или объекту в Excel. Когда пользователи выбирают команду надстройки, они запускают задачу, определяемую этой командой надстройки, например выполнение кода JavaScript, открытие области задач или запуск диалогового окна.

- Контейнеры HTML, такие как [области задач](../design/task-pane-add-ins.md), [контентные надстройки](../design/content-add-ins.md) и [диалоговые окна](../design/dialog-boxes.md) можно использовать для отображения настраиваемого пользовательского интерфейса и предоставления дополнительных функций в приложении Office. Содержимое и функции каждой области задач, контентной надстройки или диалогового окна зависят от указанной вами веб-страницы. Эти веб-страницы могут использовать API JavaScript для Office с целью взаимодействия с содержимым в документе Office, в котором запущена надстройка, а также могут выполнять другие типовые действия веб-страниц, например вызовы внешних веб-служб, упрощение проверки подлинности пользователей и т. д.

На следующем изображении показана команда надстройки на ленте, область задач справа от документа, диалоговое окно или контентная надстройка поверх документа.

![Изображение с командами надстроек на ленте, областью задач и диалоговым окном в документе Office](../images/add-in-ui-elements.png)

Дополнительные сведения о расширении пользовательского интерфейса Office и разработке интерфейса надстройки см. в статье [Элементы пользовательского интерфейса Office для надстроек Office](../design/interface-elements.md).

## <a name="next-steps"></a>Дальнейшие действия

В этой статье рассмотрены различные способы создания надстроек Office, представлены варианты, которыми надстройка может расширить пользовательский интерфейс Office, описаны наборы API и представлен инструмент Script Lab, полезный при изучении API JavaScript для Office и создании прототипов функций надстроек. После изучения этих ознакомительных сведений рекомендуется продолжить исследование надстроек Office по следующим путям.

### <a name="create-an-office-add-in"></a>Создание надстройки Office

Вы можете быстро создать простую надстройку для Excel, OneNote, Outlook, PowerPoint, Project или Word с помощью [5-минутного краткого руководства по началу работы](/office/dev/add-ins/). Если вы уже ознакомились с кратким руководством и хотите создать более сложную надстройку, воспользуйтесь [учебником](/office/dev/add-ins/).

### <a name="learn-more"></a>Подробнее

Ознакомьтесь с этой документацией, чтобы узнать больше о разработке, тестировании и публикации надстроек Office.

> [!TIP]
> При создании любой надстройки вы можете использовать информацию из раздела [Жизненный цикл разработки](../overview/core-concepts-office-add-ins.md) этой документации, а также сведения из разделов для определенных приложений, соответствующих типу создаваемой надстройки (например, [Excel](../excel/index.yml)).

## <a name="see-also"></a>См. также

- [Обзор платформы надстроек Office](../overview/office-add-ins.md)
- [Сведения о программе для разработчиков Microsoft 365](https://developer.microsoft.com/microsoft-365/dev-program)
- [Проектирование надстроек Office](../design/add-in-design.md)
- [Тестирование и отладка надстроек Office](../testing/test-debug-office-add-ins.md)
- [Публикация надстроек Office](../publish/publish.md)
