---
title: Работа с диапазонами с использованием API JavaScript для Excel (дополнительные задачи)
description: Расширенные функции и сценарии объектов Range, такие как специальные ячейки, удаление дубликатов и работа с датами.
ms.date: 10/13/2020
localization_priority: Normal
ms.openlocfilehash: 144012177e0e070149f6cef825c63392a468773d
ms.sourcegitcommit: 6fa29989dfaec4dfa0f8df3fe5fb038d7afbae30
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487889"
---
# <a name="work-with-ranges-using-the-excel-javascript-api-advanced"></a>Работа с диапазонами с использованием API JavaScript для Excel (дополнительные задачи)

Эта статья основана на сведениях из статьи [Работа с диапазонами с использованием API JavaScript для Excel (основные задачи)](excel-add-ins-ranges.md) с предоставлением примеров кода, демонстрирующих способы выполнения более сложных задач с диапазонами с использованием API JavaScript для Excel. Полный список свойств и методов, `Range` поддерживаемых объектом, представлен в разделе [объект Range (API JavaScript для Excel)](/javascript/api/excel/excel.range).

## <a name="work-with-dates-using-the-moment-msdate-plug-in"></a>Работа с датами с использованием подключаемого модуля Moment-MSDate

[Библиотека JavaScript Moment](https://momentjs.com/) предоставляет удобный способ использования дат и меток времени. [Подключаемый модуль Moment-MSDate](https://www.npmjs.com/package/moment-msdate) преобразует формат моментов времени в предпочитаемый для Excel. Это тот же формат, который возвращает [функция ТДАТА](https://support.office.com/article/now-function-3337fd29-145a-4347-b2e6-20c904739c46).

В приведенном ниже коде показано, как установить для диапазона в **B4** метку момента времени.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");

    var now = Date.now();
    var nowMoment = moment(now);
    var nowMS = nowMoment.toOADate();

    var dateRange = sheet.getRange("B4");
    dateRange.values = [[nowMS]];

    dateRange.numberFormat = [["[$-409]m/d/yy h:mm AM/PM;@"]];

    return context.sync();
}).catch(errorHandlerFunction);
```

Это похоже на способ получения даты из ячейки и ее преобразования в формат момента времени или другой формат, как показано в приведенном ниже коде:

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");

    var dateRange = sheet.getRange("B4");
    dateRange.load("values");

    return context.sync().then(function () {
        var nowMS = dateRange.values[0][0];

        // log the date as a moment
        var nowMoment = moment.fromOADate(nowMS);
        console.log(`get (moment): ${JSON.stringify(nowMoment)}`);

        // log the date as a UNIX-style timestamp
        var now = nowMoment.unix();
        console.log(`get (timestamp): ${now}`);
    });
}).catch(errorHandlerFunction);
```

Вашей надстройке потребуется отформатировать диапазоны, чтобы отобразить даты в более понятной для человека форме. В примере `"[$-409]m/d/yy h:mm AM/PM;@"` время отобразится как "12/3/18 3:57 PM". Дополнительные сведения о форматах чисел даты и времени см. в разделе "Рекомендации по форматам даты и времени" статьи [Рекомендации по настройке числовых форматов](https://support.microsoft.com/office/c0a1d1fa-d3f4-4018-96b7-9c9354dd99f5).

## <a name="work-with-multiple-ranges-simultaneously"></a>Одновременное работу с несколькими диапазонами

Объект [RangeAreas](/javascript/api/excel/excel.rangeareas) позволяет надстройке выполнять операции над несколькими диапазонами одновременно. Эти диапазоны могут быть смежными, но это необязательно. Объект `RangeAreas` подробнее рассматривается в статье [Работа с несколькими диапазонами одновременно в надстройках Excel](excel-add-ins-multiple-ranges.md).

## <a name="find-special-cells-within-a-range"></a>Поиск специальных ячеек в диапазоне

Методы [Range. жетспеЦиалцеллс](/javascript/api/excel/excel.range#getspecialcells-celltype--cellvaluetype-) и [Range. жетспеЦиалцеллсорнуллобжект](/javascript/api/excel/excel.range#getspecialcellsornullobject-celltype--cellvaluetype-) находят диапазоны на основе характеристик их ячеек и типов значений их ячеек. Оба этих метода возвращают объекты `RangeAreas`. Подписи методов из файла типов данных TypeScript:

```typescript
getSpecialCells(cellType: Excel.SpecialCellType, cellValueType?: Excel.SpecialCellValueType): Excel.RangeAreas;
```

```typescript
getSpecialCellsOrNullObject(cellType: Excel.SpecialCellType, cellValueType?: Excel.SpecialCellValueType): Excel.RangeAreas;
```

В приведенном ниже примере используется метод `getSpecialCells`, чтобы найти все ячейки с формулами. Вот что нужно знать об этом коде:

- Он ограничивает часть листа, в которой требуется выполнять поиск, путем вызова сначала метода `Worksheet.getUsedRange`, а затем метода `getSpecialCells` только для этого диапазона.
- Метод `getSpecialCells` возвращает объект `RangeAreas`, поэтому все ячейки с формулами окрашены розовым цветом даже в том случае, если они не являются смежными.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var usedRange = sheet.getUsedRange();
    var formulaRanges = usedRange.getSpecialCells(Excel.SpecialCellType.formulas);
    formulaRanges.format.fill.color = "pink";

    return context.sync();
})
```

Если в диапазоне нет ячеек с целевыми характеристиками, метод `getSpecialCells` выдает ошибку **ItemNotFound**. Это приведет к переадресации потока управления к блоку `catch`, если таковой существует. Если `catch` блок отсутствует, то ошибка приостанавливается для метода.

Если ожидается, что всегда должны существовать ячейки с целевыми характеристиками, скорее всего вы захотите, чтобы код выдавал ошибку при их отсутствии. Если отсутствие соответствующих ячеек является допустимым сценарием, ваш код должен проверить наличие такой возможности и корректно выполнить действие без выдачи ошибки. Добиться такого поведения можно с помощью метода `getSpecialCellsOrNullObject` и возвращаемого им свойства `isNullObject`. Этот шаблон используется в приведенном ниже примере. Вот что нужно знать об этом коде:

- Метод `getSpecialCellsOrNullObject` всегда возвращает прокси-объект, поэтому он не может иметь значение `null` в обычном смысле JavaScript. Но если соответствующие ячейки не обнаружены, свойству `isNullObject` объекта присваивается значение `true`.
- Он вызывает `context.sync` *перед* тестированием свойства `isNullObject`. Это требование для всех методов и свойств `*OrNullObject`, так как всегда нужно загружать и синхронизировать свойство, чтобы его прочесть. Однако необязательно *явно* загружать свойство `isNullObject`. Оно автоматически загружается с помощью `context.sync`, даже если `load` не вызывается для объекта. Дополнительные сведения см. в статье [ \* методы и свойства орнуллобжект](../develop/application-specific-api-model.md#ornullobject-methods-and-properties).
- Этот код можно проверить, выбрав сначала диапазон без ячеек с формулами и запустив его. Затем следует выбрать диапазон, содержащий по крайней мере одну ячейку с формулой, и снова запустить его.

```js
Excel.run(function (context) {
    var range = context.workbook.getSelectedRange();
    var formulaRanges = range.getSpecialCellsOrNullObject(Excel.SpecialCellType.formulas);
    return context.sync()
        .then(function() {
            if (formulaRanges.isNullObject) {
                console.log("No cells have formulas");
            }
            else {
                formulaRanges.format.fill.color = "pink";
            }
        })
        .then(context.sync);
})
```

Для удобства во всех других примерах в этой статье используйте метод `getSpecialCells` вместо `getSpecialCellsOrNullObject`.

### <a name="narrow-the-target-cells-with-cell-value-types"></a>Ограничение целевых ячеек с помощью типа значений ячеек

Методы `Range.getSpecialCells()` и `Range.getSpecialCellsOrNullObject()` принимают необязательный второй параметр, используемый для дополнительного ограничения целевых ячеек. Этот второй параметр `Excel.SpecialCellValueType` используется для указания того, что требуются только ячейки, содержащие определенные типы значений.

> [!NOTE]
> Параметр `Excel.SpecialCellValueType` можно использовать, только если для параметра `Excel.SpecialCellType` задано значение `Excel.SpecialCellType.formulas` или `Excel.SpecialCellType.constants`.

#### <a name="test-for-a-single-cell-value-type"></a>Тестирование для ячеек с одним типом значений

Для перечисления `Excel.SpecialCellValueType` существует четыре основных типа (в дополнение к другим объединенным значениям, описанным ниже в этом разделе):

- `Excel.SpecialCellValueType.errors`
- `Excel.SpecialCellValueType.logical` (означает логическое значение)
- `Excel.SpecialCellValueType.numbers`
- `Excel.SpecialCellValueType.text`

В приведенном ниже примере выполняется поиск специальных ячеек, являющихся числовыми константами, и их окрашивание в розовый цвет. Вот что нужно знать об этом коде:

- Он выделяет только ячейки с числовым значением литерала. Он не выделяет ячейки с формулой (даже если результат является числом), логическим значением, текстовым значением или ячейки с состоянием ошибки.
- Чтобы протестировать код, убедитесь, что в листе есть ячейки с числовыми значениями литералов, ячейки с другими значениями литералов и ячейки с формулами.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var usedRange = sheet.getUsedRange();
    var constantNumberRanges = usedRange.getSpecialCells(
        Excel.SpecialCellType.constants,
        Excel.SpecialCellValueType.numbers);
    constantNumberRanges.format.fill.color = "pink";

    return context.sync();
})
```

#### <a name="test-for-multiple-cell-value-types"></a>Тестирование для ячеек с несколькими типами значений

Иногда требуется работать с ячейками, имеющими несколько типов значений, например со всеми ячейками с текстовыми значениями и всеми ячейками с логическими значениями (`Excel.SpecialCellValueType.logical`). Для перечисления `Excel.SpecialCellValueType` существуют значения с объединенными типами. Например, `Excel.SpecialCellValueType.logicalText` обрабатывает все ячейки с логическими и текстовыми значениями. `Excel.SpecialCellValueType.all` является значением по умолчанию, которое не ограничивает возвращаемые типы значений ячеек. В приведенном ниже примере окрашены все ячейки с формулами, которые производят числовое или логическое значение.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var usedRange = sheet.getUsedRange();
    var formulaLogicalNumberRanges = usedRange.getSpecialCells(
        Excel.SpecialCellType.formulas,
        Excel.SpecialCellValueType.logicalNumbers);
    formulaLogicalNumberRanges.format.fill.color = "pink";

    return context.sync();
})
```

## <a name="cut-copy-and-paste"></a>Команды "Вырезать", "Копировать" и "Вставить"

### <a name="copy-and-paste"></a>Copy and paste

Метод [Range. copyFrom](/javascript/api/excel/excel.range#copyfrom-sourcerange--copytype--skipblanks--transpose-) реплицирует действия **копирования** и **вставки** пользовательского интерфейса Excel. Диапазон объекта, который вызывается `copyFrom`, является назначением. Источник для копирования передается как диапазон или адрес строки, представляющий диапазон.

В следующем примере кода копируются данные из **A1:E1** в диапазон, начиная с **G1** (который заканчивается вставкой в **G1:K1**).

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");
    // copy everything from "A1:E1" into "G1" and the cells afterwards ("G1:K1")
    sheet.getRange("G1").copyFrom("A1:E1");
    return context.sync();
}).catch(errorHandlerFunction);
```

У функции `Range.copyFrom` есть три необязательных параметра.

```TypeScript
copyFrom(sourceRange: Range | RangeAreas | string, copyType?: Excel.RangeCopyType, skipBlanks?: boolean, transpose?: boolean): void;
```

`copyType` указывает, какие данные копируются из источника в назначение.

- `Excel.RangeCopyType.formulas` передает формулы в исходных ячейках и сохраняет относительное расположение диапазонов этих формул. Все записи, не являющиеся формулами, копируются в исходном виде.
- `Excel.RangeCopyType.values` копирует значения данных, а в случае формул — результат формулы.
- `Excel.RangeCopyType.formats` копирует форматирование диапазона, включая шрифт, цвет и другие параметры форматирования, но без значений.
- `Excel.RangeCopyType.all` (параметр по умолчанию) копирует данные и форматирование, сохраняя формулы ячеек, если они найдены.

`skipBlanks` устанавливает, будут ли копироваться пустые ячейки в назначение. Если значение равно true, `copyFrom` пропускает пустые ячейки в диапазоне источника.
Пропущенные ячейки не перезапишут существующие данные в соответствующих им ячейках конечного диапазона. Значение по умолчанию: false.

`transpose` определяет, переставляются ли данные в исходное расположение, то есть переключаются ли строки и столбцы.
Переставленный диапазон переключается на главной диагонали, поэтому строки **1**, **2** и **3** становятся столбцами **A**, **B** и **C**.

В приведенном ниже примере кода и изображениях демонстрируется это поведение в простом сценарии.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");
    // copy a range, omitting the blank cells so existing data is not overwritten in those cells
    sheet.getRange("D1").copyFrom("A1:C1",
        Excel.RangeCopyType.all,
        true, // skipBlanks
        false); // transpose
    // copy a range, including the blank cells which will overwrite existing data in the target cells
    sheet.getRange("D2").copyFrom("A2:C2",
        Excel.RangeCopyType.all,
        false, // skipBlanks
        false); // transpose
    return context.sync();
}).catch(errorHandlerFunction);
```

*Прежде чем предыдущая функция была запущена.*

![Данные в Excel перед запуском метода копирования диапазона](../images/excel-range-copyfrom-skipblanks-before.png)

*После запуска предыдущей функции.*

![Данные в Excel после запуска метода копирования диапазона](../images/excel-range-copyfrom-skipblanks-after.png)

### <a name="cut-and-paste-move-cells"></a>Вырезание и вставка (перемещение) ячеек

Метод [Range. moveTo](/javascript/api/excel/excel.range#moveto-destinationrange-) перемещает ячейки в новое расположение в книге. Поведение перемещения ячейки работает так же, как при перемещении ячеек, [перетаскивая границу диапазона](https://support.office.com/article/Move-or-copy-cells-and-cell-contents-803d65eb-6a3e-4534-8c6f-ff12d1c4139e) или при выполнении действий по **вырезанию** и **вставке** . Форматирование и значения диапазона перемещаются в расположение, указанное в качестве `destinationRange` параметра.

В следующем примере кода показан диапазон, перемещенный с `Range.moveTo` методом. Обратите внимание, что если конечный диапазон меньше исходного, он будет развернут, чтобы охватывать исходное содержимое.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    sheet.getRange("F1").values = [["Moved Range"]];

    // Move the cells "A1:E1" to "G1" (which fills the range "G1:K1").
    sheet.getRange("A1:E1").moveTo("G1");
    return context.sync();
});
```

## <a name="remove-duplicates"></a>Удаление дубликатов

Метод [Range. removeDuplicates](/javascript/api/excel/excel.range#removeduplicates-columns--includesheader-) удаляет строки с повторяющимися записями в указанных столбцах. Метод проходит через каждую строку в диапазоне от самого низкого значения до индекса с максимальным значением в диапазоне (сверху вниз). Строка удаляется, если значение в ее указанном столбце или столбцах уже встречалось в диапазоне. Строки в диапазоне под удаленной строкой сдвигаются вверх. Функция `removeDuplicates` не влияет на положение ячеек вне диапазона.

Функция `removeDuplicates` использует параметр `number[]`, представляющий индексы столбцов, которые проверяются на наличие дубликатов. Этот массив отсчитывается от нуля относительно диапазона, а не листа. Метод также использует логический параметр, указывающий, является ли первая строка заголовком. При значении **true** верхняя строка игнорируется при поиске дубликатов. `removeDuplicates`Метод возвращает `RemoveDuplicatesResult` объект, указывающий количество удаленных строк и количество оставшихся уникальных строк.

При использовании метода диапазона учитывайте `removeDuplicates` следующее:

- Функция `removeDuplicates` рассматривает значения ячеек, а не результаты функций. Если две разные функции вычисляют одинаковый результат, значения ячеек не считаются повторяющимися.
- Пустые ячейки не игнорируются функцией `removeDuplicates`. Значение пустой ячейки обрабатывается как любое другое значение. Это означает, что пустые строки, содержащиеся в диапазоне, будут включены в объект `RemoveDuplicatesResult`.

В приведенном ниже примере показано удаление записей с повторяющимися значениями в первом столбце.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");
    var range = sheet.getRange("B2:D11");

    var deleteResult = range.removeDuplicates([0],true);
    deleteResult.load();

    return context.sync().then(function () {
        console.log(deleteResult.removed + " entries with duplicate names removed.");
        console.log(deleteResult.uniqueRemaining + " entries with unique names remain in the range.");
    });
}).catch(errorHandlerFunction);
```

*Прежде чем предыдущая функция была запущена.*

![Данные в Excel перед выполнением метода удаления дубликатов в диапазоне](../images/excel-ranges-remove-duplicates-before.png)

*После запуска предыдущей функции.*

![Данные в Excel после запуска метода удаления повторяющихся значений диапазона](../images/excel-ranges-remove-duplicates-after.png)

## <a name="group-data-for-an-outline"></a>Группирование данных для структуры

Строки или столбцы диапазона можно объединять для создания [структуры](https://support.office.com/article/Outline-group-data-in-a-worksheet-08CE98C4-0063-4D42-8AC7-8278C49E9AFF). Эти группы можно сворачивать и разворачивать для скрытия и отображения соответствующих ячеек. Это упрощает быстрый анализ данных в верхней строке. Используйте [Range. Group](/javascript/api/excel/excel.range#group-groupoption-) , чтобы сделать эти группы структуры.

Структура может иметь иерархию, где небольшие группы вложены в крупные группы. Это позволяет просматривать структуру на разных уровнях. Изменение видимого уровня структуры можно выполнить программным способом с помощью метода [листа. шоваутлинелевелс](/javascript/api/excel/excel.worksheet#showoutlinelevels-rowlevels--columnlevels-) . Обратите внимание, что Excel поддерживает только восемь уровней групп структуры.

В приведенном ниже примере кода показано, как создать структуру с двумя уровнями групп для строк и столбцов. На следующем изображении показаны группирования этой структуры. Обратите внимание, что в примере кода сгруппированные диапазоны не включают строку или столбец элемента управления структуры (итоговые значения для этого примера). Группа определяет, что будет свернуто, а не как строка или столбец с элементом управления.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");

    // Group the larger, main level. Note that the outline controls
    // will be on row 10, meaning 4-9 will collapse and expand.
    sheet.getRange("4:9").group(Excel.GroupOption.byRows);

    // Group the smaller, sublevels. Note that the outline controls
    // will be on rows 6 and 9, meaning 4-5 and 7-8 will collapse and expand.
    sheet.getRange("4:5").group(Excel.GroupOption.byRows);
    sheet.getRange("7:8").group(Excel.GroupOption.byRows);

    // Group the larger, main level. Note that the outline controls
    // will be on column R, meaning C-Q will collapse and expand.
    sheet.getRange("C:Q").group(Excel.GroupOption.byColumns);

    // Group the smaller, sublevels. Note that the outline controls
    // will be on columns G, L, and R, meaning C-F, H-K, and M-P will collapse and expand.
    sheet.getRange("C:F").group(Excel.GroupOption.byColumns);
    sheet.getRange("H:K").group(Excel.GroupOption.byColumns);
    sheet.getRange("M:P").group(Excel.GroupOption.byColumns);
    return context.sync();
}).catch(errorHandlerFunction);

```

![Диапазон с двумя уровнями структуры с двумя измерениями](../images/excel-outline.png)

Чтобы разгруппировать группу строк или столбцов, используйте метод [Range. Ungroup](/javascript/api/excel/excel.range#ungroup-groupoption-) . Это приведет к удалению внешнего уровня структуры. Если несколько групп одного и того же типа строк или столбцов находятся на одном уровне в пределах указанного диапазона, все эти группы размещаются в разгруппировании.

## <a name="handle-dynamic-arrays-and-spilling"></a>Обработка динамических массивов и сброс

Некоторые формулы Excel возвращают [динамические массивы](https://support.microsoft.com/office/dynamic-array-formulas-and-spilled-array-behavior-205c6b06-03ba-4151-89a1-87a7eb36e531). Эти значения заполняют значения нескольких ячеек за прев ячейке оргинал в формуле. Это значение переполнения называется "Spill". Надстройка может найти диапазон, используемый для Spill, с помощью метода [Range. жетспиллингторанже](/javascript/api/excel/excel.range#getspillingtorange--) . Кроме того, существует [версия * орнуллобжект](..//develop/application-specific-api-model.md#ornullobject-methods-and-properties), `Range.getSpillingToRangeOrNullObject` .

В следующем примере показана базовая формула, которая копирует содержимое диапазона в ячейку, которая переводится в соседние ячейки. Затем надстройка заносит в журнал диапазон, содержащий сброс.

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getItem("Sample");

    // Set G4 to a formula that returns a dynamic array.
    var targetCell = sheet.getRange("G4");
    targetCell.formulas = [["=A4:D4"]];

    // Get the address of the cells that the dynamic array spilled into.
    var spillRange = targetCell.getSpillingToRange();
    spillRange.load("address");

    // Sync and log the spilled-to range.
    return context.sync().then(function () {
        // This will log the range as "G4:J4".
        console.log(`Copying the table headers spilled into ${spillRange.address}.`);
    });
}).catch(errorHandlerFunction);
```

Кроме того, можно найти ячейку, отвечающую за прохождение в заданную ячейку, с помощью метода [Range. жетспиллпарент](/javascript/api/excel/excel.range#getspillparent--) . Обратите внимание, что `getSpillParent` работает, только если объект Range является одной ячейкой. Вызов `getSpillParent` в диапазоне с несколькими ячейками приведет к ошибке (или возвращаемому диапазону значений NULL `Range.getSpillParentOrNullObject` ).

## <a name="get-formula-precedents"></a>Получение ячеек формулы

Формула Excel часто ссылается на другие ячейки. Когда ячейка предоставляет данные формуле, она называется "влияющей" формулой. Дополнительные сведения о функциях Excel, связанных с отношениями между ячейками, приведены в статье [Отображение связей между формулами и ячейками](https://support.microsoft.com/office/display-the-relationships-between-formulas-and-cells-a59bef2b-3701-46bf-8ff1-d3518771d507) . 

С помощью [Range. жетдиректпрецедентс](/javascript/api/excel/excel.range#getdirectprecedents--)надстройка может искать прямые влияющие ячейки формулы. `Range.getDirectPrecedents` Возвращает `WorkbookRangeAreas` объект. Этот объект содержит адреса всех влияющих ячеек в книге. У него есть отдельный `RangeAreas` объект для каждого листа, содержащего по крайней мере одну формулу. Узнайте [, как работать с несколькими диапазонами одновременно в](excel-add-ins-multiple-ranges.md) надстройках Excel, чтобы получить дополнительные сведения о работе с `RangeAreas` объектом.

В пользовательском интерфейсе Excel кнопка **трассировки влияющих** элементов рисует стрелку от влияющих ячеек до выбранной формулы. В отличие от кнопки пользовательского интерфейса Excel, `getDirectPrecedents` метод не рисует стрелки. 

> [!IMPORTANT]
> `getDirectPrecedents`Метод не может получать влияющие ячейки между книгами. 

В примере ниже показано, как получить прямые и влияющие границы для активного диапазона, а затем изменить цвет фона этих ячеек на желтый. 

> [!NOTE]
> Активный диапазон должен содержать формулу, ссылающуюся на другие ячейки в той же книге, чтобы выделение работало должным образом. 

```js
Excel.run(function (context) {
    // Precedents are cells that provide data to the selected formula.
    var range = context.workbook.getActiveCell();
    var directPrecedents = range.getDirectPrecedents();
    range.load("address");
    directPrecedents.areas.load("address");
    
    return context.sync()
        .then(function () {
            console.log(`Direct precedent cells of ${range.address}:`);

            // Use the direct precedents API to loop through precedents of the active cell.
            for (var i = 0; i < directPrecedents.areas.items.length; i++) {
              // Highlight and print out the address of each precedent cell.
              directPrecedents.areas.items[i].format.fill.color = "Yellow";
              console.log(`  ${directPrecedents.areas.items[i].address}`);
            }
        })
        .then(context.sync);
}).catch(errorHandlerFunction);
```

## <a name="see-also"></a>См. также

- [Работа с диапазонами с использованием API JavaScript для Excel](excel-add-ins-ranges.md)
- [Объектная модель JavaScript для Excel в надстройках Office](excel-add-ins-core-concepts.md)
- [Работа с несколькими диапазонами одновременно в надстройках Excel](excel-add-ins-multiple-ranges.md)
