---
ms.date: 11/06/2020
description: Определите метаданные JSON для пользовательских функций в Excel и свяжите свойства идентификатора и имени функции.
title: Создание метаданных JSON для пользовательских функций вручную в Excel
localization_priority: Normal
ms.openlocfilehash: adbcbb9d2705a38b1ed9ff5cdffa6162b9d93a9c
ms.sourcegitcommit: 5bfd1e9956485c140179dfcc9d210c4c5a49a789
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071643"
---
# <a name="manually-create-json-metadata-for-custom-functions"></a>Создание метаданных JSON для пользовательских функций вручную

Как описано в статье [Обзор пользовательских функций](custom-functions-overview.md) , проект пользовательских функций должен включать файл метаданных JSON и файл скрипта (JavaScript или TypeScript) для регистрации функции, делая ее доступной для использования. Пользовательские функции регистрируются при первом запуске надстройки и после их появления для одного и того же пользователя во всех книгах.

[!include[Excel custom functions note](../includes/excel-custom-functions-note.md)]

Рекомендуется использовать автоматическое создание JSON, когда это возможно, вместо создания файла JSON. Автоматическое создание менее подвержено ошибкам пользователей, и в шаблоне `yo office` уже есть файл шаблона. Дополнительные сведения о тегах Жсдок и процессе автоматического формирования JSON приведены в статье Автоматическое [Создание МЕТАДАННЫХ JSON для пользовательских функций](custom-functions-json-autogeneration.md).

Тем не менее, проект настраиваемых функций можно сделать с нуля. Этот процесс требует выполнения следующих действий:

- Создайте файл JSON.
- Убедитесь, что файл манифеста подключен к файлу JSON.
- Свяжите функции `id` и `name` свойства в файле скрипта, чтобы зарегистрировать функции.

На следующем рисунке показано различие между `yo office` файлами формирования шаблонов и записью JSON с нуля.

![Изображение различий при использовании Yo Office и написании собственного JSON](../images/custom-functions-json.png)

> [!NOTE]
> Не забудьте подключить манифест к созданному файлу JSON, используя `<Resources>` раздел XML-файла манифеста, если генератор не используется `yo office` .

## <a name="authoring-metadata-and-connecting-to-the-manifest"></a>Создание метаданных и подключение к манифесту

Создайте файл JSON в проекте и предоставьте все подробные сведения о функциях, таких как параметры функции. В [приведенном ниже примере метаданных](#json-metadata-example) и [справочнике по метаданным](#metadata-reference) представлен полный список свойств функций.

Убедитесь, что XML-файл манифеста ссылается на JSON-файл в `<Resources>` разделе, как показано в следующем примере.

```json
<Resources>
    <bt:Urls>
        <bt:Url id="JSON-URL" DefaultValue="https://subdomain.contoso.com/config/customfunctions.json"/>
        <bt:Url id="JS-URL" DefaultValue="https://subdomain.contoso.com/dist/win32/ship/index.win32.bundle"/>
            <bt:Url id="HTML-URL" DefaultValue="https://subdomain.contoso.com/index.html"/>
    </bt:Urls>
    <bt:ShortStrings>
        <bt:String id="namespace" DefaultValue="CONTOSO"/>
    </bt:ShortStrings>
</Resources>
```

## <a name="json-metadata-example"></a>Пример метаданных JSON

В примере кода ниже показано содержимое JSON-файла метаданных для надстройки, определяющей настраиваемые функции. В следующих за этим примером разделах приводятся подробные сведения об отдельных свойствах, представленных в этом примере JSON.

```json
{
  "functions": [
    {
      "id": "ADD",
      "name": "ADD",
      "description": "Add two numbers",
      "helpUrl": "http://www.contoso.com/help",
      "result": {
        "type": "number",
        "dimensionality": "scalar"
      },
      "parameters": [
        {
          "name": "first",
          "description": "first number to add",
          "type": "number",
          "dimensionality": "scalar"
        },
        {
          "name": "second",
          "description": "second number to add",
          "type": "number",
          "dimensionality": "scalar"
        }
      ]
    },
    {
      "id": "GETDAY",
      "name": "GETDAY",
      "description": "Get the day of the week",
      "helpUrl": "http://www.contoso.com/help",
      "result": {
        "dimensionality": "scalar"
      },
      "parameters": []
    },
    {
      "id": "INCREMENTVALUE",
      "name": "INCREMENTVALUE",
      "description": "Count up from zero",
      "helpUrl": "http://www.contoso.com/help",
      "result": {
        "dimensionality": "scalar"
      },
      "parameters": [
        {
          "name": "increment",
          "description": "the number to be added each time",
          "type": "number",
          "dimensionality": "scalar"
        }
      ],
      "options": {
        "stream": true,
        "cancelable": true
      }
    },
    {
      "id": "SECONDHIGHEST",
      "name": "SECONDHIGHEST",
      "description": "Get the second highest number from a range",
      "helpUrl": "http://www.contoso.com/help",
      "result": {
        "dimensionality": "scalar"
      },
      "parameters": [
        {
          "name": "range",
          "description": "the input range",
          "type": "number",
          "dimensionality": "matrix"
        }
      ]
    }
  ]
}
```

> [!NOTE]
> Полный пример JSON-файла доступен в журнале транзакций [OfficeDev/Excel-Custom-functions](https://github.com/OfficeDev/Excel-Custom-Functions/blob/77760adb1dcc53469183049bea08196734dbc114/config/customfunctions.json) репозитория GitHub. Так как проект был скорректирован для автоматического создания JSON, полный пример рукописного кода JSON доступен только в предыдущих версиях проекта.

## <a name="metadata-reference"></a>Справка по метаданным

### <a name="functions"></a>functions

Свойство `functions` представляет собой массив объектов настраиваемых функций. В таблице ниже приведены свойства каждого объекта.

| Свойство      | Тип данных | Обязательный | Описание                                                                                                                                                                      |
| :------------ | :-------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `description` | строка    | Нет       | Описание функции, которое отображается пользователям в Excel (например, **преобразует значение по шкале Цельсия в температуру по шкале Фаренгейта** ).                                                            |
| `helpUrl`     | string    | Нет       | URL-адрес, по которому можно получить сведения о функции (отображается в области задач). Пример: `http://contoso.com/help/convertcelsiustofahrenheit.html`.                      |
| `id`          | string    | Да      | Уникальный идентификатор для функции. Этот идентификатор может содержать только буквы, цифры и точки и не может изменяться после настройки.                                            |
| `name`        | string    | Да      | Имя функции, которое отображается пользователям в Excel. В Excel это имя функции предваряется пространством имен пользовательских функций, указанным в XML-файле манифеста. |
| `options`     | object    | Нет       | Позволяет настроить некоторые аспекты того, как и когда Excel выполняет функцию. Дополнительные сведения см. в разделе [options](#options).                                                          |
| `parameters`  | array     | Да      | Массив, который определяет входные параметры для функции. Дополнительные сведения см. в разделе [Parameters](#parameters) .                                                                             |
| `result`      | object    | Да      | Объект, который определяет тип информации, возвращаемый функцией. Дополнительные сведения см. в разделе [result](#result).                                                                 |

### <a name="options"></a>options

Объект `options` позволяет настроить некоторые аспекты того, как и когда Excel выполняет функцию. В таблице ниже приведены свойства объекта `options`.

| Свойство          | Тип данных | Обязательный                               | Описание |
| :---------------- | :-------- | :------------------------------------- | :---------- |
| `cancelable`      | boolean   | Нет<br/><br/>Значение по умолчанию: `false`.  | Если это свойство имеет значение `true`, Excel будет вызывать обработчик `CancelableInvocation` каждый раз, когда пользователь будет предпринимать действия, которые приводят к отмене функции (например, вручную вызывает пересчет или редактирует ячейку, на которую ссылается функция). Функции, которые можно отменять, обычно используются только для асинхронных функций, которые возвращают один результат и нуждаются в обработке отмены запроса данных. Функция не может быть одновременно потоковой и отмены. Более подробную информацию можно найти в заметке около конца [функции потоковой передачи](custom-functions-web-reqs.md#make-a-streaming-function). |
| `requiresAddress` | boolean   | Нет <br/><br/>Значение по умолчанию: `false`. | Если `true` Пользовательская функция может получить доступ к адресу ячейки, которая вызвала пользовательскую функцию. Чтобы получить адрес ячейки, которая вызвала пользовательскую функцию, используйте context. Address в пользовательской функции. Пользовательские функции не могут быть заданы как потоковые, так и Рекуиресаддресс. При использовании этого параметра параметр "вызов" должен быть последним параметром, переданным в параметрах. |
| `stream`          | boolean   | Нет<br/><br/>Значение по умолчанию: `false`.  | Если это свойство имеет значение `true`, функция может выводить значение в ячейку несколько раз, даже если вызвана всего единожды. Этот параметр полезен для быстро изменяющихся источников данных, таких как цена акций. Функция не должна содержать оператор `return`. Вместо этого результирующее значение передается как аргумент метода обратного вызова `StreamingInvocation.setResult`. Дополнительные сведения см. в разделе [Потоковые функции](custom-functions-web-reqs.md#make-a-streaming-function). |
| `volatile`        | boolean   | Нет <br/><br/>Значение по умолчанию: `false`. | Если `true` функция пересчитывает при каждом пересчете Excel, функция пересчитывается, а не только при изменении зависимых значений формулы. Функция не может быть одновременно потоковой и переменной. Если обоим свойствам `stream` и `volatile` присвоено значение `true`, параметр переменности будет игнорироваться. |

### <a name="parameters"></a>parameters

Свойство `parameters` представляет собой массив объектов параметров. В таблице ниже приведены свойства каждого объекта.

|  Свойство  |  Тип данных  |  Обязательный  |  Описание  |
|:-----|:-----|:-----|:-----|
|  `description`  |  строка  |  Нет |  Описание параметра. Это отображается в IntelliSense Excel.  |
|  `dimensionality`  |  string  |  Нет  |  Должно быть **скалярным** (значение, отличное от массива) или **матричным** (двухмерный массив).  |
|  `name`  |  string  |  Да  |  Имя параметра. Это имя отображается в IntelliSense Excel.  |
|  `type`  |  string  |  Нет  |  Тип данных параметра. Может иметь значение **boolean** , **number** , **string** или **any** , что позволяет использовать любой из трех предыдущих типов. Если это свойство не задано, по умолчанию устанавливается тип данных **any**. |
|  `optional`  | boolean | Нет | Если присвоено значение `true`, параметр не обязателен. |
|`repeating`| boolean | Нет | Если `true` параметры заполняются из указанного массива. Обратите внимание, что функции все повторяющиеся параметры считаются необязательными параметрами по определению.  |

### <a name="result"></a>result

Объект `result` определяет тип информации, возвращаемый функцией. В таблице ниже приведены свойства объекта `result`.

| Свойство         | Тип данных | Обязательный | Описание                                                                          |
| :--------------- | :-------- | :------- | :----------------------------------------------------------------------------------- |
| `dimensionality` | строка    | Нет       | Должно быть **скалярным** (значение, отличное от массива) или **матричным** (двухмерный массив). |

## <a name="associating-function-names-with-json-metadata"></a>Сопоставление имен функций с метаданными JSON

Чтобы функция работала должным образом, необходимо связать `id` свойство функции с реализацией JavaScript. Убедитесь, что существует связь, в противном случае функция не будет зарегистрирована и непригодна для работы в Excel. В приведенном ниже примере кода показано, как выполнить связь с помощью `CustomFunctions.associate()` метода. Пример определяет пользовательскую функцию `add` и связывает ее с объектом в файле метаданных JSON, где для свойства `id` установлено значение **ADD**.

```js
/**
 * Add two numbers
 * @customfunction
 * @param {number} first First number
 * @param {number} second Second number
 * @returns {number} The sum of the two numbers.
 */
function add(first, second) {
  return first + second;
}

CustomFunctions.associate("ADD", add);
```

В следующем JSON показаны метаданные JSON, связанные с предыдущим кодом пользовательской функции JavaScript.

```json
{
  "functions": [
    {
      "description": "Add two numbers",
      "id": "ADD",
      "name": "ADD",
      "parameters": [
        {
          "description": "First number",
          "name": "first",
          "type": "number"
        },
        {
          "description": "Second number",
          "name": "second",
          "type": "number"
        }
      ],
      "result": {
        "type": "number"
      }
    }
  ]
}
```

Имейте в виду приведенные ниже рекомендации при создании пользовательских функций в файле JavaScript и указании соответствующих сведений в файле метаданных JSON.

- Убедитесь, что в файле метаданных JSON значение каждого свойства `id` содержит только буквы, цифры и точки.

- Убедитесь, что в файле метаданных JSON значение каждого свойства `id` уникально в пределах файла. То есть никакие два объекта функций в файле метаданных не должны иметь одинаковое значение `id`.

- Не изменяйте значение свойства `id` в файле метаданных JSON после его сопоставления с соответствующим именем функции JavaScript. Вы можете изменить имя функции, которое отображается для конечных пользователей в Excel, путем обновления свойства `name` в файле метаданных JSON, но никогда не следует изменять значение свойства `id` после его установления.

- В файле JavaScript укажите настраиваемое сопоставление функций с помощью `CustomFunctions.associate` каждой функции.

В следующем примере показаны метаданные JSON, которые соответствуют функциям, определенным в предыдущем примере кода JavaScript. `id` `name` Значения свойств и представлены в верхнем регистре, что является лучшим вариантом при описании пользовательских функций. Этот код JSON необходимо добавить только в том случае, если вы готовите собственный файл JSON вручную и не используете автоматическое создание. Дополнительные сведения об автоформировании приведены в статье Автоматическое [Создание МЕТАДАННЫХ JSON для пользовательских функций](custom-functions-json-autogeneration.md).

```json
{
  "$schema": "https://developer.microsoft.com/en-us/json-schemas/office-js/custom-functions.schema.json",
  "functions": [
    {
      "id": "ADD",
      "name": "ADD",
      ...
    },
    {
      "id": "INCREMENT",
      "name": "INCREMENT",
      ...
    }
  ]
}
```

## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь с рекомендациями [по именованию функции](custom-functions-naming.md) или [локализации функции](custom-functions-localize.md) с помощью ранее описанного рукописного метода JSON.

## <a name="see-also"></a>См. также

- [Автоматическое генерирование метаданных JSON для пользовательских функций](custom-functions-json-autogeneration.md)
- [Параметры параметров пользовательских функций](custom-functions-parameter-options.md)
- [Создание пользовательских функций в Excel](custom-functions-overview.md)
