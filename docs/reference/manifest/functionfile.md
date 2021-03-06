---
title: Элемент FunctionFile в файле манифеста
description: Указывает файл исходного кода для операций, предоставляемых надстройкой через команды надстройки, которые выполняют функцию JavaScript вместо отображения пользовательского интерфейса.
ms.date: 11/06/2020
localization_priority: Normal
ms.openlocfilehash: 4c47c3e4b824f2b93aaea17cef88e01f748d6f95
ms.sourcegitcommit: ca66ff7462bfdf4ed7ae04f43d1388c24de63bf9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996447"
---
# <a name="functionfile-element"></a>Элемент FunctionFile

Указывает файл исходного кода для операций, предоставляемых надстройкой, одним из следующих способов:

* Команды надстройки, которые выполняют функцию JavaScript вместо отображения пользовательского интерфейса.
* Сочетания клавиш, которые выполняют функцию JavaScript.

`FunctionFile`Элемент является дочерним для элемента [DesktopFormFactor](desktopformfactor.md) или [MobileFormFactor](mobileformfactor.md). `resid` `FunctionFile` Для атрибута элемента задается значение `id` атрибута `Url` элемента в `Resources` элементе, который содержит URL-адрес HTML-файла, который содержит или загружает все функции JavaScript, которые используются КНОПКАМИ надстройки без пользовательского интерфейса, как определено [элементом Control](control.md).

Ниже приведен пример `FunctionFile` элемента.

```XML
<DesktopFormFactor>
  <FunctionFile resid="residDesktopFuncUrl" />
  <ExtensionPoint xsi:type="PrimaryCommandSurface">
    <!-- information about this extension point -->
  </ExtensionPoint>

  <!-- You can define more than one ExtensionPoint element as needed -->

</DesktopFormFactor>
```

JavaScript в HTML-файле, указанном `FunctionFile` элементом, должен вызывать `Office.initialize` и определять именованные функции, которые принимают один параметр: `event` . Функции должны использовать API `item.notificationMessages`, чтобы сообщать пользователю о ходе выполнения, успешном завершении или ошибке. Он также должен вызывать метод `event.completed` после выполнения. Имя функции используется в `FunctionName` элементе для кнопок без пользовательского интерфейса.

Ниже приведен пример HTML-файла, определяющего `trackMessage` функцию.

```js
Office.initialize = function () {
    doAuth();
}

function trackMessage (event) {
    var buttonId = event.source.id;    
    var itemId = Office.context.mailbox.item.id;
    // save this message
    event.completed();
}
```

В приведенном ниже коде показано, как реализовать функцию, используемую в `FunctionName` .

```js
// The initialize function must be run each time a new page is loaded.
(function () {
    Office.initialize = function (reason) {
        // If you need to initialize something you can do so here.
    };
})();

// Your function must be in the global namespace.
function writeText(event) {

    // Implement your custom code here. The following code is a simple example.

    Office.context.document.setSelectedDataAsync("ExecuteFunction works. Button ID=" + event.source.id,
        function (asyncResult) {
            var error = asyncResult.error;
            if (asyncResult.status === "failed") {
                // Show error message.
            }
            else {
                // Show success message.
            }
        });
    // Calling event.completed is required. event.completed lets the platform know that processing has completed.
    event.completed();
}
```

> [!IMPORTANT]
> Вызов `event.completed` , сигнализирующий о том, что событие успешно обработано. Если функция вызывается несколько раз, например при выборе одной команды надстройки несколько раз, все события автоматически помещаются в очередь. Первое событие запускается автоматически, тогда как остальные ожидают в очереди. При вызове функции `event.completed` выполняется следующий вызов этой функции в очереди. Необходимо позвонить `event.completed` ; в противном случае функция не будет запускаться.
