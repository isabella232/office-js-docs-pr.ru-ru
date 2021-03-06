---
title: Предварительная версия набора обязательных элементов API для надстройки Outlook
description: Функции и API, которые в настоящее время находятся в режиме предварительной версии для надстроек Outlook.
ms.date: 10/14/2020
localization_priority: Normal
ms.openlocfilehash: d91105e0cfbb97dc1a239e40b1c81adc4e76988b
ms.sourcegitcommit: 4e7c74ad67ea8bf6b47d65b2fde54a967090f65b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626598"
---
# <a name="outlook-add-in-api-preview-requirement-set"></a>Предварительная версия набора обязательных элементов API для надстройки Outlook

Подмножество API надстройки Outlook в API JavaScript для Office включает объекты, методы, свойства и события, которые можно использовать в надстройке Outlook.

> [!IMPORTANT]
> Эта документация относится к **предварительной версии** [набора обязательных элементов](../../requirement-sets/outlook-api-requirement-sets.md). Этот набор обязательных элементов еще не полностью реализован, а клиенты будут неправильно сообщать о его поддержке. Не следует указывать этот набор обязательных элементов в манифесте надстройки.

[!INCLUDE [Information about using preview APIs](../../../includes/using-preview-apis-host.md)]

> [!TIP]
> Вы можете предварительно просмотреть функции в Outlook в Интернете, [настроив целевой выпуск на клиенте Microsoft 365](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center). "Настройка предварительного доступа" отмечено на этой странице в соответствующих возможностях.
>
> Для других функций вы можете запросить доступ к предварительной версии BITS для Outlook в Интернете, используя свою учетную запись Microsoft 365, заполнив и отправив [эту форму](https://aka.ms/OWAPreview). В этих функциях указано "запросить доступ к предварительному доступу".

Набор требований Preview включает все компоненты набора обязательных элементов [1,9](../requirement-set-1.9/outlook-requirement-set-1.9.md).

## <a name="features-in-preview"></a>Возможности предварительной версии

Ниже перечислены возможности предварительной версии.

### <a name="add-in-activation-on-items-protected-by-information-rights-management-irm"></a>Активация надстройки для элементов, защищенных службой управления правами на доступ к данным (IRM)

Теперь надстройки можно активировать на элементах, защищенных с помощью управления правами на доступ к данным. Чтобы включить эту возможность, администратору клиента необходимо включить `OBJMODEL` право на использование, установив параметр **Разрешить программный доступ к** настраиваемой политике в Office. Для получения дополнительных сведений ознакомьтесь [с разрешениями и описаниями использования](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) .

**Доступно в**: Outlook в Windows, начиная с сборки 13229,10000 (подключены к подписке Microsoft 365).

<br>

---

---

### <a name="additional-calendar-properties"></a>Дополнительные свойства календаря

#### <a name="isalldayevent"></a>[IsAllDayEvent](/javascript/api/outlook/office.isalldayevent?view=outlook-js-preview&preserve-view=true)

Добавлен новый объект, представляющий свойство события "целый день" для встречи в режиме создания.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="sensitivity"></a>[Sensitivity](/javascript/api/outlook/office.sensitivity?view=outlook-js-preview&preserve-view=true)

Добавлен новый объект, представляющий чувствительность встречи в режиме создания.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="officecontextmailboxitemisalldayevent"></a>[Office. Context. Mailbox. Item. Исаллдайевент](office.context.mailbox.item.md#properties)

Добавлено новое свойство, которое указывает, является ли встреча событием на целый день.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="officecontextmailboxitemsensitivity"></a>[Office. Context. Mailbox. Item. чувствительность](office.context.mailbox.item.md#properties)

Добавлено новое свойство, представляющее чувствительность встречи.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="officemailboxenumsappointmentsensitivitytype"></a>[Office. MailboxEnums. Аппоинтментсенситивититипе](/javascript/api/outlook/office.mailboxenums.appointmentsensitivitytype?view=outlook-js-preview&preserve-view=true)

Добавлено новое перечисление `AppointmentSensitivityType` , представляющее параметры конфиденциальности, доступные для встречи.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

<br>

---

---

### <a name="event-based-activation"></a>Активация на основе событий

Добавлена поддержка функций активации на основе событий в надстройках Outlook. Чтобы узнать больше, ознакомьтесь со статьей [Настройка надстройки Outlook для активации на основе событий](../../../outlook/autolaunch.md) .

#### <a name="launchevent-extension-point"></a>[Точка расширения Лаунчевент](../../manifest/extensionpoint.md#launchevent-preview)

Добавлена `LaunchEvent` Поддержка точек расширения для манифеста. Он настраивает функции активации на основе событий.

**Доступно в**: Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="launchevents-manifest-element"></a>[Элемент манифеста Лаунчевентс](../../manifest/launchevents.md)

Добавлен `LaunchEvents` элемент для манифеста. Он поддерживает настройку функций активации на основе событий.

**Доступно в**: Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="runtimes-manifest-element"></a>[Элемент манифеста среды выполнения](../../manifest/runtimes.md)

Добавлена поддержка Outlook для `Runtimes` элемента manifest. Он ссылается на HTML-и JavaScript-файлы, необходимые для функции активации на основе событий.

**Доступно в**: Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

<br>

---

---

### <a name="integration-with-actionable-messages"></a>Взаимодействие с интерактивными сообщениями

#### <a name="officecontextmailboxitemgetinitializationcontextasync"></a>[Office.context.mailbox.item.getInitializationContextAsync](office.context.mailbox.item.md#methods)

Добавлена новая функция, которая возвращает данные инициализации, передаваемые при [активации надстройки интерактивным сообщением](/outlook/actionable-messages/invoke-add-in-from-actionable-message).

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (классическая)

<br>

---

---

### <a name="mail-signature"></a>Подпись почты

#### <a name="officecontextmailboxitembodysetsignatureasync"></a>[Office. Context. Mailbox. Item. Body. Сетсигнатуреасинк](/javascript/api/outlook/office.body?view=outlook-js-preview&preserve-view=true#setsignatureasync-data--options--callback-)

Добавлена новая функция для `Body` объекта, который добавляет или заменяет подпись в теле элемента в режиме создания.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="officecontextmailboxitemdisableclientsignatureasync"></a>[Office. Context. Mailbox. Item. Дисаблеклиентсигнатуреасинк](office.context.mailbox.item.md#methods)

Добавлена новая функция, которая отключает подпись клиента для отправляющего почтового ящика в режиме создания.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="officecontextmailboxitemgetcomposetypeasync"></a>[Office. Context. Mailbox. Item. Жеткомпосетипеасинк](/javascript/api/outlook/office.messagecompose?view=outlook-js-preview&preserve-view=true#getcomposetypeasync-options--callback-)

Добавлена новая функция, которая получает тип сообщения "создание" в режиме создания.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="officecontextmailboxitemisclientsignatureenabledasync"></a>[Office. Context. Mailbox. Item. Исклиентсигнатуринабледасинк](office.context.mailbox.item.md#methods)

Добавлена новая функция, проверяющая, включена ли подпись клиента для элемента в режиме создания.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

#### <a name="officemailboxenumscomposetype"></a>[Office. MailboxEnums. Компосетипе](/javascript/api/outlook/office.mailboxenums.composetype?view=outlook-js-preview&preserve-view=true)

Добавлено новое перечисление `ComposeType` , доступное в режиме создания.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современная, [Настройка предварительного доступа](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true#set-up-the-release-option-in-the-admin-center))

<br>

---

---

### <a name="notification-messages-with-actions"></a>Сообщения уведомления с действиями

Эта функция позволяет надстройке включать сообщение уведомления с дополнительным **действием, кроме действия по** умолчанию.

#### <a name="officenotificationmessagedetailsactions"></a>[Office. NotificationMessageDetails. Actions](/javascript/api/outlook/office.notificationmessagedetails#actions)

Добавлено новое свойство, которое позволяет добавить `InsightMessage` уведомление с дополнительным действием.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современный)

#### <a name="officenotificationmessageaction"></a>[Office. Нотификатионмессажеактион](/javascript/api/outlook/office.notificationmessageaction)

Добавлен новый объект, в котором определяется дополнительное действие для `InsightMessage` уведомления.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современный)

#### <a name="officemailboxenumsactiontype"></a>[Office. MailboxEnums.](/javascript/api/outlook/office.mailboxenums.actiontype)

Добавлено новое перечисление `ActionType` .

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современный)

#### <a name="officemailboxenumsitemnotificationmessagetypeinsightmessage"></a>[Office. MailboxEnums. Итемнотификатионмессажетипе. Инсигхтмессаже](/javascript/api/outlook/office.mailboxenums.itemnotificationmessagetype)

Добавлен новый тип `InsightMessage` в `ItemNotificationMessageType` перечисление.

**Доступно в**: Outlook в Windows (подключенном к подписке Microsoft 365), Outlook в Интернете (современный)

<br>

---

---

### <a name="office-theme"></a>Тема Office

#### <a name="officecontextofficetheme"></a>[Office.context.officeTheme](/javascript/api/office/office.context#officetheme)

Добавлена возможность получения темы Office.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="officeeventtypeofficethemechanged"></a>[Office.EventType.OfficeThemeChanged](/javascript/api/office/office.eventtype)

Добавлено событие `OfficeThemeChanged` для объекта `Mailbox`.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

<br>

---

---

### <a name="session-data"></a>Данные сеансов

#### <a name="officesessiondata"></a>[Office. Сессиондата](/javascript/api/outlook/office.sessiondata)

Добавлен новый объект, представляющий данные сеанса для элемента.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

#### <a name="officecontextmailboxitemsessiondata"></a>[Office. Context. Mailbox. Item. Сессиондата](office.context.mailbox.item.md#properties)

Добавлено новое свойство для управления данными сеанса элемента в режиме создания.

**Доступно в**: Outlook в Windows (подключено к подписке Microsoft 365)

## <a name="see-also"></a>См. также

- [Надстройки Outlook](../../../outlook/outlook-add-ins-overview.md)
- [Примеры кода надстройки Outlook](https://developer.microsoft.com/outlook/gallery/?filterBy=Outlook,Samples,Add-ins)
- [Начало работы](../../../quickstarts/outlook-quickstart.md)
- [Наборы обязательных элементов и поддерживаемые клиенты](../../requirement-sets/outlook-api-requirement-sets.md)
