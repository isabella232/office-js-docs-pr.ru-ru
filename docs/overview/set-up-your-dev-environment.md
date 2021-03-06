---
title: Настройка среды разработки
description: Настройка среды разработки для создания надстроек Office.
ms.date: 10/14/2020
localization_priority: Normal
ms.openlocfilehash: 644194d7d0da479b13ac09d7e830af53e9a9838e
ms.sourcegitcommit: 42e6cfe51d99d4f3f05a3245829d764b28c46bbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48740835"
---
# <a name="set-up-your-development-environment"></a>Настройка среды разработки

Это руководство поможет вам настроить средства для создания надстроек Office, выполнив следующие краткие руководства по началу. Вам потребуется установить средства из приведенного ниже списка. Если у вас уже есть эти компоненты, вы можете начать краткий запуск, например, на [панели быстрого запуска Excel](../quickstarts/excel-quickstart-react.md).

- Node.js
- npm
- Учетная запись Microsoft 365, включающая версию Office для подписки
- Любой редактор кода

В этом руководстве предполагается, что вы знаете, как использовать средство командной строки. 

## <a name="install-nodejs"></a>Установите Node.js.

Node.js — это среда выполнения JavaScript, вам потребуется разработать современные надстройки Office.

Установите Node.js, [загрузив последнюю рекомендуемую версию со своего веб-сайта](https://nodejs.org). Следуйте инструкциям по установке для вашей операционной системы.

## <a name="install-npm"></a>Установка NPM

NPM — это реестр программного обеспечения с открытым кодом, из которого загружаются пакеты, используемые при разработке надстроек Office.

Чтобы установить NPM, выполните следующую команду в командной строке:

```command&nbsp;line
    npm install npm -g
```

Чтобы проверить, установлен ли у вас NPM, и просмотреть установленную версию, выполните следующую команду в командной строке:

```command&nbsp;line
npm -v
```

Вы можете использовать диспетчер версий узла, чтобы позволить переключаться между несколькими версиями Node.js и NPM, но это не является обязательным. Для получения дополнительных сведений о том, как это сделать, [обратитесь к разделу инструкции NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

## <a name="get-office-365"></a>Получение Office 365

Если у вас еще нет учетной записи Microsoft 365, вы можете оформить бесплатную возобновляемую подписку на Microsoft 365 на 90 дней, присоединившись к [программе для разработчиков Microsoft 365](https://developer.microsoft.com/office/dev-program).

## <a name="install-a-code-editor"></a>Установка редактора кода

Для создания веб-частей можно использовать любой редактор кода или интерфейс IDE, поддерживающий клиентскую разработку, например:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Atom](https://atom.io);
- [Webstorm](https://www.jetbrains.com/webstorm).

## <a name="next-steps"></a>Дальнейшие действия

Попробуйте создать собственную надстройку или воспользоваться лабораториями скриптов, чтобы испытать встроенные примеры.

### <a name="create-an-office-add-in"></a>Создание надстройки Office

Вы можете быстро создать простую надстройку для Excel, OneNote, Outlook, PowerPoint, Project или Word с помощью [5-минутного краткого руководства по началу работы](/office/dev/add-ins/). Если вы уже ознакомились с кратким руководством и хотите создать более сложную надстройку, воспользуйтесь [учебником](/office/dev/add-ins/).

### <a name="explore-the-apis-with-script-lab"></a>Изучение API с помощью Script Lab

Изучите библиотеку встроенных примеров в [Script Lab](explore-with-script-lab.md), чтобы ознакомиться с возможностями API JavaScript для Office.

## <a name="see-also"></a>См. также

- [Основные принципы надстроек Office](../overview/core-concepts-office-add-ins.md)
- [Разработка надстроек Office](../develop/develop-overview.md)
- [Проектирование надстроек Office](../design/add-in-design.md)
- [Тестирование и отладка надстроек Office](../testing/test-debug-office-add-ins.md)
- [Публикация надстроек Office](../publish/publish.md)
- [Сведения о программе для разработчиков Microsoft 365](https://developer.microsoft.com/microsoft-365/dev-program)
