---
title: Загрузка модели DOM и среды выполнения
description: Загрузка среды выполнения надстроек DOM и надстроек Office
ms.date: 04/22/2020
localization_priority: Normal
ms.openlocfilehash: 02f950ca23d52b333f704c7d8aed431cb426a6f0
ms.sourcegitcommit: 9609bd5b4982cdaa2ea7637709a78a45835ffb19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "47293277"
---
# <a name="loading-the-dom-and-runtime-environment"></a>Загрузка модели DOM и среды выполнения

Перед запуском собственной логики надстройка должна проверить, что загружены модель DOM и среда выполнения Надстройки Office.

## <a name="startup-of-a-content-or-task-pane-add-in"></a>Запуск контентной надстройки или надстройки области задач

На рисунке ниже приведен поток событий, происходящих при запуске контентной надстройки или надстройки области задач в Excel, PowerPoint, Project или Word.

![Поток событий при запуске контентной надстройки или надстройки области задач](../images/office15-app-sdk-loading-dom-agave-runtime.png)

При запуске контентной надстройки или надстройки области задач возникают указанные ниже события.

1. Пользователь открывает документ, который уже содержит надстройку, или вставляет надстройку в документ.

2. Клиентское приложение Office считывает XML-манифест надстройки из AppSource, каталога приложений в SharePoint или каталога общих папок, от которого он создан.

3. Клиентское приложение Office открывает HTML-страницу надстройки в элементе управления браузера.

    Следующие два действия, 4 и 5, выполняются одновременно и параллельно. Поэтому код надстройки перед обработкой должен убедиться, что и модель DOM, и среда выполнения надстройки полностью загрузились.

4. Элемент управления браузером загружает DOM и основной текст HTML и вызывает обработчик события для `window.onload` события.

5. Клиентское приложение Office загружает среду выполнения, которая загружает и кэширует файлы библиотеки API JavaScript для Office из сервера сети распространения содержимого (CDN), а затем вызывает обработчик событий надстройки для события [Initialize](/javascript/api/office#office-initialize-reason-) объекта [Office](/javascript/api/office) , если ему назначен обработчик. В это время также проверяется, выполнялась ли передача (или связывание) любых обратных вызовов (или связанных функций `then()`) обработчику `Office.onReady`. Для получения дополнительных сведений о различии между `Office.initialize` и `Office.onReady` см [Initialize your add-in](initialize-add-in.md).

6. После завершения загрузки DOM и основного текста HTML и инициализации надстройки запускается основная функция надстройки.


## <a name="startup-of-an-outlook-add-in"></a>Запуск надстройки Outlook

На рисунке ниже приведен поток событий при запуске надстройки Outlook на настольном компьютере, планшетном ПК или смартфоне.

![Поток событий при запуске надстройки Outlook](../images/outlook15-loading-dom-agave-runtime.png)

При запуске надстройки Outlook происходят указанные ниже события.

1. При запуске Outlook считывает XML-манифесты надстроек Outlook, установленных для учетной записи пользователя.

2. Пользователь выбирает элемент в Outlook.

3. Если выбранный элемент удовлетворяет условиям активации надстройки Outlook, то Outlook активирует надстройку и делает соответствующую кнопку видимой в пользовательском интерфейсе.

4. Если пользователь нажимает кнопку для запуска надстройки Outlook, то ведущее приложение открывает HTML-страницу в элементе управления браузером. Следующие два шага, шаг 5 и шаг 6, выполняются одновременно.

5. Элемент управления браузером загружает DOM и основной текст HTML и вызывает обработчик события для `onload` события.

6. Outlook загружает среду выполнения, которая загружает и кэширует API JavaScript для файлов библиотеки JavaScript с сервера сети доставки содержимого, а затем вызывает обработчик события [инициализации](/javascript/api/office#office-initialize-reason-) объекта [Office](/javascript/api/office) надстройки, если ему назначен обработчик. В это время также проверяется, выполнялась ли передача (или связывание) любых обратных вызовов (или связанных функций `then()`) обработчику `Office.onReady`. Для получения дополнительных сведений о различии между `Office.initialize` и `Office.onReady` см [Initialize your add-in](initialize-add-in.md).

7. После завершения загрузки DOM и основного текста HTML и инициализации надстройки запускается основная функция надстройки.


## <a name="checking-the-load-status"></a>Проверка состояния загрузки

Одним из способов проверки завершения загрузки DOM и среды выполнения надстроек является использование функции [.ready()](https://api.jquery.com/ready/) jQuery — `$(document).ready()`. Например, следующий `onReady` обработчик событий гарантирует, что модель DOM сначала загружается, прежде чем будет запущен код, предназначенный для инициализации надстройки. Затем `onReady` обработчик продолжает использовать свойство [Mailbox. Item](/javascript/api/outlook/office.mailbox#item) для получения выбранного в данный момент элемента в Outlook и вызывает основную функцию надстройки `initDialer` .

```js
Office.onReady()
    .then(
        // Checks for the DOM to load.
        $(document).ready(function () {
            // After the DOM is loaded, add-in-specific code can run.
            var mailbox = Office.context.mailbox;
            _Item = mailbox.item;
            initDialer();
        });
);
```

Кроме того, вы можете использовать один и тот же код в `initialize` обработчике событий, как показано в следующем примере.

```js
Office.initialize = function () {
    // Checks for the DOM to load.
    $(document).ready(function () {
        // After the DOM is loaded, add-in-specific code can run.
        var mailbox = Office.context.mailbox;
        _Item = mailbox.item;
        initDialer();
    });
}
```

Этот же метод можно использовать в `onReady` `initialize` обработчиках или в обработчиках любой надстройки Office.

В примере надстройки Outlook "Телефон" показан несколько другой подход, использующий только JavaScript для проверки тех же условий.

> [!IMPORTANT]
> Даже если у надстройки нет задач инициализации, необходимо включить по крайней мере вызов `Office.onReady` или назначить минимальную `Office.initialize` функцию обработчика событий, как показано в следующих примерах.
>
>```js
>Office.onReady();
>```
>
>```js
>Office.initialize = function () {};
>```
>
> Если не вызвать `Office.onReady` или назначить `Office.initialize` обработчик события, надстройка может вызвать ошибку при запуске. Кроме того, если пользователь попробует использовать надстройку с веб-клиентом Office, например Excel, PowerPoint или Outlook, произойдет сбой.
>
> Если надстройка содержит несколько страниц, при загрузке новой страницы, которая должна вызываться `Office.onReady` или назначить `Office.initialize` обработчик событий.

## <a name="see-also"></a>См. также

- [Общие сведения об API JavaScript для Office](understanding-the-javascript-api-for-office.md)
- [Инициализация надстройки Office](initialize-add-in.md)
