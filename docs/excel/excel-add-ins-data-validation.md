---
title: Добавление проверки данных в диапазоны Excel
description: ''
ms.date: 04/13/2018
ms.openlocfilehash: 8e5f09f1c566103f34ad584885769229c17ab1f7
ms.sourcegitcommit: c72c35e8389c47a795afbac1b2bcf98c8e216d82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "19437530"
---
# <a name="add-data-validation-to-excel-ranges-preview"></a><span data-ttu-id="4b475-102">Добавление проверки данных в диапазоны Excel (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="4b475-102">Add data validation to Excel ranges (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="4b475-103">Пока API проверки данных являются предварительной версией, для их использования вы должны загрузить бета-версию библиотеки JavaScript для Office.</span><span class="sxs-lookup"><span data-stu-id="4b475-103">While the data validation APIs are in preview, you must load the beta version of the Office JavaScript library to use them.</span></span> <span data-ttu-id="4b475-104">URL-адрес: https://appsforoffice.microsoft.com/lib/beta/hosted/office.js.</span><span class="sxs-lookup"><span data-stu-id="4b475-104">The full URL is https://appsforoffice.microsoft.com/lib/beta/hosted/office.js.</span></span> <span data-ttu-id="4b475-105">Если вы используете TypeScript или редактор кода использует файл определения типа TypeScript для IntelliSense, воспользуйтесь https://appsforoffice.microsoft.com/lib/beta/hosted/office.d.ts.</span><span class="sxs-lookup"><span data-stu-id="4b475-105">If you are using TypeScript or your code editor uses a TypeScript type definition file for intellisense, use https://appsforoffice.microsoft.com/lib/beta/hosted/office.d.ts.</span></span>

<span data-ttu-id="4b475-106">Библиотека JavaScript Excel предоставляет API, позволяющие вашей надстройке добавлять автоматическую проверку данных в таблицы, столбцы, строки и другие диапазоны в книге.</span><span class="sxs-lookup"><span data-stu-id="4b475-106">The Excel JavaScript Library provides APIs to enable your add-in to add automatic data validation to tables, columns, rows, and other ranges in a workbook.</span></span> <span data-ttu-id="4b475-107">Для ознакомления с понятиями и терминологией проверки данных смотрите следующие статьи о том, как пользователи добавляют проверку данных через интерфейс Excel:</span><span class="sxs-lookup"><span data-stu-id="4b475-107">To understand the concepts and the terminology of data validation, please see the following articles about how users add data validation through the Excel UI:</span></span>

- [<span data-ttu-id="4b475-108">Применение проверки данных к ячейкам</span><span class="sxs-lookup"><span data-stu-id="4b475-108">Apply data validation to cells</span></span>](https://support.office.com/en-us/article/Apply-data-validation-to-cells-29FECBCC-D1B9-42C1-9D76-EFF3CE5F7249)
- [<span data-ttu-id="4b475-109">Подробнее о проверке данных</span><span class="sxs-lookup"><span data-stu-id="4b475-109">More on data validation</span></span>](https://microsoft.sharepoint.com/:p:/r/teams/oext/_layouts/15/Doc.aspx?sourcedoc=%7B51143964-d52c-429d-bfac-c7495473d536%7D&action=edit)
- [<span data-ttu-id="4b475-110">Описание и примеры проверки данных в Excel</span><span class="sxs-lookup"><span data-stu-id="4b475-110">Description and examples of data validation in Excel</span></span>](https://support.microsoft.com/en-us/help/211485/description-and-examples-of-data-validation-in-excel)

## <a name="programmatic-control-of-data-validation"></a><span data-ttu-id="4b475-111">Программный элемент управления проверкой данных</span><span class="sxs-lookup"><span data-stu-id="4b475-111">Programmatic control of data validation</span></span>

<span data-ttu-id="4b475-112">Свойство `Range.dataValidation`, которое принимает объект [DataValidation](https://dev.office.com/reference/add-ins/excel/datavalidation), является точкой входа для программного управления проверкой данных в Excel.</span><span class="sxs-lookup"><span data-stu-id="4b475-112">The `Range.dataValidation` property, which takes a [DataValidation](https://dev.office.com/reference/add-ins/excel/datavalidation) object, is the entry point for programmatic control of data validation in Excel.</span></span> <span data-ttu-id="4b475-113">Существует пять свойств объекта `DataValidation`:</span><span class="sxs-lookup"><span data-stu-id="4b475-113">There are five properties to the `DataValidation` object:</span></span>

- <span data-ttu-id="4b475-114">`rule` — Определяет, какие данные для диапазона являются достоверными.</span><span class="sxs-lookup"><span data-stu-id="4b475-114">`rule` &#8212; Defines what constitutes valid data for the range.</span></span> <span data-ttu-id="4b475-115">См. [DataValidationRule](https://dev.office.com/reference/add-ins/excel/datavalidationrule).</span><span class="sxs-lookup"><span data-stu-id="4b475-115">See [DataValidationRule](https://dev.office.com/reference/add-ins/excel/datavalidationrule).</span></span>
- <span data-ttu-id="4b475-116">`errorAlert` — Указывает, появляется ли ошибка, если пользователь вводит неверные данные, и определяет текст, название и стиль оповещения, например, **Informational** (информирование), **Warning** (предупреждение), а также **Stop** (остановка).</span><span class="sxs-lookup"><span data-stu-id="4b475-116">`errorAlert` &#8212; Specifies whether an error pops up if the user enters invalid data, and defines the alert text, title, and style; for example, **Informational**, **Warning**, and **Stop**.</span></span> <span data-ttu-id="4b475-117">См. [DataValidationErrorAlert](https://dev.office.com/reference/add-ins/excel/datavalidationerroralert).</span><span class="sxs-lookup"><span data-stu-id="4b475-117">See [DataValidationErrorAlert](https://dev.office.com/reference/add-ins/excel/datavalidationerroralert).</span></span>
- <span data-ttu-id="4b475-118">`prompt` — Указывает, появляется ли подсказка, когда пользователь наводит курсор мыши на диапазон, и определяет текст подсказки.</span><span class="sxs-lookup"><span data-stu-id="4b475-118">`prompt` &#8212; Specifies whether a prompt appears when the user hovers over the range and defines the prompt message.</span></span> <span data-ttu-id="4b475-119">См. [DataValidationPrompt](https://dev.office.com/reference/add-ins/excel/datavalidationprompt).</span><span class="sxs-lookup"><span data-stu-id="4b475-119">See [DataValidationPrompt](https://dev.office.com/reference/add-ins/excel/datavalidationprompt).</span></span>
- <span data-ttu-id="4b475-120">`ignoreBlanks` — Указывает, применяется ли правило проверки данных к пустым ячейкам в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="4b475-120">`ignoreBlanks` &#8212; Specifies whether the data validation rule applies to blank cells in the range.</span></span> <span data-ttu-id="4b475-121">Значение по умолчанию: `true`.</span><span class="sxs-lookup"><span data-stu-id="4b475-121">Defaults to `true`.</span></span>
- <span data-ttu-id="4b475-122">`type` — Идентификация типа проверки "только для чтения", например, WholeNumber, Date, TextLength и т. д. Это свойство устанавливается неявно при установке `rule`.</span><span class="sxs-lookup"><span data-stu-id="4b475-122">`type` &#8212; A read-only identification of the validation type, such as WholeNumber, Date, TextLength, etc. It is set indirectly when you set the `rule` property.</span></span>

> [!NOTE]
> <span data-ttu-id="4b475-123">Добавленная программно проверка данных ведет себя так же, как и добавленная вручную.</span><span class="sxs-lookup"><span data-stu-id="4b475-123">Data validation added programmatically behaves just like manually added data validation.</span></span> <span data-ttu-id="4b475-124">Например, обратите внимание, что проверка данных запускается только в том случае, если пользователь непосредственно вводит значение в ячейку или копирует и вставляет ячейку из другого места в книге с параметром вставки **Значения**.</span><span class="sxs-lookup"><span data-stu-id="4b475-124">In particular, note that data validation is triggered only if the user directly enters a value into a cell or copies and pastes a cell from elsewhere in the workbook and chooses the **Values** paste option.</span></span> <span data-ttu-id="4b475-125">Если пользователь копирует ячейку и выполняет простую вставку в диапазон с проверкой данных, проверка не запускается.</span><span class="sxs-lookup"><span data-stu-id="4b475-125">If the user copies a cell and does a plain paste into a range with data validation, validation is not triggered.</span></span>

### <a name="creating-validation-rules"></a><span data-ttu-id="4b475-126">Создание правил проверки</span><span class="sxs-lookup"><span data-stu-id="4b475-126">Creating validation rules</span></span>

<span data-ttu-id="4b475-127">Чтобы добавить проверку данных в диапазон, в код нужно добавить свойство `rule` объекта `DataValidation` в `Range.dataValidation`.</span><span class="sxs-lookup"><span data-stu-id="4b475-127">To add data validation to a range, your code must set the `rule` property of the `DataValidation` object in `Range.dataValidation`.</span></span> <span data-ttu-id="4b475-128">При этом используется объект [DataValidationRule](https://dev.office.com/reference/add-ins/excel/datavalidationrule), который имеет семь необязательных свойств.</span><span class="sxs-lookup"><span data-stu-id="4b475-128">This takes a [DataValidationRule](https://dev.office.com/reference/add-ins/excel/datavalidationrule) object which has seven optional properties.</span></span> <span data-ttu-id="4b475-129">*В любом объекте `DataValidationRule` может использоваться не более одного из этих свойств.*</span><span class="sxs-lookup"><span data-stu-id="4b475-129">*No more than one of these properties may be present in any `DataValidationRule` object.*</span></span> <span data-ttu-id="4b475-130">Включенное свойство определяет тип проверки.</span><span class="sxs-lookup"><span data-stu-id="4b475-130">The property that you include determines the type of validation.</span></span>

#### <a name="basic-and-datetime-validation-rule-types"></a><span data-ttu-id="4b475-131">Типы правил проверки Basic и DateTime</span><span class="sxs-lookup"><span data-stu-id="4b475-131">Basic and DateTime validation rule types</span></span>

<span data-ttu-id="4b475-132">Первые три свойства `DataValidationRule` (т. е. типа правил проверки) в качестве своего значения принимают объект [BasicDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation).</span><span class="sxs-lookup"><span data-stu-id="4b475-132">The first three `DataValidationRule` properties (i.e., validation rule types) take a [BasicDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation) object as their value.</span></span>

- <span data-ttu-id="4b475-133">`wholeNumber` — Требует целое число в дополнение к другим проверкам, определенным в объекте `BasicDataValidation`.</span><span class="sxs-lookup"><span data-stu-id="4b475-133">`wholeNumber` &#8212; Requires a whole number in addition to any other validation specified by the `BasicDataValidation` object.</span></span>
- <span data-ttu-id="4b475-134">`decimal` — Требует десятичное число в дополнение к другим условиям проверки, определенным в объекте `BasicDataValidation`.</span><span class="sxs-lookup"><span data-stu-id="4b475-134">`decimal` &#8212; Requires a decimal number in addition to any other validation specified by the `BasicDataValidation` object.</span></span>
- <span data-ttu-id="4b475-135">`textLength` — Применяет сведения проверки объекта `BasicDataValidation` к *длине* значения ячейки.</span><span class="sxs-lookup"><span data-stu-id="4b475-135">`textLength` &#8212; Applies the validation details in the `BasicDataValidation` object to the *length* of the cell's value.</span></span>

<span data-ttu-id="4b475-136">Вот пример создания правила проверки.</span><span class="sxs-lookup"><span data-stu-id="4b475-136">Here is an example of creating a validation rule.</span></span> <span data-ttu-id="4b475-137">Обратите внимание на особенности этого кода:</span><span class="sxs-lookup"><span data-stu-id="4b475-137">Note the following about this code:</span></span>

- <span data-ttu-id="4b475-138"> `operator` — это бинарный оператор "GreaterThan".</span><span class="sxs-lookup"><span data-stu-id="4b475-138">The `operator` is the binary operator "GreaterThan".</span></span> <span data-ttu-id="4b475-139">Всякий раз, когда вы используете бинарный оператор, значение, которое пользователь пытается ввести в ячейку, — это левый операнд, а значение, указанное в `formula1` — правый операнд.</span><span class="sxs-lookup"><span data-stu-id="4b475-139">Whenever you use a binary operator, the value that the user tries to enter in the cell is the left-hand operand and the value specified in `formula1` is the right-hand operand.</span></span> <span data-ttu-id="4b475-140">Таким образом, это правило устанавливает, что действительны только целые числа, которые больше 0.</span><span class="sxs-lookup"><span data-stu-id="4b475-140">So this rule says that only whole numbers that are greater than 0 are valid.</span></span> 
- <span data-ttu-id="4b475-141"> `formula1` — жестко заданное число.</span><span class="sxs-lookup"><span data-stu-id="4b475-141">The `formula1` is a hard-coded number.</span></span> <span data-ttu-id="4b475-142">Если во время написания кода вы не знаете, каким должно быть значение, для него можно использовать формулу Excel (как строку).</span><span class="sxs-lookup"><span data-stu-id="4b475-142">If you don't know at coding time what the value should be, you can also use an Excel formula (as a string) for the value.</span></span> <span data-ttu-id="4b475-143">Например, "= A3" и "= SUM (A4, B5)" также могут быть значениями `formula1`.</span><span class="sxs-lookup"><span data-stu-id="4b475-143">For example, "=A3" and "=SUM(A4,B5)" could also be values of `formula1`.</span></span>

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");
   
    range.dataValidation.rule = {
            wholeNumber: {
                formula1: 0,
                operator: "GreaterThan"
            }
        };

    return context.sync();
})
```

<span data-ttu-id="4b475-144">Перечень других бинарных операторов см. в статье [BasicDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation).</span><span class="sxs-lookup"><span data-stu-id="4b475-144">See [BasicDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation) for a list of the other binary operators.</span></span> 

<span data-ttu-id="4b475-145">Есть также два тернарных оператора: "Between" и "NotBetween".</span><span class="sxs-lookup"><span data-stu-id="4b475-145">There are also two ternary operators: "Between" and "NotBetween".</span></span> <span data-ttu-id="4b475-146">Чтобы их использовать, необходимо указать необязательное свойство `formula2`.</span><span class="sxs-lookup"><span data-stu-id="4b475-146">To use these, you must specify the optional `formula2` property.</span></span> <span data-ttu-id="4b475-147">Значения `formula1` и `formula2` — ограничивающие операнды.</span><span class="sxs-lookup"><span data-stu-id="4b475-147">The `formula1` and `formula2` values are the bounding operands.</span></span> <span data-ttu-id="4b475-148">Значение, которое пользователь вводит в ячейку, является третьим (оцениваемым) операндом.</span><span class="sxs-lookup"><span data-stu-id="4b475-148">The value that the user tries to enter in the cell is the third (evaluated) operand.</span></span> <span data-ttu-id="4b475-149">Ниже приведен пример использования оператора "Between":</span><span class="sxs-lookup"><span data-stu-id="4b475-149">The following is an example of using the "Between" operator:</span></span>

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");
   
    range.dataValidation.rule = {
            decimal: {
                formula1: 0,
                formula2: 100,
                operator: "Between"
            }
        };

    return context.sync();
})
```

<span data-ttu-id="4b475-150">Следующие два свойства правила в качестве своего значения принимают объект [DateTimeDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation).</span><span class="sxs-lookup"><span data-stu-id="4b475-150">The next two rule properties take a [DateTimeDataValidation](https://dev.office.com/reference/add-ins/excel/basicdatavalidation) object as their value.</span></span>

- `date`
- `time`

<span data-ttu-id="4b475-151">Объект `DateTimeDataValidation` структурирован аналогично `BasicDataValidation`: он содержит свойства `formula1`, `formula2` и `operator` и используется таким же образом.</span><span class="sxs-lookup"><span data-stu-id="4b475-151">The `DateTimeDataValidation` object is structured similarly to the `BasicDataValidation`: it has the properties `formula1`, `formula2`, and `operator`, and is used in the same way.</span></span> <span data-ttu-id="4b475-152">Разница состоит в том, что число в свойствах формулы использовать нельзя, но можно ввести строку [с датой и временем по ISO 8606](https://www.iso.org/iso-8601-date-and-time-format.html) (или формулу Excel).</span><span class="sxs-lookup"><span data-stu-id="4b475-152">The difference is that you cannot use a number in the formula properties, but you can enter a [ISO 8606 datetime](https://www.iso.org/iso-8601-date-and-time-format.html) string (or an Excel formula).</span></span> <span data-ttu-id="4b475-153">Ниже приведен пример, в котором определены допустимые значения дат для первой недели апреля 2018 года.</span><span class="sxs-lookup"><span data-stu-id="4b475-153">The following is an example that defines valid values as dates in the first week of April, 2018.</span></span> 

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");
   
    range.dataValidation.rule = {
            date: {
                formula1: "2018-04-01",
                formula2: "2018-04-08",
                operator: "Between"
            }
        };

    return context.sync();
})
```

#### <a name="list-validation-rule-type"></a><span data-ttu-id="4b475-154">Тип правила проверки List</span><span class="sxs-lookup"><span data-stu-id="4b475-154">List validation rule type</span></span>

<span data-ttu-id="4b475-155">Используйте свойство `list` для объекта `DataValidationRule` для указания того, что единственно допустимыми являются значения из ограниченного списка.</span><span class="sxs-lookup"><span data-stu-id="4b475-155">Use the `list` property in the `DataValidationRule` object to specify that the only valid values are those from a finite list.</span></span> <span data-ttu-id="4b475-156">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="4b475-156">The following is an example.</span></span> <span data-ttu-id="4b475-157">Обратите внимание на особенности этого кода:</span><span class="sxs-lookup"><span data-stu-id="4b475-157">Note the following about this code:</span></span>

- <span data-ttu-id="4b475-158">Предполагается, что существует лист с именем "Names", и значения в диапазоне "A1: A3" являются именами.</span><span class="sxs-lookup"><span data-stu-id="4b475-158">It assumes that there is a worksheet named "Names" and that the values in the range "A1:A3" are names.</span></span>
- <span data-ttu-id="4b475-159">Свойство `source`задает список допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="4b475-159">The `source` property specifies the list of valid values.</span></span> <span data-ttu-id="4b475-160">Ему присвоен диапазон с именами.</span><span class="sxs-lookup"><span data-stu-id="4b475-160">The range with the names has been assigned to it.</span></span> <span data-ttu-id="4b475-161">Также можно назначить список с разделителями-запятыми, например, "Сью, Рики, Лиз".</span><span class="sxs-lookup"><span data-stu-id="4b475-161">You can also assign a comma-delimited list; for example: "Sue, Ricky, Liz".</span></span> 
- <span data-ttu-id="4b475-162">Свойство `inCellDropDown` определяет, будет ли выпадающий элемент управления появляться в ячейке, когда пользователь ее выберет.</span><span class="sxs-lookup"><span data-stu-id="4b475-162">The `inCellDropDown` property specifies whether a drop-down control will appear in the cell when the user selects it.</span></span> <span data-ttu-id="4b475-163">Если установлено значение `true`, появится выпадающий список значений из `source`.</span><span class="sxs-lookup"><span data-stu-id="4b475-163">If set to `true`, then the drop-down appears with the list of values from the `source`.</span></span>

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");   
    var nameSourceRange = context.workbook.worksheets.getItem("Names").getRange("A1:A3");

    range.dataValidation.rule = {
        list: {
            inCellDropDown: true,
            source: nameSourceRange
        }
    };

    return context.sync();
})
```

#### <a name="custom-validation-rule-type"></a><span data-ttu-id="4b475-164">Тип правила проверки Custom</span><span class="sxs-lookup"><span data-stu-id="4b475-164">Custom validation rule type</span></span>

<span data-ttu-id="4b475-165">Используйте свойство `custom` для объекта `DataValidationRule`, чтобы указать настраиваемую формулу проверки.</span><span class="sxs-lookup"><span data-stu-id="4b475-165">Use the `custom` property in the `DataValidationRule` object to specify a custom validation formula.</span></span> <span data-ttu-id="4b475-166">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="4b475-166">The following is an example.</span></span> <span data-ttu-id="4b475-167">Обратите внимание на особенности этого кода:</span><span class="sxs-lookup"><span data-stu-id="4b475-167">Note the following about this code:</span></span>

- <span data-ttu-id="4b475-168">Предполагается, что на листе расположена таблица с двумя столбцами, A и B: **Athlete Name** (имя спортсмена) и **Comments** .</span><span class="sxs-lookup"><span data-stu-id="4b475-168">It assumes there is a two-column table with columns **Athlete Name** and **Comments** in the A and B columns of the worksheet.</span></span>
- <span data-ttu-id="4b475-169">Для исключения многословия в столбце **Комментарии** код определяет недопустимыми данные, которые содержат имя спортсмена.</span><span class="sxs-lookup"><span data-stu-id="4b475-169">To reduce verbosity in the **Comments** column, it makes data that includes the athlete's name invalid.</span></span>
- <span data-ttu-id="4b475-170">`SEARCH(A2,B2)` возвращает начальную позицию строки в A2 в строке в B2.</span><span class="sxs-lookup"><span data-stu-id="4b475-170">`SEARCH(A2,B2)` returns the starting position, in string in B2, of the string in A2.</span></span> <span data-ttu-id="4b475-171">Если A2 не содержится в B2, число не возвращается.</span><span class="sxs-lookup"><span data-stu-id="4b475-171">If A2 is not contained in B2, it does not return a number.</span></span> <span data-ttu-id="4b475-172">`ISNUMBER()` возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="4b475-172">`ISNUMBER()` returns a boolean.</span></span> <span data-ttu-id="4b475-173">Итак, свойство `formula` говорит, что данные в столбце**Comment** действительны, если в них не включена строка из столбца **Имя атлета**.</span><span class="sxs-lookup"><span data-stu-id="4b475-173">So the `formula` property says that valid data for the **Comment** column is data that does not include the string in the **Athlete Name** column.</span></span>

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");   
    var commentsRange = sheet.tables.getItem("AthletesTable").columns.getItem("Comments").getDataBodyRange();

    commentsRange.dataValidation.rule = {
            custom: {
                formula: "=NOT(ISNUMBER(SEARCH(A2,B2)))"
            }
        };

    return context.sync();
})
```

### <a name="create-validation-error-alerts"></a><span data-ttu-id="4b475-174">Создание предупреждений об ошибках проверки</span><span class="sxs-lookup"><span data-stu-id="4b475-174">Create validation error alerts</span></span>

<span data-ttu-id="4b475-175">Вы можете создать настраиваемое предупреждение об ошибке, которое появляется, когда пользователь пытается ввести недопустимые данные в ячейку.</span><span class="sxs-lookup"><span data-stu-id="4b475-175">You can a create custom error alert that appears when a user tries to enter invalid data in a cell.</span></span> <span data-ttu-id="4b475-176">Ниже приведен простой пример.</span><span class="sxs-lookup"><span data-stu-id="4b475-176">The following is a simple example:</span></span> <span data-ttu-id="4b475-177">Обратите внимание на особенности этого кода:</span><span class="sxs-lookup"><span data-stu-id="4b475-177">Note the following about this code:</span></span>

- <span data-ttu-id="4b475-178">Свойство `style` определяет, какое сообщение получит пользователь: alert (оповещение), warning (предупреждение) или "stop" (стоп-оповещение).</span><span class="sxs-lookup"><span data-stu-id="4b475-178">The `style` property determines whether the user gets an informational alert, a warning, or a "stop" alert.</span></span> <span data-ttu-id="4b475-179">Только `Stop` действительно предотвращает добавление пользователем недопустимых данных.</span><span class="sxs-lookup"><span data-stu-id="4b475-179">Only `Stop` actually prevents the user from adding invalid data.</span></span> <span data-ttu-id="4b475-180">Всплывающее окна `Warning` и `Information` обладают параметрами, которые позволяют пользователю все равно ввести недопустимые данные.</span><span class="sxs-lookup"><span data-stu-id="4b475-180">The pop-up for `Warning` and `Information` has options that allow the user enter the invalid data anyway.</span></span>
- <span data-ttu-id="4b475-181">Свойство `showAlert` по умолчанию имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4b475-181">The `showAlert` property defaults to `true`.</span></span> <span data-ttu-id="4b475-182">Это означает, что в ведущем приложении Excel появится общее оповещение (типа `Stop`), если вы не создали настраиваемое оповещение, которое либо устанавливает `showAlert` значение `false`, либо устанавливает настраиваемое сообщение, заголовок и стиль.</span><span class="sxs-lookup"><span data-stu-id="4b475-182">This means that the Excel host will pop-up a generic alert (of type `Stop`) unless you create a custom alert which either sets `showAlert` to `false` or sets a custom message, title, and style.</span></span> <span data-ttu-id="4b475-183">Этот код устанавливает настраиваемое сообщение и заголовок.</span><span class="sxs-lookup"><span data-stu-id="4b475-183">This code sets a custom message and title.</span></span>


```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");
   
    range.dataValidation.errorAlert = {
            message: "Sorry, only positive whole numbers are allowed",
            showAlert: true, // default is 'true'
            style: "Stop", // other possible values: Warning, Information
            title: "Negative or Decimal Number Entered"
        };
    
    // Set range.dataValidation.rule and optionally .prompt here.

    return context.sync();
})
```

<span data-ttu-id="4b475-184">Дополнительные сведения см. в статье [DataValidationErrorAlert](https://dev.office.com/reference/add-ins/excel/datavalidationerroralert).</span><span class="sxs-lookup"><span data-stu-id="4b475-184">For more information see   </span></span>

### <a name="create-validation-prompts"></a><span data-ttu-id="4b475-185">Создание запросов проверки</span><span class="sxs-lookup"><span data-stu-id="4b475-185">Create validation prompts</span></span>

<span data-ttu-id="4b475-186">Вы можете создать подсказку, которая появляется, когда пользователь наводит курсор мыши на ячейку, к которой применяется проверка данные, или выбирает ее.</span><span class="sxs-lookup"><span data-stu-id="4b475-186">You can create an instructional prompt that appears when a user hovers over, or selects, a cell to which data validation has been applied.</span></span> <span data-ttu-id="4b475-187">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="4b475-187">The following is an example:</span></span>

```js
Excel.run(function (context) {
    var sheet = context.workbook.worksheets.getActiveWorksheet();
    var range = sheet.getRange("B2:C5");
   
    range.dataValidation.prompt = {
            message: "Please enter a positive whole number.",
            showPrompt: true, // default is 'false'
            title: "Positive Whole Numbers Only."
        };
    
    // Set range.dataValidation.rule and optionally .errorAlert here.

    return context.sync();
})
```

<span data-ttu-id="4b475-188">Дополнительные сведения см. в статье [DataValidationPrompt](https://dev.office.com/reference/add-ins/excel/datavalidationprompt).</span><span class="sxs-lookup"><span data-stu-id="4b475-188">For more information see   </span></span>

### <a name="remove-data-validation-from-a-range"></a><span data-ttu-id="4b475-189">Удаление проверки данных из диапазона</span><span class="sxs-lookup"><span data-stu-id="4b475-189">Remove data validation from a range</span></span>

<span data-ttu-id="4b475-190">Чтобы удалить проверку данных из диапазона, вызовите метод [Range.dataValidation.clear ()](https://dev.office.com/reference/add-ins/excel/datavalidation#clear).</span><span class="sxs-lookup"><span data-stu-id="4b475-190">To remove data validation from a range, call the  [Range.dataValidation.clear()](https://dev.office.com/reference/add-ins/excel/datavalidation#clear) method.</span></span>

```js
myrange.dataValidation.clear()
```

<span data-ttu-id="4b475-191">Не обязательно, чтобы диапазон, который вы очищаете, полностью совпадал с диапазоном, для которого вы добавили проверку данных.</span><span class="sxs-lookup"><span data-stu-id="4b475-191">It isn't necessary that the range you clear is exactly the same range as a range on which you added data validation.</span></span> <span data-ttu-id="4b475-192">Если они не совпадают, очищаются только из двух диапазонов, которые совпадают.</span><span class="sxs-lookup"><span data-stu-id="4b475-192">If it isn't, only the overlapping cells, if any, of the two ranges are cleared.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b475-193">Очистка проверки данных из диапазона также распространяется на любую проверку данных, которую пользователь добавил вручную в диапазон.</span><span class="sxs-lookup"><span data-stu-id="4b475-193">Clearing data validation from a range will also clear any data validation that a user has added manually to the range.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b475-194">См. также</span><span class="sxs-lookup"><span data-stu-id="4b475-194">See also</span></span>

- [<span data-ttu-id="4b475-195">Основные понятия API JavaScript для Excel</span><span class="sxs-lookup"><span data-stu-id="4b475-195">Excel JavaScript API core concepts</span></span>](excel-add-ins-core-concepts.md)
- [<span data-ttu-id="4b475-196">Объект DataValidation (API JavaScript для Excel)</span><span class="sxs-lookup"><span data-stu-id="4b475-196">Worksheet Object (JavaScript API for Excel)</span></span>](https://dev.office.com/reference/add-ins/excel/datavalidation)
- [<span data-ttu-id="4b475-197">Объект Диапазон (API JavaScript для Excel)</span><span class="sxs-lookup"><span data-stu-id="4b475-197">Range Object (JavaScript API for Excel)</span></span>](https://dev.office.com/reference/add-ins/excel/range)



 