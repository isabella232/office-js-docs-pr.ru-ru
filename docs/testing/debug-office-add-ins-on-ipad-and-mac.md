---
title: Отладка надстроек Office на Mac
description: Узнайте, как использовать Mac для отладки надстроек Office
ms.date: 11/26/2019
localization_priority: Normal
ms.openlocfilehash: 12785a195c336e0de8c619379a3839bd15079b2c
ms.sourcegitcommit: 7ef14753dce598a5804dad8802df7aaafe046da7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094129"
---
# <a name="debug-office-add-ins-on-a-mac"></a>Отладка надстроек Office на Mac

Так как надстройки создаются с помощью кода HTML и JavaScript, они рассчитаны на работу на многих платформах, но отрисовка HTML в разных браузерах может слегка отличаться. В этой статье описывается отладка надстроек на компьютере Mac.

## <a name="debugging-with-safari-web-inspector-on-a-mac"></a>Отладка с помощью Safari Web Inspector на компьютере Mac

Если у вас есть надстройка, которая отображает пользовательский интерфейс в области задач или контентной надстройке, вы можете отлаживать надстройку Office с помощью Safari Web Inspector.

Отладку надстроек Office на компьютере Mac можно выполнить, только если на нем установлена система Mac OS High Sierra И Office для Mac версии 16.9.1 (сборка 18012504) или более поздней. Если у вас нет сборки Office Mac, вы можете получить ее, присоединяясь к [программе для разработчиков Microsoft 365](https://developer.microsoft.com/office/dev-program).

Для этого откройте терминал и установите свойство `OfficeWebAddinDeveloperExtras` для соответствующего приложения Office следующим образом:

- `defaults write com.microsoft.Word OfficeWebAddinDeveloperExtras -bool true`

- `defaults write com.microsoft.Excel OfficeWebAddinDeveloperExtras -bool true`

- `defaults write com.microsoft.Powerpoint OfficeWebAddinDeveloperExtras -bool true`

- `defaults write com.microsoft.Outlook OfficeWebAddinDeveloperExtras -bool true`

Затем откройте приложение Office и [загрузите свою неопубликованную надстройку](sideload-an-office-add-in-on-ipad-and-mac.md). Щелкните надстройку правой кнопкой мыши. В контекстном меню отобразится пункт **Проверить элемент**. Выберите его. Он появится в инспекторе, где можно устанавливать точки останова и отлаживать надстройку.

> [!NOTE]
> Если при попытке использовать инспектор диалоговое окно мерцает, обновите Office до последней версии. Если проблема с мерцанием сохраняется, попробуйте применить следующее временное решение:
> 1. Уменьшите размер диалогового окна.
> 2. Выберите пункт **Проверить элемент**, который откроется в новом окне.
> 3. Измените размер диалогового окна на исходный.
> 4. Используйте инспектор должным образом.

## <a name="clearing-the-office-applications-cache-on-a-mac"></a>Очистка кэша приложения Office на компьютере Mac

[!include[additional cache folders on Mac](../includes/mac-cache-folders.md)]
