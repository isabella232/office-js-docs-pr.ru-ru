---
title: Правила активации для надстроек Outlook
description: Outlook активирует некоторые типы надстроек, если сообщение или сведения о встрече, которые читает или создает пользователь, соответствуют правилам активации надстройки.
ms.date: 09/22/2020
localization_priority: Normal
ms.openlocfilehash: cdcdfbf3961ad9f627ba00f7366f49c77bba435d
ms.sourcegitcommit: fd110305c2be8660ab8a47c1da3e3969bd1ede86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214598"
---
# <a name="activation-rules-for-contextual-outlook-add-ins"></a>Правила активации контекстных надстроек Outlook

Outlook активирует некоторые типы надстроек, если сообщение или сведения о встрече, которые читает или создает пользователь, соответствуют правилам активации надстройки. Это верно для всех надстроек, для которых используется схема манифеста 1.1. Затем пользователь может выбрать надстройку из пользовательского интерфейса Outlook, чтобы запустить ее для текущего элемента.

На следующем изображении показаны надстройки Outlook, активируемые в области надстройки для сообщения в области чтения.

![Панель приложения, на которой указаны почтовые приложения, активированные в форме чтения](../images/read-form-app-bar.png)


## <a name="specify-activation-rules-in-a-manifest"></a>Указание правил активации в манифесте


Чтобы надстройка активировалась в Outlook для определенных условий, укажите правила активации в манифесте надстройки, используя один из следующих `Rule` элементов:

- [элемент Rule (MailApp complexType)](../reference/manifest/rule.md), задающий отдельное правило;
- [Элемент Rule (RuleCollection complexType)](../reference/manifest/rule.md#rulecollection), совмещающий несколько правил с помощью логических операторов.
    

 > [!NOTE]
 > `Rule`Элемент, используемый для указания отдельного правила, относится к сложному типу абстрактного [правила](../reference/manifest/rule.md) . Каждый из следующих типов правил расширяет этот абстрактный `Rule` сложный тип. Следовательно, указывая отдельное правило в манифесте, необходимо использовать атрибут [xsi:type](https://www.w3.org/TR/xmlschema-1/), чтобы определить один из перечисленных ниже типов правил.
 > 
 > Например, следующее правило определяет правило[ItemIs](../reference/manifest/rule.md#itemis-rule): `<Rule xsi:type="ItemIs" ItemType="Message" />`
 > 
 > `FormType`Атрибут применяется к правилам активации в манифесте версии 1.1, но не определен в `VersionOverrides` версии 1.0. Поэтому его нельзя использовать, если в узле используется [элемент](../reference/manifest/rule.md#itemis-rule) `VersionOverrides` .

В таблице ниже перечислены доступные типы элементов. Дополнительные сведения см. под таблицей и в статьях, перечисленных в статье [Создание надстроек Outlook для форм чтения](read-scenario.md).

<br/>

|**Имя правила**|**Применимые формы**|**Описание**|
|:-----|:-----|:-----|
|[ItemIs](#itemis-rule)|Чтение, создание|Проверяет, относится ли текущий элемент к определенному типу (сообщение или встреча). Кроме того, оно может проверять класс элемента, тип формы и, при необходимости, класс сообщения элемента.|
|[ItemHasAttachment](#itemhasattachment-rule)|Чтение|Проверяет, содержит ли выделенный элемент вложение.|
|[ItemHasKnownEntity](#itemhasknownentity-rule)|Чтение|Проверяет, содержит ли выделенный элемент одну или несколько известных сущностей. Дополнительные сведения см. в статье [Сопоставление строк в элементе Outlook как известных сущностей](match-strings-in-an-item-as-well-known-entities.md).|
|[ItemHasRegularExpressionMatch](#itemhasregularexpressionmatch-rule)|Чтение|Проверяет, содержит ли адрес электронной почты отправителя, тема и/или тело выбранного элемента совпадение с регулярным выражением. Подробнее: [Использование регулярных правил активации выражений для отображения надстройки Outlook](use-regular-expressions-to-show-an-outlook-add-in.md).|
|[RuleCollection](#rulecollection-rule)|Чтение, создание|Объединяет набор правил, чтобы можно было создавать более сложные правила.|

## <a name="itemis-rule"></a>Правило ItemIs

Сложный тип **ItemIs** определяет правило, которое имеет значение **true**, если текущий элемент совпадает с типом элемента и (необязательно) с классом сообщения элемента (если он указан в правиле).

Укажите один из следующих типов элементов в `ItemType` атрибуте "правило **элемента** ". В манифесте можно указать несколько правил **ItemIs**. Значение simpleType атрибута ItemType определяет типы элементов Outlook, поддерживающих надстройки Outlook.

<br/>

|**Value**|**Описание**|
|:-----|:-----|
|**Встреча**|Указывает элемент в календаре Outlook. Это может быть элемент собрания, для которого был отправлен ответ и у которого есть организатор и участники, или встреча без организатора или участника, которая просто представляет собой элемент календаря. Соответствует классу сообщений IPM.Appointment в Outlook.|
|**Сообщение**|Указывает один из приведенных ниже элементов, обычно поступающих в папку "Входящие". <ul><li><p>Сообщение электронной почты. Соответствует классу сообщений IPM.Note в Outlook.</p></li><li><p>Запрос на собрание, ответ или отклонение. Соответствует следующим классам сообщений в Outlook:</p><p>IPM.Schedule.Meeting.Request</p><p>IPM.Schedule.Meeting.Neg</p><p>IPM.Schedule.Meeting.Pos</p><p>IPM.Schedule.Meeting.Tent</p><p>IPM.Schedule.Meeting.Canceled</p></li></ul>|

`FormType`Атрибут используется для указания режима (чтение или создание), в котором должна быть активирована надстройка.


 > [!NOTE]
 > `FormType`Атрибут Item определен в схеме версии 1.1 и более поздних версиях, но не в `VersionOverrides` версии 1.0. Не включайте `FormType` атрибут при определении команд надстройки.

После активации надстройки можно использовать свойство [mailbox.item](../reference/objectmodel/preview-requirement-set/office.context.mailbox.item.md) для получения элемента, выбранного в текущий момент в Outlook, и свойство [item.itemType](../reference/objectmodel/preview-requirement-set/office.context.mailbox.item.md#properties) для получения типа текущего элемента.

При необходимости можно использовать атрибут, `ItemClass` чтобы указать класс сообщения для элемента, а также `IncludeSubClasses` атрибут, указывающий, должно ли правило выполняться, если **true** элемент является подклассом указанного класса.

Дополнительные сведения о классах сообщений см. в статье [Типы элементов и классы сообщений](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).

В приведенном ниже примере показано правило **ItemIs**, которое отображает надстройку на панели надстройки Outlook, когда пользователь просматривает сообщение.

```xml
<Rule xsi:type="ItemIs" ItemType="Message" FormType="Read" />
```

В приведенном ниже примере показано правило **ItemIs**, которое отображает надстройку на панели надстройки Outlook, когда пользователь просматривает сообщение или встречу.

```xml
<Rule xsi:type="RuleCollection" Mode="Or">
  <Rule xsi:type="ItemIs" ItemType="Message" FormType="Read" />
  <Rule xsi:type="ItemIs" ItemType="Appointment" FormType="Read" />
</Rule>
```


## <a name="itemhasattachment-rule"></a>Правило ItemHasAttachment


`ItemHasAttachment`Сложный тип определяет правило, которое проверяет, содержит ли выделенный элемент вложение.

```xml
<Rule xsi:type="ItemHasAttachment" />
```


## <a name="itemhasknownentity-rule"></a>Правило ItemHasKnownEntity

Чтобы сделать элемент доступным для надстройки, сервер проверяет его, чтобы определить, содержит ли тема и основной текст какой-либо текст, который может быть одной из известных сущностей. Если найдена какая-либо из этих сущностей, она помещается в коллекцию известных сущностей, доступ к которым осуществляется с помощью `getEntities` метода или этого `getEntitiesByType` элемента.

Вы можете указать правило, используя `ItemHasKnownEntity` этот параметр, чтобы отобразить надстройку, когда в элементе присутствует сущность указанного типа. В атрибуте правила можно указать следующие известные сущности `EntityType` `ItemHasKnownEntity` :

- Address
- Contact
- EmailAddress
- MeetingSuggestion
- PhoneNumber
- TaskSuggestion
- URL-адрес
    
При необходимости можно включить регулярное выражение в атрибут, `RegularExpression` чтобы надстройка отображалась только тогда, когда присутствует сущность, соответствующая регулярному выражению. Для получения соответствий регулярным выражениям, указанным в `ItemHasKnownEntity` правилах, можно `getRegExMatches` использовать `getFilteredEntitiesByName` метод или для выбранного в данный момент элемента Outlook.

В следующем примере показана коллекция `Rule` элементов, которые отображают надстройку, когда одна из указанных хорошо известных сущностей присутствует в сообщении.

```xml
<Rule xsi:type="RuleCollection" Mode="Or">
    <Rule xsi:type="ItemHasKnownEntity" EntityType="Address" />
    <Rule xsi:type="ItemHasKnownEntity" EntityType="MeetingSuggestion" />
    <Rule xsi:type="ItemHasKnownEntity" EntityType="TaskSuggestion" />
</Rule>
```

В приведенном ниже примере показано `ItemHasKnownEntity` правило с `RegularExpression` атрибутом, которое активирует надстройку, когда в сообщении присутствует URL-адрес, содержащий слово "contoso".


```xml
<Rule xsi:type="ItemHasKnownEntity" EntityType="Url" RegularExpression="contoso" />
```

Дополнительные сведения о сущностях в правилах активации см. в статье [Сопоставление строк в элементе Outlook как известных сущностей](match-strings-in-an-item-as-well-known-entities.md).


## <a name="itemhasregularexpressionmatch-rule"></a>Правило ItemHasRegularExpressionMatch

`ItemHasRegularExpressionMatch`Сложный тип определяет правило, которое использует регулярное выражение для сравнения содержимого указанного свойства элемента. Если текст, соответствующий регулярному выражению, находится в указанном свойстве элемента, Outlook активирует панель надстройки и отображает надстройку. Можно использовать `getRegExMatches` `getRegExMatchesByName` метод или объекта, который представляет выбранный в данный момент элемент, чтобы получить совпадения для указанного регулярного выражения.

В следующем примере показана надстройка `ItemHasRegularExpressionMatch` , которая активирует надстройку, когда текст выбранного элемента содержит "Apple", "" "," в "," Coconut ", или" ", игнорируя регистр.

```xml
<Rule xsi:type="ItemHasRegularExpressionMatch" RegExName="fruits" RegExValue="apple|banana|coconut" PropertyName="BodyAsPlaintext" IgnoreCase="true" />
```

Дополнительные сведения об использовании `ItemHasRegularExpressionMatch` правила приведены [в статье Использование правил активации регулярных выражений для отображения надстройки Outlook](use-regular-expressions-to-show-an-outlook-add-in.md).


## <a name="rulecollection-rule"></a>Правило RuleCollection


`RuleCollection`Сложный тип сочетает несколько правил с одним правилом. Вы можете указать, будут ли правила в коллекции объединяться с логическим или логическим оператором AND с помощью `Mode` атрибута.

Если указан логический оператор "И", то для отображения надстройки элемент должен соответствовать всем заданным правилам в коллекции. Если выбран логический оператор "ИЛИ", надстройка будет отображаться при наличии элемента, соответствующего любому из заданных правил в коллекции.

Вы можете комбинировать `RuleCollection` правила для создания сложных правил. Следующий пример активирует надстройку, когда пользователь просматривает встречу или элемент сообщения, а тема или текст элемента содержит адрес.

```xml
<Rule xsi:type="RuleCollection" Mode="And">
  <Rule xsi:type="RuleCollection" Mode="Or">
    <Rule xsi:type="ItemIs" ItemType="Message" FormType="Read" />
    <Rule xsi:type="ItemIs" ItemType="Appointment" FormType="Read"/>
  </Rule>
  <Rule xsi:type="ItemHasKnownEntity" EntityType="Address" />
</Rule>
```

Следующий пример активирует надстройку, если пользователь создает сообщение или просматривает встречу, а тема или основной текст встречи содержит адрес.

```xml
<Rule xsi:type="RuleCollection" Mode="Or"> 
  <Rule xsi:type="ItemIs" ItemType="Message" FormType="Edit" /> 
  <Rule xsi:type="RuleCollection" Mode="And">
    <Rule xsi:type="ItemIs" ItemType="Appointment" FormType="Read" />
    <Rule xsi:type="ItemHasKnownEntity" EntityType="Address" />
  </Rule> 
</Rule>
```


## <a name="limits-for-rules-and-regular-expressions"></a>Ограничения для правил и регулярных выражений


Чтобы обеспечить удовлетворительную работу с надстройками Outlook, необходимо следовать рекомендациям по активации и использованию API. В следующей таблице показаны общие пределы для регулярных выражений и правил, но существуют определенные правила для разных приложений. Дополнительные сведения см. в разделе [Limits for Activation и API JavaScript для надстроек Outlook](limits-for-activation-and-javascript-api-for-outlook-add-ins.md) и [Устранение неполадок активации надстроек Outlook](troubleshoot-outlook-add-in-activation.md).

<br/>

|**Элемент надстройки**|**Рекомендации**|
|:-----|:-----|
|Размер манифеста|Не более 256 КБ.|
|Правила|Не более 15 правил.|
|ItemHasKnownEntity|Полнофункциональный клиент Outlook применит правило к первому мегабайту основного текста, но не будет применять его к остальному тексту.|
|Регулярные выражения|Для правил ItemHasKnownEntity или ItemHasRegularExpressionMatch для всех приложений Outlook:<br><ul><li>Задавайте не более 5 регулярных выражений в правилах активации для надстройки Outlook. Если этот предел будет превышен, установить надстройку будет невозможно.</li><li>Задавайте регулярные выражения, ожидаемые результаты которых возвращаются в первых 50 совпадениях с помощью метода <b>getRegExMatches</b>. </li><li>Указывайте в регулярных выражениях утверждения с просмотром вперед, а не утверждения с просмотром назад `(?<=text)` или отрицательные утверждения с просмотром назад `(?<!text)`.</li><li>Задавайте регулярные выражения, соответствия которым не превышают ограничений, указанных в приведенной ниже таблице.<br/><br/><table><tr><th>Ограничение длины для результата, соответствующего регулярному выражению</th><th>Полнофункциональные клиенты Outlook</th><th>Outlook для iOS и Android</th></tr><tr><td>Основной текст элемента в виде простого текста</td><td>1,5 КБ</td><td>3 КБ</td></tr><tr><td>Основной текст элемента в виде HTML-кода</td><td>3 КБ</td><td>3 КБ</td></tr></table>|

## <a name="see-also"></a>См. также

- [Создание надстроек Outlook для форм создания](compose-scenario.md)
- [Ограничения активации и API JavaScript для надстроек Outlook](limits-for-activation-and-javascript-api-for-outlook-add-ins.md)
- [Использование правил активации на основе регулярных выражений для отображения надстройки Outlook](use-regular-expressions-to-show-an-outlook-add-in.md)
- [Сопоставление строк в элементе Outlook как известных сущностей](match-strings-in-an-item-as-well-known-entities.md)
    
