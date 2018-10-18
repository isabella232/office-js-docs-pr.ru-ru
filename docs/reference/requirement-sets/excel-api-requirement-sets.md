# <a name="excel-javascript-api-requirement-sets"></a>Наборы требований API JavaScript для Excel

Наборы требований — это именованные группы обязательных элементов API. С помощью наборов обязательных элементов, указанных в манифесте, или проверки в среде выполнения надстройки Office определяют, поддерживает ли ведущее приложение Office необходимые API. Дополнительные сведения см. в статье [Версии Office и наборы требований](https://docs.microsoft.com/office/dev/add-ins/develop/office-versions-and-requirement-sets).

Надстройки Excel выполняются в нескольких версиях Office, включая Office 2016 или более поздние для Windows, Office для iPad, Office для Mac и Office Online. В таблице ниже перечислены наборы требований Excel, ведущих приложений Office, которые поддерживают каждый набор требований, а также версии сборки или номер для этих приложений.

> [!NOTE]
> Любой API, помеченный как **Бета**, не готов для конечного пользователя. Мы делаем их доступными для разработчиков для испытаний в среде тестирования и разработки. Они не предназначены для использования с производственными/критическими для бизнеса документами.
> 
> Для наборов требований, помеченных как **Бета**, используйте указанную (или более позднюю) версию программного обеспечения Office и используйте бета-библиотеку на CDN: https://appsforoffice.microsoft.com/lib/beta/hosted/office.js. Записи, не отмеченные как **Бета**, обычно доступны в сети, и вы можете использовать Production library на CDN: https://appsforoffice.microsoft.com/lib/1/hosted/office.js.

|  Набор требований  |  Office 365 для Windows\*  |  Office для iPad  |  Office 365 для Mac  | Office Online  |  Office Online Server  |
|:-----|-----|:-----|:-----|:-----|:-----|
| Бета-версии  | Пожалуйста, [посетите страницу открытых спецификаций Excel JavaScript API](https://github.com/OfficeDev/office-js-docs/tree/ExcelJs_OpenSpec)! |
| ExcelApi1.8  | Версия 1808 (сборка 10730.20102) или более поздняя | 2.17 или более поздняя | 16.17 или более поздняя | Сентябрь 2018 г. | Ожидается в скором времени |
| ExcelApi1.7  | Версия 1801 (сборка 9001.2171) или более поздняя   | 2.9 или более поздняя | 16.9 или более поздняя | Апрель 2018 г. | Ожидается в скором времени |
| ExcelApi1.6  | Версия 1704 (сборка 8201.2001) или более поздняя   | 2.2 или более поздняя |15.36 или более поздняя| Апрель 2017 г. | Ожидается в скором времени|
| ExcelApi1.5  | Версия 1703 (сборка 8067.2070) или более поздняя   | 2.2 или более поздняя |15.36 или более поздняя| Март 2017 г. | Ожидается в скором времени|
| ExcelApi1.4  | Версия 1701 (сборка 7870.2024) или более поздняя   | 2.2 или более поздняя |15.36 или более поздняя| Январь 2017 г. | Ожидается в скором времени|
| ExcelApi1.3  | Версия 1608 (сборка 7369.2055) или более поздняя | 1.27 или более поздняя |  15.27 или более поздняя| Сентябрь 2016 г. | Версия 1608 (сборка 7601.6800) или более поздняя|
| ExcelApi1.2  | Версия 1601 (сборка 6741.2088) или более поздняя | 1.21 или более поздняя | 15.22 или более поздняя| Январь 2016 г. ||
| ExcelApi1.1  | Версия 1509 (сборка 4266.1001) или более поздняя | 1.19 или более поздняя | 15.20 или более поздняя| Январь 2016 г. ||

> [!NOTE]
> Номер сборки Office 2016, установленной с помощью MSI, — 16.0.4266.1001. Эта версия содержит только наборы требований ExcelApi 1.1.

Для дополнительных сведений о версии, номерах сборок и Office Online Server см.:

- [Номера версий и сборок выпусков из канала обновления для клиентов Office 365](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)
- [Какую версию Office я использую?](https://support.office.com/article/What-version-of-Office-am-I-using-932788b8-a3ce-44bf-bb09-e334518b8b19)
- [Где можно найти номера версии и сборки клиентского приложения Office 365](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)
- [Обзор Office Online Server](https://docs.microsoft.com/officeonlineserver/office-online-server-overview)

## <a name="whats-new-in-excel-javascript-api-18"></a>Новые возможности API JavaScript для Excel 1.8

Функции набора требований 1.8 к API JavaScript для Excel включают API для сводных таблиц, проверку данных, диаграммы, события для диаграмм, параметры производительности и создание рабочей книги.

### <a name="pivottable"></a>Сводная таблица

Wave 2 для API сводной таблицы позволяет надстройкам устанавливать иерархии сводной таблицы. Теперь вы можете управлять данными и то, как они агрегируются. Наша [статья о сводной таблице](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-pivottables) рассказывает о новых функциональных возможностях сводной таблицы.

### <a name="data-validation"></a>Проверка данных

Проверка данных дает вам контроль над данными, вводимыми пользователем в лист. Вы можете ограничить ячейки предопределенными наборами ответов или задать всплывающие предупреждения о нежелательном вводе. Узнайте больше о [ добавлении проверки данных в диапазоны ](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-data-validation) уже сегодня.

### <a name="charts"></a>Диаграммы

Еще один раунд API диаграмм обеспечивает еще больший программный контроль над элементами диаграммы. Теперь у вас имеется больший доступ к условным обозначениям, осям, линии тренда и области построения.

### <a name="events"></a>События

Для диаграмм добавлено больше [событий](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-events). Пусть ваша надстройка реагирует на взаимодействие пользователей с диаграммой. Вы также можете [переключаться между запусками событий](https://docs.microsoft.com/office/dev/add-ins/excel/performance#enable-and-disable-events) во всей книге.


|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[приложение](/javascript/api/excel/excel.application)|_Метод_ > [createWorkbook(base64File: string)](/javascript/api/excel/excel.application)|Создает новую скрытую книгу, используя необязательный файл .xlsx с кодировкой base64.|1.8|
|[basicDataValidation](/javascript/api/excel/excel.basicdatavalidation)|_Свойство_ > formula1|Получает или задает Formula1, то есть минимальное значение или значение в зависимости от оператора.|1.8|
|[basicDataValidation](/javascript/api/excel/excel.basicdatavalidation)|_Свойство_ > formula2|Получает или задает Formula2, то есть максимальное значение или значение в зависимости от оператора.|1.8|
|[basicDataValidation](/javascript/api/excel/excel.basicdatavalidation)|_Связь_ > operator|Оператор, используемый для проверки данных.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > categoryLabelLevel|Возвращает или задает константу перечисления ChartCategoryLabelLevel, относящуюся к уровню, из которого получают метки категорий. Чтение/запись.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > plotVisibleOnly|True, если отображаются только видимые ячейки. False, если отображаются как видимые, так и скрытые ячейки. ReadWrite.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > seriesNameLevel|Возвращает или задает константу перечисления ChartSeriesNameLevel, относящуюся к уровню, из которого получают имена серий. Чтение/запись.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > showDataLabelsOverMaximum|Представляет, показывать ли метки данных, когда значение больше максимального значения на оси значений.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > style|Возвращает или задает стиль для диаграммы. ReadWrite.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Связь_ > displayBlanksAs|Возвращает или задает способ отображения пустых ячеек на диаграмме. ReadWrite.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Связь_ > plotArea|Представляет plotArea для диаграммы. Только для чтения.|1.8|
|[chart](/javascript/api/excel/excel.chart)|_Связь_ > plotBy|Возвращает или задает способ использования столбцов или строк в виде рядов данных на диаграмме. ReadWrite.|1.8|
|[chartActivatedEventArgs](/javascript/api/excel/excel.chartactivatedeventargs)|_Свойство_ > chartId|Получает идентификатор диаграммы, которая активируется.|1.8|
|[chartActivatedEventArgs](/javascript/api/excel/excel.chartactivatedeventargs)|_Свойство_ > type|Получает тип события.|1.8|
|[chartActivatedEventArgs](/javascript/api/excel/excel.chartactivatedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором активируется диаграмма.|1.8|
|[chartAddedEventArgs](/javascript/api/excel/excel.chartaddedeventargs)|_Свойство_ > chartId|Получает идентификатор диаграммы, которая добавляется в лист.|1.8|
|[chartAddedEventArgs](/javascript/api/excel/excel.chartaddedeventargs)|_Свойство_ > type|Получает тип события.|1.8|
|[chartAddedEventArgs](/javascript/api/excel/excel.chartaddedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в который добавляется диаграмма.|1.8|
|[chartAddedEventArgs](/javascript/api/excel/excel.chartaddedeventargs)|_Связь_ > source|Получает источник события.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > isBetweenCategories|Указывает, пересекает ли ось значений ось категорий между категориями.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > multiLevel|Указывает, является ли ось многоуровневой или нет.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > numberFormat|Представляет код формата для метки делений оси.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > offset|Представляет расстояние между уровнями меток и расстояние между первым уровнем и линией оси. Значение должно быть целым числом от 0 до 1000.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > positionAt|Представляет указанное положение оси в месте, где ее пересекает другая ось. Чтобы задать это свойство, следует использовать метод SetPositionAt(double). Только для чтения.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > textOrientation|Представляет ориентацию текста для метки делений оси. Значение должно быть целым числом от -90 до 90 или 180 для вертикально-ориентированного текста.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > alignment|Представляет выравнивание для указанной метки делений оси.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > position|Представляет указанное положение оси в месте, где ее пересекает другая ось.|1.8|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Метод_ > [setPositionAt(value: double)](/javascript/api/excel/excel.chartaxis)|Задает указанное положение оси в месте, где ее пересекает другая ось.|1.8|
|[chartAxisFormat](/javascript/api/excel/excel.chartaxisformat)|_Связь_ > fill|Представляет форматирование заполнения диаграммы. Только для чтения.|1.8|
|[chartAxisTitle](/javascript/api/excel/excel.chartaxistitle)|_Метод_ > [setFormula(formula: string)](/javascript/api/excel/excel.chartaxistitle)|Строковое значение, которое представляет формулу заголовка оси диаграммы с использованием нотации стиля A1.|1.8|
|[chartAxisTitleFormat](/javascript/api/excel/excel.chartaxistitleformat)|_Связь_ > border|Представляет формат границы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.8|
|[chartAxisTitleFormat](/javascript/api/excel/excel.chartaxistitleformat)|_Связь_ > fill|Представляет форматирование заполнения диаграммы. Только для чтения.|1.8|
|[chartBorder](/javascript/api/excel/excel.chartborder)|_Метод_ > [clear()](/javascript/api/excel/excel.chartborder)|Очистить формат границы элемента диаграммы.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > autoText|Булево значение, указывающее на то, генерирует ли метка данных автоматически соответствующий текст на основе контекста.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > formula|Строковое значение, которое представляет формулу метки данных диаграммы с использованием нотации стиля A1.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > height|Возвращает высоту, в пунктах метки данных диаграммы. Только для чтения. Значение NULL, если метка данных диаграммы не видна. Только для чтения.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > left|Представляет расстояние в пунктах от левого края метки данных диаграммы до левого края области диаграммы. Значение NULL, если метка данных диаграммы не видна.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > numberFormat|Строковое значение, которое представляет собой код формата для метки данных.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > text|Строка, представляющая текст метки данных на диаграмме.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > textOrientation|Указывает на ориентацию текста метки данных диаграммы. Значение должно быть целым числом от -90 до 90 или 180 для вертикально-ориентированного текста.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > top|Представляет расстояние в пунктах от верхнего края метки данных диаграммы до верха области диаграммы. Значение NULL, если метка данных диаграммы не видна.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > width|Возвращает ширину в пунктах метки данных диаграммы. Только для чтения. Значение NULL, если метка данных диаграммы не видна. Только для чтения.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Связь_ > format|Представляет формат метки данных диаграммы. Только для чтения.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Связь_ > horizontalAlignment|Представляет горизонтальное выравнивание для метки данных диаграммы.|1.8|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Связь_ > verticalAlignment|Представляет вертикальное выравнивание метки данных диаграммы.|1.8|
|[chartDataLabelFormat](/javascript/api/excel/excel.chartdatalabelformat)|_Связь_ > border|Представляет формат границы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.8|
|[chartDataLabels](/javascript/api/excel/excel.chartdatalabels)|_Свойство_ > autoText|Указывает на то, генерируют ли метки данных автоматически соответствующий текст на основе контекста.|1.8|
|[chartDataLabels](/javascript/api/excel/excel.chartdatalabels)|_Свойство_ > numberFormat|Представляет код формата для меток данных.|1.8|
|[chartDataLabels](/javascript/api/excel/excel.chartdatalabels)|_Свойство_ > textOrientation|Представляет ориентацию текста метки данных. Значение должно быть целым числом от -90 до 90 или от 0 до 180 для вертикально-ориентированного текста.|1.8|
|[chartDataLabels](/javascript/api/excel/excel.chartdatalabels)|_Связь_ > horizontalAlignment|Представляет горизонтальное выравнивание для метки данных диаграммы.|1.8|
|[chartDataLabels](/javascript/api/excel/excel.chartdatalabels)|_Связь_ > verticalAlignment|Представляет вертикальное выравнивание метки данных диаграммы.|1.8|
|[chartDeactivatedEventArgs](/javascript/api/excel/excel.chartdeactivatedeventargs)|_Свойство_ > chartId|Получает идентификатор диаграммы, которая деактивирована.|1.8|
|[chartDeactivatedEventArgs](/javascript/api/excel/excel.chartdeactivatedeventargs)|_Свойство_ > type|Получает тип события.|1.8|
|[chartDeactivatedEventArgs](/javascript/api/excel/excel.chartdeactivatedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором деактивирована диаграмма.|1.8|
|[chartDeletedEventArgs](/javascript/api/excel/excel.chartdeletedeventargs)|_Свойство_ > chartId|Получает идентификатор диаграммы, которая удаляется с листа.|1.8|
|[chartDeletedEventArgs](/javascript/api/excel/excel.chartdeletedeventargs)|_Свойство_ > type|Получает тип события.|1.8|
|[chartDeletedEventArgs](/javascript/api/excel/excel.chartdeletedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором удаляется диаграмма.|1.8|
|[chartDeletedEventArgs](/javascript/api/excel/excel.chartdeletedeventargs)|_Связь_ > source|Получает источник события.|1.8|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > height|Представляет высоту legendEntry в условных обозначениях диаграммы. Только для чтения.|1.8|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > index|Представляет индекс legendEntry в условных обозначениях диаграммы. Только для чтения.|1.8|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > left|Представляет левую часть диаграммы legendEntry. Только для чтения.|1.8|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > top|Представляет верх диаграммы legendEntry. Только для чтения.|1.8|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > width|Представляет ширину legendEntry в условных обозначениях диаграммы. Только для чтения.|1.8|
|[chartLegendFormat](/javascript/api/excel/excel.chartlegendformat)|_Связь_ > border|Представляет формат границы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > height|Представляет значения высоты plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > insideHeight|Представляет значение insideHeight для plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > insideLeft|Представляет значение insideLeft для plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > insideTop|Представляет значение insideTop для plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > insideWidth|Представляет значение insideWidth для plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > left|Представляет левое значение plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > top|Представляет верхнее значение plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Свойство_ > width|Представляет значение ширины plotArea.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Связь_ > format|Представляет форматирование для plotArea диаграммы. Только для чтения.|1.8|
|[chartPlotArea](/javascript/api/excel/excel.chartplotarea)|_Связь_ > position|Представляет положение plotArea.|1.8|
|[chartPlotAreaFormat](/javascript/api/excel/excel.chartplotareaformat)|_Связь_ > border|Представляет атрибуты границы для plotArea диаграммы. Только для чтения.|1.8|
|[chartPlotAreaFormat](/javascript/api/excel/excel.chartplotareaformat)|_Связь_ > fill|Представляет формат заливки объекта, включая сведения о форматировании фона. Только для чтения.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > explosion|Возвращает или задает значение развертывания для сектора круговой или кольцевой диаграммы. Возвращает нуль (0) при отсутствии развертывания (верхушка сектора — в центре круговой диаграммы). ReadWrite.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > firstSliceAngle|Возвращает или задает угол первого сектора круговой или кольцевой диаграммы, в градусах (по часовой стрелке из вертикального положения). Применяется только к круговым, объемным круговым и кольцевым диаграммам. Может находиться в диапазоне от 0 до 360. ReadWrite|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > invertIfNegative|Значение true, если Microsoft Excel инвертирует шаблон в элементе, когда он соответствует отрицательному числу. ReadWrite.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > overlap|Указывает на расположение строк и столбцов. Может находиться в диапазоне от -100 до 100. Применяется только к двумерным диаграммам и гистограммам. ReadWrite.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > secondPlotSize|Возвращает или задает размер вторичного раздела круга круговой диаграммы, либо линии круговой диаграммы в процентах от размера основной круговой диаграммы. Может находиться в диапазоне от 5 до 200. ReadWrite.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > varyByCategories|Значение true, если Microsoft Excel назначает разные цвета или шаблоны каждому маркеру данных. Диаграмма должна содержать только один ряд. ReadWrite.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Связь_ > axisGroup|Возвращает или задает группу для указанного ряда. ReadWrite|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Связь_ > dataLabels|Представляет коллекцию всех dataLabels в ряду. Только для чтения.|1.8|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Связь_ > splitType|Возвращает или задает способ разделения двух разделов круга круговой диаграммы либо линии круговой диаграммы. ReadWrite.|1.8|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > backwardPeriod|Представляет число периодов, на которые линия тренда расширяется назад.|1.8|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > forwardPeriod|Представляет число периодов, на которые линия тренда расширяется вперед.|1.8|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > showEquation|Значение true, если формула для линии тренда отображается на диаграмме.|1.8|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > showRSquared|Значение true, если величина достоверности аппроксимации для линии тренда отображается на диаграмме.|1.8|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Связь_ > label|Представляет метку линии тренда диаграммы. Только для чтения.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > autoText|Булево значение, указывающее на то, генерирует ли метка линии тренда автоматически соответствующий текст на основе контекста.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > formula|Строковое значение, которое представляет формулу подписи линии тренда диаграммы с использованием нотации стиля A1.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > height|Возвращает высоту, в пунктах, подписи линии тренда диаграммы. Только для чтения. Значение NULL, если метка линии тренда диаграммы не видна. Только для чтения.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > left|Представляет расстояние в пунктах от левого края подписи линии тренда диаграммы до левого края области диаграммы. Значение NULL, если метка линии тренда диаграммы не видна.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > numberFormat|Строковое значение, которое представляет собой код формата для подписи линии тренда.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > text|Строка, представляющая текст подписи линии тренда на диаграмме.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > textOrientation|Указывает на ориентацию текста подписи линии тренда диаграммы. Значение должно быть целым числом от -90 до 90 или 180 для вертикально-ориентированного текста.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > top|Представляет расстояние в пунктах от верхнего края подписи линии тренда диаграммы до верха области диаграммы. Значение NULL, если метка линии тренда диаграммы не видна.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Свойство_ > width|Возвращает ширину в пунктах подписи линии тренда диаграммы. Только для чтения. Значение NULL, если метка линии тренда диаграммы не видна. Только для чтения.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Связь_ > format|Представляет формат подписи линии тренда диаграммы. Только для чтения.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Связь_ > horizontalAlignment|Представляет горизонтальное выравнивание для подписи линии тренда диаграммы.|1.8|
|[chartTrendlineLabel](/javascript/api/excel/excel.charttrendlinelabel)|_Связь_ > verticalAlignment|Представляет вертикальное выравнивание подписи линии тренда диаграммы.|1.8|
|[chartTrendlineLabelFormat](/javascript/api/excel/excel.charttrendlinelabelformat)|_Связь_ > border|Представляет формат границы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.8|
|[chartTrendlineLabelFormat](/javascript/api/excel/excel.charttrendlinelabelformat)|_Связь_ > fill|Представляет формат заполнения текущей подписи линии тренда диаграммы. Только для чтения.|1.8|
|[chartTrendlineLabelFormat](/javascript/api/excel/excel.charttrendlinelabelformat)|_Связь_ > font|Представляет атрибуты шрифта (имя, размер, цвет и т. д.) для подписи линии тренда диаграммы. Только для чтения. Только для чтения.|1.8|
|[createWorkbookPostProcessAction](/javascript/api/excel/excel.createworkbookpostprocessaction)|_Свойство_ > fakeFileId|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[createWorkbookPostProcessAction](/javascript/api/excel/excel.createworkbookpostprocessaction)|_Свойство_ > fileBase64|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[createWorkbookPostProcessAction](/javascript/api/excel/excel.createworkbookpostprocessaction)|_Связь_ > actionType|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[customDataValidation](/javascript/api/excel/excel.customdatavalidation)|_Свойство_ > formula| Формула проверки настраиваемых данных. Создает специальные правила ввода, например, недопущение появления дубликатов или ограничение итога в диапазоне ячеек.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Свойство_ > id|Идентификатор DataPivotHierarchy. Только для чтения.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Свойство_ > name|Имя DataPivotHierarchy.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Свойство_ > numberFormat|Числовой формат DataPivotHierarchy.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Свойство_ > position|Положение DataPivotHierarchy.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Связь_ > field|Возвращает PivotFields, связанные с DataPivotHierarchy. Только для чтения.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Связь_ > showAs|Определяет, должны ли данные отображаться как конкретные суммарные вычисления или нет.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Связь_ > summarizeBy|Определяет, следует ли отображать все элементы DataPivotHierarchy.|1.8|
|[dataPivotHierarchy](/javascript/api/excel/excel.datapivothierarchy)|_Метод_ > [setToDefault()](/javascript/api/excel/excel.datapivothierarchy#settodefault)|Сброс DataPivotHierarchy до значений по умолчанию.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Свойство_ > items|Коллекция объектов dataPivotHierarchy. Только для чтения.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Метод_ > [add(pivotHierarchy: PivotHierarchy)](/javascript/api/excel/excel.datapivothierarchycollection)|Добавляет PivotHierarchy к текущей оси.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.datapivothierarchycollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.datapivothierarchycollection)|Получает DataPivotHierarchy по своему имени или идентификатору.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.datapivothierarchycollection)|Возвращает DataPivotHierarchy по имени. Если DataPivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[dataPivotHierarchyCollection](/javascript/api/excel/excel.datapivothierarchycollection)|_Метод_ > [remove(DataPivotHierarchy: DataPivotHierarchy)](/javascript/api/excel/excel.datapivothierarchycollection)|Удаляет PivotHierarchy из текущей оси.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Свойство_ > ignoreBlanks|Игнорировать пустые ячейки: проверка данных не будет выполняться в пустых ячейках, по умолчанию используется значение true.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Свойство_ > valid|Указывает на то, являются ли все значения ячеек допустимыми в соответствии с правилами проверки данных. Только для чтения.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Связь_ > errorAlert|Сообщение об ошибке, когда пользователь вводит недопустимые данные.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Связь_ > prompt|Подсказка, когда пользователь выбирает ячейку.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Связь_ > rule|Правило проверки данных, которое содержит различные типы условий проверки данных.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Связь_ > type|Тип проверки данных, см. [Excel.DataValidationType](/javascript/api/excel/excel.datavalidationtype) для получения дополнительных сведений. Только для чтения.|1.8|
|[dataValidation](/javascript/api/excel/excel.datavalidation)|_Метод_ > [clear()](/javascript/api/excel/excel.datavalidation)|Очищает проверку данных из текущего диапазона.|1.8|
|[dataValidationErrorAlert](/javascript/api/excel/excel.datavalidationerroralert)|_Свойство_ > message|Представляет сообщение-предупреждение об ошибке.|1.8|
|[dataValidationErrorAlert](/javascript/api/excel/excel.datavalidationerroralert)|_Свойство_ > showAlert|Определяет, показывать ли диалоговое окно с предупреждением об ошибке или нет, когда пользователь вводит неверные данные. Значение по умолчанию: true.|1.8|
|[dataValidationErrorAlert](/javascript/api/excel/excel.datavalidationerroralert)|_Свойство_ > title|Представляет заголовок диалогового окна предупреждения об ошибке.|1.8|
|[dataValidationErrorAlert](/javascript/api/excel/excel.datavalidationerroralert)|_Связь_ > style|Представляет тип предупреждения проверки данных, см. [Excel.DataValidationAlertStyle](/javascript/api/excel/excel.datavalidationalertstyle) для получения дополнительной информации.|1.8|
|[dataValidationPrompt](/javascript/api/excel/excel.datavalidationprompt)|_Свойство_ > message|Представляет сообщение подсказки.|1.8|
|[dataValidationPrompt](/javascript/api/excel/excel.datavalidationprompt)|_Свойство_ > showPrompt|Определяет, показывать ли подсказку, когда пользователь выбирает ячейку с проверкой данных.|1.8|
|[dataValidationPrompt](/javascript/api/excel/excel.datavalidationprompt)|_Свойство_ > title|Представляет заголовок подсказки.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > custom|Условия проверки настраиваемых данных.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > date|Критерии проверки данных даты.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > decimal|Критерий проверки десятичных данных.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > list|Критерии проверки данных списка.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > textLength|Критерии проверки данных TextLength.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > time|Критерии проверки данных времени.|1.8|
|[dataValidationRule](/javascript/api/excel/excel.datavalidationrule)|_Связь_ > wholeNumber|Критерии проверки данных WholeNumber.|1.8|
|[dateTimeDataValidation](/javascript/api/excel/excel.datetimedatavalidation)|_Свойство_ > formula1|Получает или задает Formula1, то есть минимальное значение или значение в зависимости от оператора.|1.8|
|[dateTimeDataValidation](/javascript/api/excel/excel.datetimedatavalidation)|_Свойство_ > formula2|Получает или задает Formula2, то есть максимальное значение или значение в зависимости от оператора.|1.8|
|[dateTimeDataValidation](/javascript/api/excel/excel.datetimedatavalidation)|_Связь_ > operator|Оператор, используемый для проверки данных.|1.8|
|[enableEventsPostProcessAction](/javascript/api/excel/excel.enableeventspostprocessaction)|_Свойство_ > isEnableEvents{|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[enableEventsPostProcessAction](/javascript/api/excel/excel.enableeventspostprocessaction)|_Связь_ > actionType|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[enableEventsPostProcessAction](/javascript/api/excel/excel.enableeventspostprocessaction)|_Связь_ > controlId|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Свойство_ > enableMultipleFilterItems|Определяет, следует ли разрешить несколько элементов фильтра.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Свойство_ > id|Идентификатор FilterPivotHierarchy. Только для чтения.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Свойство_ > name|Имя FilterPivotHierarchy.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Свойство_ > position|Положение FilterPivotHierarchy.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Связь_ > fields|Возвращает сводные поля, связанные с FilterPivotHierarchy. Только для чтения.|1.8|
|[filterPivotHierarchy](/javascript/api/excel/excel.filterpivothierarchy)|_Метод_ > [setToDefault()](/javascript/api/excel/excel.filterpivothierarchy)|Сброс FilterPivotHierarchy до значения по умолчанию.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Свойство_ > items|Коллекция объектов filterPivotHierarchy. Только для чтения.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Метод_ > [add(pivotHierarchy: PivotHierarchy)](/javascript/api/excel/excel.filterpivothierarchycollection)|Добавляет PivotHierarchy к текущей оси. Если иерархия присутствует в другом месте строки, столбца или оси фильтра, она будет удалена из этого местоположения.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.filterpivothierarchycollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.filterpivothierarchycollection)|Получает FilterPivotHierarchy по имени или идентификатору.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.filterpivothierarchycollection)|Возвращает FilterPivotHierarchy по имени. Если FilterPivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[filterPivotHierarchyCollection](/javascript/api/excel/excel.filterpivothierarchycollection)|_Метод_ > [remove(filterPivotHierarchy: FilterPivotHierarchy)](/javascript/api/excel/excel.filterpivothierarchycollection)|Удаляет PivotHierarchy из текущей оси.|1.8|
|[listDataValidation](/javascript/api/excel/excel.listdatavalidation)|_Свойство_ > inCellDropDown|Отображает или не отображает список в раскрывающемся меню ячейки, по умолчанию используется значение true.|1.8|
|[listDataValidation](/javascript/api/excel/excel.listdatavalidation)|_Свойство_ > source|Источник списка для проверки данных|1.8|
|[openWorkbookPostProcessAction](/javascript/api/excel/excel.openworkbookpostprocessaction)|_Свойство_ > fakeFileId|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[openWorkbookPostProcessAction](/javascript/api/excel/excel.openworkbookpostprocessaction)|_Связь_ > actionType|Передает дополнительные данные на сторону клиента, например, worksheetId для TableSelectionChangedEvent.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Свойство_ > id|Идентификатор сводного поля. Только для чтения.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Свойство_ > name|Имя сводного поля.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Свойство_ > showAllItems|Определяет, следует ли отображать все элементы сводных полей.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Связь_ > items|Возвращает сводные поля, связанные со сводным полем. Только для чтения.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Связь_ > subtotals|Промежуточные итоги сводного поля.|1.8|
|[pivotField](/javascript/api/excel/excel.pivotfield)|_Метод_ > [sortByLabels(sortby: SortBy)](/javascript/api/excel/excel.pivotfield)|Сортирует сводное поле. Если указана DataPivotHierarchy, то сортировка будет применяться на ее основе, в ином случае сортировка будет основываться на самом сводном поле.|1.8|
|[pivotFieldCollection](/javascript/api/excel/excel.pivotfieldcollection)|_Свойство_ > items|Коллекция объектов сводных полей. Только для чтения.|1.8|
|[pivotFieldCollection](/javascript/api/excel/excel.pivotfieldcollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.pivotfieldcollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[pivotFieldCollection](/javascript/api/excel/excel.pivotfieldcollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.pivotfieldcollection)|Получает PivotHierarchy по имени или идентификатору.|1.8|
|[pivotFieldCollection](/javascript/api/excel/excel.pivotfieldcollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.pivotfieldcollection)|Возвращает PivotHierarchy по имени. Если PivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[pivotHierarchy](/javascript/api/excel/excel.pivothierarchy)|_Свойство_ > id|Идентификатор PivotHierarchy. Только для чтения.|1.8|
|[pivotHierarchy](/javascript/api/excel/excel.pivothierarchy)|_Свойство_ > name|Имя PivotHierarchy.|1.8|
|[pivotHierarchy](/javascript/api/excel/excel.pivothierarchy)|_Связь_ > fields|Возвращает сводные поля, связанные с PivotHierarchy. Только для чтения.|1.8|
|[pivotHierarchyCollection](/javascript/api/excel/excel.pivothierarchycollection)|_Свойство_ > items|Коллекция объектов pivotHierarchy. Только для чтения.|1.8|
|[pivotHierarchyCollection](/javascript/api/excel/excel.pivothierarchycollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.pivothierarchycollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[pivotHierarchyCollection](/javascript/api/excel/excel.pivothierarchycollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.pivothierarchycollection)|Получает PivotHierarchy по имени или идентификатору.|1.8|
|[pivotHierarchyCollection](/javascript/api/excel/excel.pivothierarchycollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.pivothierarchycollection)|Возвращает PivotHierarchy по имени. Если PivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[pivotItem](/javascript/api/excel/excel.pivotitem)|_Свойство_ > id|Идентификатор элемента сводной таблицы. Только для чтения.|1.8|
|[pivotItem](/javascript/api/excel/excel.pivotitem)|_Свойство_ > isExpanded|Определяет, развернут ли элемент для отображения дочерних элементов или же свернут, а дочерние элементы являются скрытыми.|1.8|
|[pivotItem](/javascript/api/excel/excel.pivotitem)|_Свойство_ > name|Имя элемента сводной таблицы.|1.8|
|[pivotItem](/javascript/api/excel/excel.pivotitem)|_Свойство_ > visible|Определяет, отображается ли элемент сводной таблицы или нет.|1.8|
|[pivotItemCollection](/javascript/api/excel/excel.pivotitemcollection)|_Свойство_ > items|Коллекция объектов элемента сводной таблицы. Только для чтения.|1.8|
|[pivotItemCollection](/javascript/api/excel/excel.pivotitemcollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.pivotitemcollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[pivotItemCollection](/javascript/api/excel/excel.pivotitemcollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.pivotitemcollection)|Получает PivotHierarchy по имени или идентификатору.|1.8|
|[pivotItemCollection](/javascript/api/excel/excel.pivotitemcollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.pivotitemcollection)|Возвращает PivotHierarchy по имени. Если PivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Свойство_ > showColumnGrandTotals|Значение true, если отчет сводной таблицы отображает общие итоги для столбцов.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Свойство_ > showRowGrandTotals|Значение true, если отчет сводной таблицы отображает общие итоги для строк.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Свойство_ > subtotalLocation|Это свойство показывает SubtotalLocationType всех полей в сводной таблице. Если поля имеют различные состояния, оно будет иметь значение NULL. Возможные значения: AtTop, AtBottom.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Связь_ > layoutType|Это свойство показывает PivotLayoutType всех полей в сводной таблице. Если поля имеют различные состояния, оно будет иметь значение NULL.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Метод_ > [getColumnLabelRange()](/javascript/api/excel/excel.pivotlayout)|Возвращает диапазон, где находятся названия столбцов сводной таблицы.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Метод_ > [getDataBodyRange()](/javascript/api/excel/excel.pivotlayout)|Возвращает диапазон, где находятся значения данных сводной таблицы.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout.md)|_Метод_ > [getFilterAxisRange()](/javascript/api/excel/excel.pivotlayout)|Возвращает диапазон области фильтра сводной таблицы.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Метод_ > [getRange()](/javascript/api/excel/excel.pivotlayout)|Возвращает диапазон, в котором существует сводная таблица, за исключением области фильтра.|1.8|
|[pivotLayout](/javascript/api/excel/excel.pivotlayout)|_Метод_ > [getRowLabelRange()](/javascript/api/excel/excel.pivotlayout)|Возвращает диапазон, где находятся названия строк сводной таблицы.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > columnHierarchies|Иерархии сводных столбцов сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > dataHierarchies|Иерархии сводных данных сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > filterHierarchies|Иерархии сводных фильтров сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > hierarchies|Иерархии сводного документа сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > layout|PivotLayout, описывающий макет и визуальную структуру сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > rowHierarchies|Иерархии сводной строки сводной таблицы. Только для чтения.|1.8|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Метод_ > [delete()](/javascript/api/excel/excel.pivottable)|Удаляет сводную таблицу.|1.8|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Метод_ > [add(name: string, source: object, destination: object)](/javascript/api/excel/excel.pivottablecollection)|Добавление сводной таблицы на основе указанных исходных данных и вставка ее в верхнюю левую ячейку конечного диапазона.|1.8|
|[диапазон](/javascript/api/excel/excel.range)|_Связь_ > dataValidation|Возвращает объект проверки данных. Только для чтения.|1.8|
|[rowColumnPivotHierarchy](/javascript/api/excel/excel.rowcolumnpivothierarchy)|_Свойство_ > id|Идентификатор RowColumnPivotHierarchy. Только для чтения.|1.8|
|[rowColumnPivotHierarchy](/javascript/api/excel/excel.rowcolumnpivothierarchy)|_Свойство_ > name|Имя RowColumnPivotHierarchy.|1.8|
|[rowColumnPivotHierarchy](/javascript/api/excel/excel.rowcolumnpivothierarchy)|_Свойство_ > position|Положение RowColumnPivotHierarchy.|1.8|
|[rowColumnPivotHierarchy](/javascript/api/excel/excel.rowcolumnpivothierarchy)|_Связь_ > fields|Возвращает сводные поля, связанные с RowColumnPivotHierarchy. Только для чтения.|1.8|
|[rowColumnPivotHierarchy](/javascript/api/excel/excel.rowcolumnpivothierarchy)|_Метод_ > [setToDefault()](/javascript/api/excel/excel.rowcolumnpivothierarchy)|Сброс RowColumnPivotHierarchy до значений по умолчанию.|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Свойство_ > items|Коллекция объектов rowColumnPivotHierarchy. Только для чтения.|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Метод_ > [add(pivotHierarchy: PivotHierarchy)](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|Добавляет PivotHierarchy к текущей оси. Если иерархия присутствует в другом месте строки, столбца,|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Метод_ > [getCount()](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|Возвращает количество иерархий сводного документа в коллекцию.|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Метод_ > [getItem(name: string)](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|Получает RowColumnPivotHierarchy по имени или идентификатору.|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Метод_ > [getItemOrNullObject(name: string)](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|Возвращает RowColumnPivotHierarchy по имени. Если RowColumnPivotHierarchy не существует, возвращает значение пустого объекта.|1.8|
|[rowColumnPivotHierarchyCollection](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|_Метод_ > [remove(rowColumnPivotHierarchy: RowColumnPivotHierarchy)](/javascript/api/excel/excel.rowcolumnpivothierarchycollection)|Удаляет PivotHierarchy из текущей оси.|1.8|
|[среда выполнения](/javascript/api/excel/excel.runtime)|_Свойство_ > enableEvents|Переключить события JavaScript в текущей панели задач или надстройке содержимого.|1.8|
|[showAsRule](/javascript/api/excel/excel.showasrule)|_Связь_ > baseField|Базовый PivotField для обоснования расчета ShowAs, если применимо на основе типа ShowAsCalculation, в противном случае значение будет пустым.|1.8|
|[showAsRule](/javascript/api/excel/excel.showasrule)|_Связь_ > baseItem|Базовый элемент для обоснования расчета ShowAs, если применимо на основе типа ShowAsCalculation, в противном случае значение будет пустым.|1.8|
|[showAsRule](/javascript/api/excel/excel.showasrule)|_Связь_ > calculation|Расчет ShowAs для использования в Data PivotField.|1.8|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > autoIndent|Указывает, будет ли выполнен автоматический отступ для текста, если выравнивание текста в ячейке установлено на равномерное распределение.|1.8|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > textOrientation|Ориентация текста для стиля.|1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > automatic|Если для параметра "Автоматически" установлено значение true, все остальные значения будут игнорироваться при настройке промежуточных итогов.|1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > average| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > count| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > countNumbers| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > max| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > min| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > product| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > standardDeviation| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > standardDeviationP| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > sum| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > variance| |1.8|
|[subtotals](/javascript/api/excel/excel.subtotals)|_Свойство_ > varianceP| |1.8|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > legacyId|Возвращает числовой идентификатор. Только для чтения.|1.8|
|[workbook](/javascript/api/excel/excel.workbook)|_Свойство_ > только для чтения|Значение true, если книга открыта в режиме только для чтения. Только для чтения.|1.8|
|[workbookCreated](/javascript/api/excel/excel.workbookcreated)|_Свойство_ > id|Возвращает значение, уникальным образом идентифицирующее объект WorkbookCreated. Только для чтения.|1.8|
|[workbookCreated](/javascript/api/excel/excel.workbookcreated)|_Метод_ > [open()](/javascript/api/excel/excel.workbookcreated)|Откройте книгу.|1.8|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > showGridlines|Получает или задает флаг линии сетки рабочего листа.|1.8|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > showHeadings|Получает или задает флаг заголовков рабочего листа.|1.8|
|[worksheetCalculatedEventArgs](/javascript/api/excel/excel.worksheetcalculatedeventargs)|_Свойство_ > type|Получает тип события.|1.8|
|[worksheetCalculatedEventArgs](/javascript/api/excel/excel.worksheetcalculatedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, который рассчитывается.|1.8|

## <a name="whats-new-in-excel-javascript-api-17"></a>Новые возможности API JavaScript для Excel 1.7

Функции набора требований 1.7 к API JavaScript Excel включают в себя API для диаграмм, событий, рабочих листов, диапазонов, свойств документа, названных элементов, параметров защиты и стилей.

### <a name="customize-charts"></a>Настройка диаграмм

С помощью новых API диаграмм вы можете создавать дополнительные типы диаграмм, добавлять ряды данных в диаграмму, задавать заголовок диаграммы, добавлять заголовок оси, добавлять единицы отображения, добавлять линию тренда со скользящей средней, менять линию тренда на линейную и многое другое. Ниже приводятся некоторые примеры:

* Ось диаграммы — получайте, задавайте, форматируйте и удаляйте единицу, метку и заголовок оси на диаграмме.
* Ряды диаграммы — добавляйте, задавайте и удаляйте ряды в диаграмме.  Изменяйте метки рядов, порядок и размер построения.
* Трендовые линии диаграммы — добавляйте, получайте и форматируйте линий тренда на диаграмме.
* Условные обозначения диаграммы — форматируйте шрифт условных обозначений на диаграмме.
* Точка диаграммы — задавайте цвет точки диаграммы.
* Подстрока заголовка диаграммы — получайте и задавайте подстроку заголовка для диаграммы.
* Тип диаграммы — параметр для создания дополнительных типов диаграмм.

### <a name="events"></a>События

API-интерфейсы Excel предоставляют множество обработчиков событий, которые позволяют вашей надстройке автоматически запускать назначенную функцию при возникновении определенного события. Вы можете настроить эту функцию на выполнение любых действий, необходимых для вашего сценария. Список доступных событий см. в разделе [Работа с событиями с помощью API JavaScript для Excel](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-events).

### <a name="customize-the-appearance-of-worksheets-and-ranges"></a>Настройка внешнего вида таблиц и диапазонов

С помощью новых интерфейсов API, можно настроить внешний вид таблицы несколькими способами:

* Закрепляйте панели, чтобы отображать отдельные строки или столбцы при прокрутке листа. Например, если первая строка на вашем листе содержит заголовки, вы можете закрепить эту строку, чтобы заголовки столбцов оставались видимыми при прокрутке листа.
* Изменение цвета вкладки листа.
* Добавление заголовков рабочего листа.


Можно настроить внешний вид диапазонов несколькими способами:

* Задавайте стиль ячейки для диапазона, чтобы обеспечить для всех ячеек в диапазоне согласующееся форматирование. Стиль ячейки — определенный набор параметров форматирования, таких как шрифты и размеры шрифтов, форматы чисел, границы ячейки и заливка ячеек. Используйте любой из встроенных стилей ячеек Excel или создайте свой собственный стиль ячейки.
* Настройка ориентации текста для диапазона.
* Добавляйте или изменяйте гиперссылку в диапазоне, который ссылается на другое место в рабочей книге или на внешнее местоположение.

### <a name="manage-document-properties"></a>Управление свойствами документа

Используя API-интерфейсы свойств документа, вы можете получить доступ к встроенным свойствам документа, а также создавать и управлять настраиваемыми свойствами документа для хранения состояния книги и рабочего процесса привода, а также бизнес-логики.

### <a name="copy-worksheets"></a>Копирование листов

Используя API-интерфейсы копирования рабочего листа, вы можете копировать данные и формат с одного листа на новый рабочий лист в пределах одной рабочей книги и уменьшить объем необходимой передачи данных.

### <a name="handle-ranges-with-ease"></a>Легкая и удобная обработка диапазонов

Используя различные API-интерфейсы диапазона, вы можете выполнять такие действия, как получение окружающего региона, получение диапазона с измененными размерами и многое другое. Эти API должны выполнять такие задачи, как манипуляции с диапазонами и более эффективные адресации.

Кроме того:

* Параметры защиты рабочей книги и рабочего листа — используйте эти API для защиты данных на листе и в структуре рабочей книги.
* Обновление именованного элемента — используйте этот API для обновления именованного элемента.
* Получение активной ячейки — используйте этот API для получения активной ячейки рабочей книги.

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > chartType|Представляет тип диаграммы. Возможные значения: ColumnClustered, ColumnStacked, ColumnStacked100, BarClustered, BarStacked, BarStacked100, LineStacked, LineStacked100, LineMarkers, LineMarkersStacked, LineMarkersStacked100, PieOfPie, и т.д.|1.7|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > id|Уникальный идентификатор диаграммы. Только для чтения.|1.7|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > showAllFieldButtons|Указывает на то, следует отображать ли все кнопки поля в сводной диаграмме.|1.7|
|[chartAreaFormat](/javascript/api/excel/excel.chartareaformat)|_Связь_ > border|Представляет формат области диаграммы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.7|
|[chartAxes](/javascript/api/excel/excel.chartaxes)|_Метод_ > getItem(type: string, group: string)|Возвращает определенную ось, идентифицируемую по типу и группе.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > axisBetweenCategories|Указывает, пересекает ли ось значений ось категорий между категориями.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > axisGroup|Представляет группу для указанной оси. Только для чтения. Возможные значения: Primary, Secondary.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > categoryType|Возвращает или задает тип оси категории. Возможные значения: Automatic, TextAxis, DateAxis.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > crosses|Представляет указанную ось там, где ее пересекает другая ось. Возможные значения: Automatic, Maximum, Minimum, Custom.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > crossesAt|Представляет указанную ось там, где ее пересекает другая ось. Только для чтения. Для этого свойства следует использовать метод SetCrossesAt (double). Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > customDisplayUnit|Представляет значение единицы отображения настраиваемой оси. Только для чтения. Чтобы задать это свойство, используйте метод SetCustomDisplayUnit(double). Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > displayUnit|Представляет единицу отображения оси. Возможные значения: None, Hundreds, Thousands, TenThousands, HundredThousands, Millions, TenMillions, HundredMillions, Billions, Trillions, Custom.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > height|Представляет высоту, в пунктах, оси диаграммы. Значение NULL, если ось не видна. Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > left|Представляет расстояние, в пунктах, от левого края оси до левой стороны области диаграммы. Значение NULL, если ось не видна. Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > logBase|Представляет базу логарифма при использовании логарифмических шкал.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > reversePlotOrder|Указывает на то, отображает ли Microsoft Excel точки данных от последней к первой.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > scaleType|Представляет тип шкалы оси значений. Возможные значения: линейная, логарифмическая.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > showDisplayUnitLabel|Указывает на то, видна ли метка единицы отображения оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > tickLabelSpacing|Представляет количество категорий или серий между метками делений шкалы. Может иметь значение от 1 до 31999 или пустую строку для автоматической настройки. Возвращаемое значение всегда является числом.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > tickMarkSpacing|Представляет количество категорий или серий между метками делений.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > top|Представляет расстояние, в пунктах, от верхнего края оси до верха области диаграммы. Значение NULL, если ось не видна. Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > type|Представляет тип оси. Только для чтения. Возможные значения: Invalid, Category, Value, Series.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > visible|Логическое значение представляет видимость оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Свойство_ > width|Представляет ширину объекта диаграммы в пунктах. Значение NULL, если ось не видна. Только для чтения.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > baseTimeUnit|Возвращает или задает базовую единицу для указанной оси категории.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > majorTickMark|Представляет тип основного деления шкалы для указанной оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > majorTimeUnitScale|Возвращает или задает основное значение шкалы единицы для оси категории, если для свойства CategoryType установлено значение TimeScale.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > minorTickMark|Представляет тип дополнительного деления шкалы для указанной оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > minorTimeUnitScale|Возвращает или задает дополнительное значение шкалы единицы для оси категории, если для свойства CategoryType установлено значение TimeScale.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Связь_ > tickLabelPosition|Представляет положение меток делений на указанной оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Метод_ > setCategoryNames(sourceData: Range)|Устанавливает все имена категорий для указанной оси.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Метод_ > setCrossesAt(value: double)|Задает указанную ось там, где ее пересекает другая ось.|1.7|
|[chartAxis](/javascript/api/excel/excel.chartaxis)|_Метод_ > setCustomDisplayUnit(value: double)|Задает единицу отображения в виде настраиваемого значения.|1.7|
|[chartBorder](/javascript/api/excel/excel.chartborder)|_Свойство_ > color|Цветовой код HTML, представляющий цвет границ в диаграмме.|1.7|
|[chartBorder](/javascript/api/excel/excel.chartborder)|_Свойство_ > weight|Представляет вес границы, в пунктах.|1.7|
|[chartBorder](/javascript/api/excel/excel.chartborder)|_Связь_ > lineStyle|Представляет тип линии границы.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > position|Значение DataLabelPosition, которое представляет положение метки данных. Возможные значения: None, Center, InsideEnd, InsideBase, OutsideEnd, Left, Right, Top, Bottom, BestFit, Callout.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > separator|Строка, представляющая разделитель для меток данных на диаграмме.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showBubbleSize|Логическое значение, которое указывает, отображается ли размер пузырьков с метками данных.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showCategoryName|Логическое значение, которое указывает, отображается ли имя для категории меток данных.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showLegendKey|Логическое значение, которое указывает, отображаются ли условные обозначения для меток данных.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showPercentage|Логическое значение, которое указывает, отображается ли процентное соотношение меток данных.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showSeriesName|Логическое значение, которое указывает, отображается ли имя ряда для меток данных.|1.7|
|[chartDataLabel](/javascript/api/excel/excel.chartdatalabel)|_Свойство_ > showValue|Логическое значение, которое указывает, отображается ли значение метки данных.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Свойство_ > height|Представляет высоту условного обозначения диаграммы.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Свойство_ > left|Представляет левую часть условного обозначения диаграммы.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Свойство_ > showShadow|Указывает, имеют ли условные обозначения тень на диаграмме.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Свойство_ > top|Представляет верх условных обозначений диаграммы.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Свойство_ > width|Представляет ширину условных обозначений диаграммы.|1.7|
|[chartLegend](/javascript/api/excel/excel.chartlegend)|_Связь_ > legendEntries|Представляет коллекцию legendEntries в условных обозначениях. Только для чтения.|1.7|
|[chartLegendEntry](/javascript/api/excel/excel.chartlegendentry)|_Свойство_ > visible|Представляет видимый элемент записи условных обозначений диаграммы.|1.7|
|[chartLegendEntryCollection](/javascript/api/excel/excel.chartlegendentrycollection)|_Свойство_ > items|Коллекция объектов chartLegendEntry. Только для чтения.|1.7|
|[chartLegendEntryCollection](/javascript/api/excel/excel.chartlegendentrycollection)|_Метод_ > getCount()|Возвращает число legendEntry в коллекцию.|1.7|
|[chartLegendEntryCollection](/javascript/api/excel/excel.chartlegendentrycollection)|_Метод_ > getItemAt(index: number)|Возвращает legendEntry по указанному индексу.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Свойство_ > hasDataLabel|Указывает, имеет ли точка данных dataLabel. Неприменимо для поверхностных диаграмм.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Свойство_ > markerBackgroundColor|Представление цветового кода HTML для цвета фона метки точки данных. Пример: #FF0000 обозначает красный.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Свойство_ > markerForegroundColor|Представление цветового кода в HTML для основного цвета метки точки данных. Пример: #FF0000 обозначает красный.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Свойство_ > markerSize|Представляет размер метки точки данных.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Свойство_ > markerStyle|Представляет стиль метки точки данных диаграммы. Возможные значения: Invalid, Automatic, None, Square, Diamond, Triangle, X, Star, Dot, Dash, Circle, Plus, Picture.|1.7|
|[chartPoint](/javascript/api/excel/excel.chartpoint)|_Связь_ > dataLabel|Возвращает метки данных точки диаграммы. Только для чтения.|1.7|
|[chartPointFormat](/javascript/api/excel/excel.chartpointformat)|_Связь_ > border|Представляет формат границы точки данных диаграммы, включая информацио о цвете, стиле и весе. Только для чтения.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > chartType|Представляет тип диаграммы для ряда. Возможные значения: ColumnClustered, ColumnStacked, ColumnStacked100, BarClustered, BarStacked, BarStacked100, LineStacked, LineStacked100, LineMarkers, LineMarkersStacked, LineMarkersStacked100, PieOfPie, и т.д.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > doughnutHoleSize|Представляет размер отверстия ряда кольцевой диаграммы.  Допустимо только в doughnutExploded и кольцевых диаграммах.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > filtered|Логическое значение, указывающее на то, фильтруется ряд или нет. Неприменимо для поверхностных диаграмм.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > gapWidth|Представляет ширину разрывов рядов диаграммы.  Допустимо только для линейчатых диаграмм и гистограмм, а также|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > hasDataLabels|Логическое значение, указывающее, имеют ли ряды метки данных.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > markerBackgroundColor|Представляет цвет фона метки рядов диаграммы.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > markerForegroundColor|Представляет основной цвет метки рядов диаграммы.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > markerSize|Представляет размер метки рядов диаграммы.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > markerStyle|Представляет стиль метки рядов диаграммы. Возможные значения: Invalid, Automatic, None, Square, Diamond, Triangle, X, Star, Dot, Dash, Circle, Plus, Picture.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > plotOrder|Представляет порядок отображения рядов диаграммы в группе диаграммы.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > showShadow|Логическое значение, указывающее на наличие тени для ряда.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Свойство_ > smooth|Логическое значение, указывающее на то, является ли ряд плавным. Только для графиков и точечных диаграмм.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Связь_ > dataLabels|Представляет коллекцию всех dataLabels в ряду. Только для чтения.|ApiSet.InProgressFeatures.ChartingAPI|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Связь_ > trendlines|Представляет коллекцию линий тренда в ряду. Только для чтения.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Метод_ > delete()|Удаляет ряд диаграммы.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Метод_ > setBubbleSizes(sourceData: Range)|Настройка размеров пузырьков для ряда диаграммы. Работает только для пузырьковых диаграмм.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Метод_ > setValues(sourceData: Range)|Задание значения для ряда диаграммы. Для точечных диаграмм это означает значения оси Y.|1.7|
|[chartSeries](/javascript/api/excel/excel.chartseries)|_Метод_ > setXAxisValues(sourceData: Range)|Задание значения оси X для ряда диаграммы. Работает только для точечных диаграмм.|1.7|
|[chartSeriesCollection](/javascript/api/excel/excel.chartseriescollection)|_Метод_ > add(name: string, index: number)|Добавление новой серии в коллекцию.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > height|Возвращает высоту, в пунктах, заголовка диаграммы. Только для чтения. Значение NULL, если заголовок диаграммы не виден. Только для чтения.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > horizontalAlignment|Представляет горизонтальное выравнивание для заголовка диаграммы. Возможные значения: Center, Left, Justify, Distributed, Right.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > left|Представляет расстояние в пунктах от левого края заголовка диаграммы до левого края области диаграммы. Значение NULL, если заголовок диаграммы не виден.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > position|Представляет положение заголовка диаграммы. Возможные значения: Top, Automatic, Bottom, Right, Left.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > showShadow|Представляет логическое значение, которое определяет, имеет ли заголовок диаграммы тень.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > textOrientation|Представляет ориентацию текста заголовка диаграммы. Значение должно быть целым числом от -90 до 90 или 180 для вертикально-ориентированного текста.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > top|Представляет расстояние в пунктах от верхнего края заголовка диаграммы до верха области диаграммы. Значение NULL, если заголовок диаграммы не виден.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > verticalAlignment|Представляет вертикальное выравнивание заголовка диаграммы. Возможные значения: Center, Bottom, Top, Justify, Distributed.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Свойство_ > width|Возвращает ширину, в пунктах, заголовка диаграммы. Только для чтения. Значение NULL, если заголовок диаграммы не виден. Только для чтения.|1.7|
|[chartTitle](/javascript/api/excel/excel.charttitle)|_Метод_ > setFormula(formula: string)|Строковое значение, которое представляет формулу заголовка диаграммы с использованием нотации стиля A1.|1.7|
|[chartTitleFormat](/javascript/api/excel/excel.charttitleformat)|_Связь_ > border|Представляет формат границы заголовка диаграммы, который включает цвет, свойство LineStyle и вес. Только для чтения.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > backward|Представляет число периодов, на которые линия тренда расширяется назад.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > displayEquation|Значение true, если формула для линии тренда отображается на диаграмме.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > displayRSquared|Значение true, если величина достоверности аппроксимации для линии тренда отображается на диаграмме.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > forward|Представляет число периодов, на которые линия тренда расширяется вперед.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > intercept|Представляет значение отсекаемого отрезка линии тренда. Может быть присвоено числовое значение или пустая строка (для автоматических значений). Возвращаемое значение всегда является числом.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > movingAveragePeriod|Представляет собой период линии тренда диаграммы только для линии тренда с типом MovingAverage.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > name|Представляет имя линии тренда. Может быть присвоено строковое значение, или можно задать значение NULL для автоматических значений. Возвращаемое значение всегда является строковым|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > polynomialOrder|Представляет порядок линии тренда диаграммы для линии тренда с типом Polynomial.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Свойство_ > type|Представляет тип линии тренда диаграммы. Возможные значения: Linear, Exponential, Logarithmic, MovingAverage, Polynomial, Power.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Связь_ > format|Представляет форматирование линии тренда диаграммы. Только для чтения.|1.7|
|[chartTrendline](/javascript/api/excel/excel.charttrendline)|_Метод_ > delete()|Удаление объекта линии тренда.|1.7|
|[chartTrendlineCollection](/javascript/api/excel/excel.charttrendlinecollection)|_Свойство_ > items|Коллекция объектов chartTrendline. Только для чтения.|1.7|
|[chartTrendlineCollection](/javascript/api/excel/excel.charttrendlinecollection)|_Метод_ > add(type: string)|Добавляет новую линию тренда в коллекцию линий тренда.|1.7|
|[chartTrendlineCollection](/javascript/api/excel/excel.charttrendlinecollection)|_Метод_ > getCount()|Возвращает число линий тренда в коллекции.|1.7|
|[chartTrendlineCollection](/javascript/api/excel/excel.charttrendlinecollection)|_Метод_ > getItem(index: number)|Получайте объект линии тренда по индексу, который является порядком вставки в массиве элементов.|1.7|
|[chartTrendlineFormat](/javascript/api/excel/excel.charttrendlineformat)|_Связь_ > line|Представляет форматирование линий диаграммы. Только для чтения.|1.7|
|[customProperty](/javascript/api/excel/excel.customproperty)|_Свойство_ > key|Возвращает ключ настраиваемого свойства. Только для чтения. Только для чтения.|1.7|
|[customProperty](/javascript/api/excel/excel.customproperty)|_Свойство_ > type|Возвращает значение настраиваемого свойства. Только для чтения. Только для чтения. Возможные значения: Number, Boolean, Date, String, Float.|1.7|
|[customProperty](/javascript/api/excel/excel.customproperty)|_Свойство_ > value|Возвращает или задает значение настраиваемого свойства.|1.7|
|[customProperty](/javascript/api/excel/excel.customproperty)|_Метод_ > delete()|Удаляет настраиваемое свойство.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Свойство_ > items|Коллекция объектов customProperty. Только для чтения.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Метод_ > add(key: string, value: object)|Создает или задает настраиваемое свойство.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Метод_ > deleteAll()|Удаляет все настраиваемые свойства в коллекции.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Метод_ > getCount()|Возвращает количество настраиваемых свойств.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Метод_ > getItem(key: string)|Возвращает объект custom property по ключу, нечувствительному к регистру. Выдает ошибку, если настраиваемое свойство не существует.|1.7|
|[customPropertyCollection](/javascript/api/excel/excel.custompropertycollection)|_Метод_ > getItemOrNullObject(key: string)|Возвращает объект custom property по ключу, нечувствительному к регистру. Возвращает объект null, если настраиваемое свойство не существует.|1.7|
|[dataConnectionCollection](/javascript/api/excel/excel.dataconnectioncollection)|_Свойство_ > items|Коллекция объектов dataConnection. Только для чтения.|1.7|
|[dataConnectionCollection](/javascript/api/excel/excel.dataconnectioncollection)|_Метод_ > refreshAll()|Обновляет все подключения к данным в коллекции.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > author|Получает или задает автора книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > category|Получает или задает категорию рабочей книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > comments|Получает или задает комментарии рабочей книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > company|Получает или задает организацию рабочей книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > keywords|Получает или задает ключевые слова рабочей книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > lastAuthor|Возвращает последнего автора книги. Только для чтения. Только для чтения.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > manager|Получает или задает менеджера книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > revisionNumber|Возвращает номер редакции книги. Только для чтения.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > subject|Получает или задает тему книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Свойство_ > title|Получает или задает заголовок книги.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Связь_ > creationDate|Возвращает дату создания книги. Только для чтения. Только для чтения.|1.7|
|[documentProperties](/javascript/api/excel/excel.documentproperties)|_Связь_ > custom|Возвращает коллекцию настраиваемых свойств книги. Только для чтения. Только для чтения.|1.7|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Свойство_ > formula|Получает или задает формулу именованного элемента.  Формула всегда начинается со знака "=".|1.7|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Связь_ > arrayValues|Возвращает объект, содержащий значения и типы именованного элемента. Только для чтения.|1.7|
|[namedItemArrayValues](/javascript/api/excel/excel.nameditemarrayvalues)|_Свойство_ > types|Представляет типы для каждого элемента в массиве именованных элементов. Только для чтения. Возможные значения: Unknown, Empty, String, Integer, Double, Boolean, Error.|1.7|
|[namedItemArrayValues](/javascript/api/excel/excel.nameditemarrayvalues)|_Свойство_ > values|Представляет значения каждого элемента в массиве именованных элементов. Только для чтения.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > isEntireColumn|Указывает на то, является ли текущий диапазон целым столбцом. Только для чтения.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > isEntireRow|Указывает на то, является ли текущий диапазон целой строкой. Только для чтения.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > numberFormatLocal|Представляет код числового формата Excel для указанного диапазона в виде строки на языке пользователя.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > style|Представляет стиль текущего диапазона. Возвращает значение NULL или строку.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getAbsoluteResizedRange(numRows: number, numColumns: number)|Получает объект Range с той же верхней левой ячейкой, что и текущий объект Range, но с заданным количеством строк и столбцов.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getImage()|Отображает диапазон как образ с кодировкой base64.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getSurroundingRegion()|Возвращает объект Range, который представляет окружающий регион для верхней левой ячейки в этом диапазоне. Окружающий регион представляет собой диапазон, ограниченный любой комбинацией пустых строк и пустых столбцов, относящихся к этому диапазону.|1.7|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > showCard()|Отображает карточку для активной ячейки, если она имеет содержимое богатого значения.|1.7|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Свойство_ > textOrientation|Возвращает или задает ориентацию текста всех ячеек в диапазоне.|1.7|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Свойство_ > useStandardHeight|Определяет, равна ли высота строки объекта Range стандартной высоте листа.|1.7|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Свойство_ > useStandardWidth|Определяет, равна ли ширина столбца объекта Range стандартной ширине листа.|1.7|
|[rangeHyperlink](/javascript/api/excel/excel.rangehyperlink)|_Свойство_ > address|Представляет конечный URL-адрес гиперссылки.|1.7|
|[rangeHyperlink](/javascript/api/excel/excel.rangehyperlink)|_Свойство_ > document.|Представляет документ. целевой объект для гиперссылки.|1.7|
|[rangeHyperlink](/javascript/api/excel/excel.rangehyperlink)|_Свойство_ > screenTip|Представляет строку, отображаемую при наведении указателя на гиперссылку.|1.7|
|[rangeHyperlink](/javascript/api/excel/excel.rangehyperlink)|_Свойство_ > textToDisplay|Представляет строку, отображаемую в самой верхней и левой ячейке диапазона.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > addIndent|Указывает, будет ли выполнен автоматический отступ для текста, если выравнивание текста в ячейке установлено на равномерное распределение.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > autoIndent|Указывает, будет ли выполнен автоматический отступ для текста, если выравнивание текста в ячейке установлено на равномерное распределение.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > builtIn|Указывает, является ли стиль встроенным. Только для чтения.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > formulaHidden|Указывает на то, будет ли формула скрыта, если лист защищен.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > horizontalAlignment|Представляет горизонтальное выравнивание для стиля. Возможные значения: General, Left, Center, Right, Fill, Justify, CenterAcrossSelection, Distributed.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includeAlignment|Указывает, включает ли в себя стиль такие свойства: AutoIndent, HorizontalAlignment, VerticalAlignment, WrapText, IndentLevel, и TextOrientation.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includeBorder|Указывает на то, включает ли в себя стиль такие свойства границ: Color, ColorIndex, LineStyle и Weight.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includeFont|Указывает, включает ли стиль такие свойства шрифта, как Background, Bold, Color, ColorIndex, FontStyle, Italic, Name, Size, Strikethrough, Subscript, Superscript, и Underline.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includeNumber|Указывает, включает ли в себя стиль свойство NumberFormat.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includePatterns|Указывает, включает ли в себя стиль такие внутренние свойства, как Color, ColorIndex, InvertIfNegative, Pattern, PatternColor, и PatternColorIndex.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > includeProtection|Указывает, включает ли в себя стиль свойства защиты FormulaHidden и Locked.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > indentLevel|Целое число от 0 до 250 знаков, которое указывает, уровень отступа для стиля.|1.7|
|[style](/javascript/api/excel/excel.style)|locked monad startTag">_Propertylocked monad endTag">_ > locked|Указывает на то, заблокирован ли объект, когда лист защищен.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > name|Имя стиля. Только для чтения.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > numberFormat|Код формата числового формата для стиля.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > numberFormatLocal|Локализованный код формата числового формата для стиля.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > orientation|Ориентация текста для стиля.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > readingOrder|Направление чтения для стиля. Возможные значения: Context, LeftToRight, RightToLeft.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > shrinkToFit| Указывает, сжимается ли автоматически текст для соответствия имеющейся ширине столбца.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > textOrientation|Ориентация текста для стиля.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > verticalAlignment|Представляет вертикальное выравнивание для стиля. Возможные значения: Top, Center, Bottom, Justify, Distributed.|1.7|
|[style](/javascript/api/excel/excel.style)|_Свойство_ > wrapText|Указывает на то, переносит ли Microsoft Excel текст по словам в объекте.|1.7|
|[style](/javascript/api/excel/excel.style)|_Связь_ > borders|Коллекция границ из четырех объектов границы, представляющих стиль четырех границ. Только для чтения.|1.7|
|[style](/javascript/api/excel/excel.style)|_Связь_ > fill|Заливка стиля. Только для чтения.|1.7|
|[style](/javascript/api/excel/excel.style)|_Связь_ > font|Объект Font, представляющий шрифт стиля. Только для чтения.|1.7|
|[style](/javascript/api/excel/excel.style)|_Метод_ > delete()|Удаляет этот стиль.|1.7|
|[styleCollection](/javascript/api/excel/excel.stylecollection)|_Свойство_ > items|Коллекция объектов стиля. Только для чтения.|1.7|
|[styleCollection](/javascript/api/excel/excel.stylecollection)|_Метод_ > add(name: string)]|Добавляет в коллекцию новый стиль.|1.7|
|[styleCollection](/javascript/api/excel/excel.stylecollection)|_Метод_ > getItem(name: string)|Возвращает стиль по имени.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > address|Возвращает адрес, который представляет измененную область таблицы на конкретном листе.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > changeType|Возвращает тип изменения, отображающий, как инициируется событие Changed. Возможные значения: Others, RangeEdited, RowInserted, RowDeleted, ColumnInserted, ColumnDeleted, CellInserted, CellDeleted.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > source|Получает источник события. Возможные значения: Local, Remote.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > tableId|Получает идентификатор таблицы, в которой изменены данные.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[tableChangedEventArgs](/javascript/api/excel/excel.tablechangedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором изменены данные.|1.7|
|[tableSelectionChangedEventArgs](/javascript/api/excel/excel.tableselectionchangedeventargs)|_Свойство_ > address|Получает адрес диапазона, который представляет выбранную область таблицы на конкретном листе.|1.7|
|[tableSelectionChangedEventArgs](/javascript/api/excel/excel.tableselectionchangedeventargs)|_Свойство_ > isInsideTable|Указывает, будет ли выделение внутри таблицы, адреса бесполезным, если IsInsideTable имеет значение false.|1.7|
|[tableSelectionChangedEventArgs](/javascript/api/excel/excel.tableselectionchangedeventargs)|_Свойство_ > tableId|Получает идентификатор таблицы, в которой изменено выделение.|1.7|
|[tableSelectionChangedEventArgs](/javascript/api/excel/excel.tableselectionchangedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[tableSelectionChangedEventArgs](/javascript/api/excel/excel.tableselectionchangedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором изменено выделение.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Свойство_ > name|Получает имя книги. Только для чтения.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > dataConnections|Обновляет все подключения к данным в книге. Только для чтения.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > properties|Получает свойства книги. Только для чтения.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > protection|Возвращает объект защиты книги для книги. Только для чтения.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > styles|Представляет коллекцию стилей, связанную с книгой. Только для чтения.|1.7|
|[workbook](/javascript/api/excel/excel.workbook)|_Метод_ > getActiveCell()|Получает текущую активную ячейку из рабочей книги.|1.7|
|[workbookProtection](/javascript/api/excel/excel.workbookprotection)|_Свойство_ > protected|Указывает, защищена ли книга. Только для чтения. Только для чтения.|1.7|
|[workbookProtection](/javascript/api/excel/excel.workbookprotection)|_Метод_ > protect(password: string)|Защищает книгу. Не работает, если книга защищена.|1.7|
|[workbookProtection](/javascript/api/excel/excel.workbookprotection)|_Метод_ > unprotect(password: string)|Снимает защиту с книги.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > gridlines|Получает или задает флаг линии сетки рабочего листа.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > headings|Получает или задает флаг заголовков рабочего листа.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > showHeadings|Получает или задает флаг заголовков рабочего листа.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > standardHeight|Возвращает стандартную (по умолчанию) высоту всех строк на листе, в пунктах. Только для чтения.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > standardWidth|Возвращает или задает стандартную (по умолчанию) ширину всех столбцов на листе.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Свойство_ > tabColor|Получает или задает цвет вкладки листа.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Связь_ > freezePanes|Возвращает объект, который можно использовать для управления зафиксированными панелями на листе Только для чтения.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > copy(positionType: WorksheetPositionType, relativeTo: Worksheet)|Копирование листа и размещение его в заданной позиции. Возвращает скопированный лист.|1.7|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getRangeByIndexes(startRow: number, startColumn: number, rowCount: number, columnCount: number)|Возвращает объект диапазона, начинающийся с определенного индекса строки и индекса столбца, и охватывает определенное количество строк и столбцов.|1.7|
|[worksheetActivatedEventArgs](/javascript/api/excel/excel.worksheetactivatedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetActivatedEventArgs](/javascript/api/excel/excel.worksheetactivatedeventargs)|_Свойство_ > worksheetId|Возвращает идентификатор рабочего листа, который активирован.|1.7|
|[worksheetAddedEventArgs](/javascript/api/excel/excel.worksheetaddedeventargs)|_Свойство_ > source|Получает источник события. Возможные значения: Local, Remote.|1.7|
|[worksheetAddedEventArgs](/javascript/api/excel/excel.worksheetaddedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetAddedEventArgs](/javascript/api/excel/excel.worksheetaddedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, который добавляется в книгу.|1.7|
|[worksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|_Свойство_ > address|Получает адрес диапазона, который представляет измененную область конкретного листа.|1.7|
|[worksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|_Свойство_ > changeType|Возвращает тип изменения, отображающий, как инициируется событие Changed. Возможные значения: Others, RangeEdited, RowInserted, RowDeleted, ColumnInserted, ColumnDeleted, CellInserted, CellDeleted.|1.7|
|[worksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|_Свойство_ > source|Получает источник события. Возможные значения: Local, Remote.|1.7|
|[worksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором изменены данные.|1.7|
|[worksheetDeactivatedEventArgs](/javascript/api/excel/excel.worksheetdeactivatedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetDeactivatedEventArgs](/javascript/api/excel/excel.worksheetdeactivatedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, который деактивирован.|1.7|
|[worksheetDeletedEventArgs](/javascript/api/excel/excel.worksheetdeletedeventargs)|_Свойство_ > source|Получает источник события. Возможные значения: Local, Remote.|1.7|
|[worksheetDeletedEventArgs](/javascript/api/excel/excel.worksheetdeletedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetDeletedEventArgs](/javascript/api/excel/excel.worksheetdeletedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, который удален из книги.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > freezeAt(frozenRange: Range or string)|Задает закрепленные ячейки в отображении активного листа.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > freezeColumns(count: number)|Закрепляет первый столбец(ы) рабочего листа на месте.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > freezeRows(count: number)|Закрепление верхней строки (строк) листа на месте.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > getLocation()|Получает диапазон, который описывает закрепленные ячейки в представлении активного рабочего листа.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > getLocationOrNullObject()|Получает диапазон, который описывает закрепленные ячейки в представлении активного рабочего листа.|1.7|
|[worksheetFreezePanes](/javascript/api/excel/excel.worksheetfreezepanes)|_Метод_ > unfreeze()|Удаляет все закрепленные панели в рабочем листе.|1.7|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowEditObjects|Представляет параметр защиты листа, разрешающий редактирование объектов.|1.7|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowEditScenarios|Представляет параметр защиты листа, разрешающий редактирование сценариев.|1.7|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Связь_ > selectionMode|Представляет параметр защиты рабочего листа для режима выделения.|1.7|
|[worksheetSelectionChangedEventArgs](/javascript/api/excel/excel.worksheetselectionchangedeventargs)|_Свойство_ > address|Получает адрес диапазона, который представляет выбранную область конкретного листа.|1.7|
|[worksheetSelectionChangedEventArgs](/javascript/api/excel/excel.worksheetselectionchangedeventargs)|_Свойство_ > type|Получает тип события. Возможные значения: WorksheetDataChanged, WorksheetSelectionChanged, WorksheetAdded, WorksheetActivated, WorksheetDeactivated, TableDataChanged, TableSelectionChanged, WorksheetDeleted.|1.7|
|[worksheetSelectionChangedEventArgs](/javascript/api/excel/excel.worksheetselectionchangedeventargs)|_Свойство_ > worksheetId|Получает идентификатор листа, в котором изменено выделение.|1.7|


## <a name="whats-new-in-excel-javascript-api-16"></a>Новые возможности API JavaScript для Excel 1.6 

### <a name="conditional-formatting"></a>Условное форматирование

Вводит условное форматирование диапазона. Разрешает условное форматирование следующих типов:

* Цветовая шкала
* Гистограмма
* Набор значков
* Настраиваемый

Кроме того:

* Возвращает диапазон, к которому применено условное форматирование. 
* Удаление условного форматирования. 
* Возможность установки приоритетов и оператор stopifTrue. 
* Получение полной коллекции условного форматирования для определенного диапазона. 
* Полное удаление условного форматирование в указанном диапазоне. 

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[приложение](/javascript/api/excel/excel.application)|_Метод_ > suspendApiCalculationUntilNextSync()|Приостанавливает вычисление до вызова следующего "context.sync()". После этого за пересчет книги и распространение всех зависимостей несет ответственность разработчик.|1.6|
|[cellValueConditionalFormat](/javascript/api/excel/excel.cellvalueconditionalformat)|_Связь_ > format|Возвращает объект формата, который содержит шрифт, заливку, границы и другие свойства условного форматирования. Только для чтения.|1.6|
|[cellValueConditionalFormat](/javascript/api/excel/excel.cellvalueconditionalformat)|_Связь_ > rule|Представляет объект Rule в этом условном форматировании.|1.6|
|[colorScaleConditionalFormat](/javascript/api/excel/excel.colorscaleconditionalformat)|_Свойство_ > threeColorScale|Если вы укажете значение true, цветовая шкала будет иметь три точки (минимальная, средняя, максимальная), в противном случае она будет иметь две точки (минимальная, максимальная). Только для чтения.|1.6|
|[colorScaleConditionalFormat](/javascript/api/excel/excel.colorscaleconditionalformat)|_Связь_ > criteria|Условия цветовой шкалы. Средняя точка является необязательной при использовании цветовой шкалы с двумя точками.|1.6|
|[conditionalCellValueRule](/javascript/api/excel/excel.conditionalcellvaluerule)|_Свойство_ > formula1|Формула, с помощью которой при необходимости оценивается правило условного форматирования.|1.6|
|[conditionalCellValueRule](/javascript/api/excel/excel.conditionalcellvaluerule)|_Свойство_ > formula2|Формула, с помощью которой при необходимости оценивается правило условного форматирования.|1.6|
|[conditionalCellValueRule](/javascript/api/excel/excel.conditionalcellvaluerule)|_Свойство_ > operator|Оператор условного форматирования текста. Возможные значения: Invalid, Between, NotBetween, EqualTo, NotEqualTo, GreaterThan, LessThan, GreaterThanOrEqual, LessThanOrEqual.|1.6|
|[conditionalColorScaleCriteria](/javascript/api/excel/excel.conditionalcolorscalecriteria)|_Связь_ > maximum|Условие цветовой шкалы "максимальная точка".|1.6|
|[conditionalColorScaleCriteria](/javascript/api/excel/excel.conditionalcolorscalecriteria)|_Связь_ > midpoint|Условие цветовой шкалы "средняя точка", если используется трехцветная цветовая шкала.|1.6|
|[conditionalColorScaleCriteria](/javascript/api/excel/excel.conditionalcolorscalecriteria)|_Связь_ > minimum|Условие цветовой шкалы "минимальная точка".|1.6|
|[conditionalColorScaleCriterion](/javascript/api/excel/excel.conditionalcolorscalecriterion)|_Свойство_ > color|HTML-код цвета цветовой шкалы. Например, #FF0000 обозначает красный.|1.6|
|[conditionalColorScaleCriterion](/javascript/api/excel/excel.conditionalcolorscalecriterion)|_Свойство_ > formula|Число, формула или значение NULL (если указан тип LowestValue).|1.6|
|[conditionalColorScaleCriterion](/javascript/api/excel/excel.conditionalcolorscalecriterion)|_Свойство_ > type|На чем должна основываться условная формула значка. Возможные значения: Invalid, LowestValue, HighestValue, Number, Percent, Formula, Percentile.|1.6|
|[conditionalDataBarNegativeFormat](/javascript/api/excel/excel.conditionaldatabarnegativeformat)|_Свойство_ > borderColor|HTML-код, представляющий цвет линии границы в виде #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalDataBarNegativeFormat](/javascript/api/excel/excel.conditionaldatabarnegativeformat)|_Свойство_ > fillColor|HTML-код, представляющий цвет заливки в формате #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalDataBarNegativeFormat](/javascript/api/excel/excel.conditionaldatabarnegativeformat)|_Свойство_ > matchPositiveBorderColor|Указывает, имеет ли отрицательная гистограмма тот же цвет границы, что и положительная.|1.6|
|[conditionalDataBarNegativeFormat](/javascript/api/excel/excel.conditionaldatabarnegativeformat)|_Свойство_ > matchPositiveFillColor|Указывает, имеет ли отрицательная гистограмма тот же цвет заливки, что и положительная.|1.6|
|[conditionalDataBarPositiveFormat](/javascript/api/excel/excel.conditionaldatabarpositiveformat)|_Свойство_ > borderColor|HTML-код, представляющий цвет линии границы в виде #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalDataBarPositiveFormat](/javascript/api/excel/excel.conditionaldatabarpositiveformat)|_Свойство_ > fillColor|HTML-код, представляющий цвет заливки в формате #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalDataBarPositiveFormat](/javascript/api/excel/excel.conditionaldatabarpositiveformat)|_Свойство_ > gradientFill|Указывает, имеет ли гистограмма градиент.|1.6|
|[conditionalDataBarRule](/javascript/api/excel/excel.conditionaldatabarrule)|_Свойство_ > formula|Формула, с помощью которой при необходимости оценивается правило гистограммы.|1.6|
|[conditionalDataBarRule](/javascript/api/excel/excel.conditionaldatabarrule)|_Свойство_ > type|Тип правила для гистограммы. Возможные значения: LowestValue, HighestValue, Number, Percent, Formula, Percentile, Automatic.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Свойство_ > id|Приоритет условного форматирования в пределах текущей ConditionalFormatCollection. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Свойство_ > priority|Приоритет (или индекс) в коллекции условного форматирования, в котором оно в настоящее время существует. Изменение этого параметра также|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Свойство_ > stopIfTrue|Если выполняются условия этого условного форматирования, форматы с более низким приоритетом не будут применяться в этой ячейке.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Свойство_ > type|Тип условного форматирования. Одновременно можно задать только один. Только для чтения. Только для чтения. Возможные значения: Custom, DataBar, ColorScale, IconSet.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > cellValue|Возвращает свойства условного форматирования по значению ячейки, если используется условное форматирование CellValue. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > cellValueOrNullObject|Возвращает свойства условного форматирования по значению ячейки, если используется условное форматирование CellValue. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > colorScale|Возвращает свойства условного форматирования ColorScale, если используется условное форматирование ColorScale. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > colorScaleOrNullObject|Возвращает свойства условного форматирования ColorScale, если используется условное форматирование ColorScale. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > custom|Возвращает свойства специального условного форматирования, если используется специальное условное форматирование. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > customOrNullObject|Возвращает свойства специального условного форматирования, если используется специальное условное форматирование. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > dataBar|Возвращает свойства гистограммы, если текущее условное форматирование — гистограмма. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > dataBarOrNullObject|Возвращает свойства гистограммы, если текущее условное форматирование — гистограмма. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > iconSet|Возвращает свойства условного форматирования IconSet, если используется условное форматирование IconSet. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > iconSetOrNullObject|Возвращает свойства условного форматирования IconSet, если используется условное форматирование IconSet. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > preset|Возвращает условное форматирование по готовым условиям, например свойства above averagebelow averageunique valuescontains blanknonblankerrornoerror. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > presetOrNullObject|Возвращает условное форматирование по готовым условиям, например свойства above averagebelow averageunique valuescontains blanknonblankerrornoerror. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > textComparison|Возвращает свойства условного форматирования по определенному тексту, если используется текстовое условное форматирование. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > textComparisonOrNullObject|Возвращает свойства условного форматирования по определенному тексту, если используется текстовое условное форматирование. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > topBottom|Возвращает свойства условного форматирования TopBottom, если используется условное форматирование TopBottom. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Связь_ > topBottomOrNullObject|Возвращает свойства условного форматирования TopBottom, если используется условное форматирование TopBottom. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Метод_ > delete()|Удаляет это условное форматирование.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Метод_ > getRange()|Возвращает диапазон, к которому применяется условное форматирование, или объект NULL, если диапазон является непрерывным. Только для чтения.|1.6|
|[conditionalFormat](/javascript/api/excel/excel.conditionalformat)|_Метод_ > getRangeOrNullObject()|Возвращает диапазон, к которому применяется условное форматирование, или объект NULL, если диапазон является непрерывным. Только для чтения.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Свойство_ > items|Коллекция объектов conditionalFormat. Только для чтения.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Метод_ > add(type: string)|Добавляет новое условное форматирование в коллекцию с наивысшим приоритетом.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Метод_ > clearAll()|Полное удаление условного форматирование в указанном диапазоне.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Метод_ > getCount()|Возвращает количество условных форматов в книге. Только для чтения.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Метод_ > getItem(id: string)|Возвращает условное форматирование для указанного идентификатора.|1.6|
|[conditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|_Метод_ > getItemAt(index: number)|Возвращает условное форматирование по индексу.|1.6|
|[conditionalFormatRule](/javascript/api/excel/excel.conditionalformatrule)|_Свойство_ > formula|Формула, с помощью которой при необходимости оценивается правило условного форматирования.|1.6|
|[conditionalFormatRule](/javascript/api/excel/excel.conditionalformatrule)|_Свойство_ > formulaLocal|Формула, с помощью которой при необходимости оценивается правило условного форматирования на языке пользователя.|1.6|
|[conditionalFormatRule](/javascript/api/excel/excel.conditionalformatrule)|_Свойство_ > formulaR1C1|Формула, с помощью которой при необходимости оценивается правило условного форматирования в формате R1C1.|1.6|
|[conditionalIconCriterion](/javascript/api/excel/excel.conditionaliconcriterion)|_Свойство_ > formula|Число или формула в зависимости от типа.|1.6|
|[conditionalIconCriterion](/javascript/api/excel/excel.conditionaliconcriterion)|_Свойство_ > operator|Значение GreaterThan или GreaterThanOrEqual для каждого типа правила условного форматирования Icon. Возможные значения: Invalid, GreaterThan, GreaterThanOrEqual.|1.6|
|[conditionalIconCriterion](/javascript/api/excel/excel.conditionaliconcriterion)|_Связь_ > customIcon|Специальный значок для текущего условия, если он отличается от набора значков по умолчанию, в противном случае возвращается значение NULL.|1.6|
|[conditionalIconCriterion](/javascript/api/excel/excel.conditionaliconcriterion)|_Связь_ > type|На чем должна основываться условная формула значка.|1.6|
|[conditionalPresetCriteriaRule](/javascript/api/excel/excel.conditionalpresetcriteriarule)|_Свойство_ > criterion|Условие условного форматирования. Возможные значения: Invalid, Blanks, NonBlanks, Errors, NonErrors, Yesterday, Today, Tomorrow, LastSevenDays, LastWeek, ThisWeek, NextWeek, LastMonth, ThisMonth, NextMonth, AboveAverage, BelowAverage, EqualOrAboveAverage, EqualOrBelowAverage, OneStdDevAboveAverage, OneStdDevBelowAverage, TwoStdDevAboveAverage, TwoStdDevBelowAverage, ThreeStdDevAboveAverage, ThreeStdDevBelowAverage, UniqueValues, DuplicateValues.|1.6|
|[conditionalRangeBorder](/javascript/api/excel/excel.conditionalrangeborder)|_Свойство_ > color|HTML-код, представляющий цвет линии границы в виде #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalRangeBorder](/javascript/api/excel/excel.conditionalrangeborder)|_Свойство_ > id|Представляет идентификатор границы. Только для чтения. Возможные значения: EdgeTop, EdgeBottom, EdgeLeft, EdgeRight.|1.6|
|[conditionalRangeBorder](/javascript/api/excel/excel.conditionalrangeborder)|_Свойство_ > sideIndex|Постоянное значение, указывающее определенную сторону границы. Только для чтения. Возможные значения: EdgeTop, EdgeBottom, EdgeLeft, EdgeRight.|1.6|
|[conditionalRangeBorder](/javascript/api/excel/excel.conditionalrangeborder)|_Свойство_ > style|Одна из констант стиля линии, определяющая стиль линии границы. Возможные значения: None, Continuous, Dash, DashDot, DashDotDot, Dot, Double, SlantDashDot.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Свойство_ > count|Количество объектов границы в коллекции. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Свойство_ > items|Коллекция объектов conditionalRangeBorder. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Связь_ > bottom|Возвращает верхнюю границу. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Связь_ > left|Возвращает верхнюю границу. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Связь_ > right|Возвращает верхнюю границу. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Связь_ > top|Возвращает верхнюю границу. Только для чтения.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Метод_ > getItem(index: string)|Возвращает объект границы, используя его имя.|1.6|
|[conditionalRangeBorderCollection](/javascript/api/excel/excel.conditionalrangebordercollection)|_Метод_ > getItemAt(index: number)|Возвращает объект границы, используя его индекс.|1.6|
|[conditionalRangeFill](/javascript/api/excel/excel.conditionalrangefill)|_Свойство_ > color|HTML-код, представляющий цвет заливки в формате #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[conditionalRangeFill](/javascript/api/excel/excel.conditionalrangefill)|_Метод_ > clear()|Удаляет заливку.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Свойство_ > bold|Указывает, является ли шрифт полужирным.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Свойство_ > color|HTML-код цвета текста. Например, значение #FF0000 обозначает красный цвет.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Свойство_ > italic|Указывает, применяется ли курсив.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Свойство_ > strikethrough|Указывает, зачеркнут ли шрифт.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Свойство_ > underline|Тип подчеркивания, применяемый для шрифта. Возможные значения: None, Single, Double.|1.6|
|[conditionalRangeFont](/javascript/api/excel/excel.conditionalrangefont)|_Метод_ > clear()|Удаляет форматирование шрифтов.|1.6|
|[conditionalRangeFormat](/javascript/api/excel/excel.conditionalrangeformat)|_Свойство_ > numberFormat|Представляет код в числовом формате Excel для данного диапазона. Удаляется, если передается значение NULL.|1.6|
|[conditionalRangeFormat](/javascript/api/excel/excel.conditionalrangeformat)|_Связь_ > borders|Коллекция объектов границы, которые применяются ко всему диапазону условного форматирования. Только для чтения.|1.6|
|[conditionalRangeFormat](/javascript/api/excel/excel.conditionalrangeformat)|_Связь_ > fill|Возвращает объект заливки, определенный для всего диапазона условного форматирования. Только для чтения.|1.6|
|[conditionalRangeFormat](/javascript/api/excel/excel.conditionalrangeformat)|_Связь_ > font|Возвращает объект шрифта, определенный для всего диапазона условного форматирования. Только для чтения.|1.6|
|[conditionalTextComparisonRule](/javascript/api/excel/excel.conditionaltextcomparisonrule)|_Свойство_ > operator|Оператор условного форматирования текста. Возможные значения: Invalid, Contains, NotContains, BeginsWith, EndsWith.|1.6|
|[conditionalTextComparisonRule](/javascript/api/excel/excel.conditionaltextcomparisonrule)|_Свойство_ > text|Текстовое значение условного форматирования.|1.6|
|[conditionalTopBottomRule](/javascript/api/excel/excel.conditionaltopbottomrule)|_Свойство_ > rank|От 1 до 1000 для числовых рейтингов или от 1 до 100 для процентных рейтингов.|1.6|
|[conditionalTopBottomRule](/javascript/api/excel/excel.conditionaltopbottomrule)|_Свойство_ > type|Значения форматирования на основе рейтинга. Возможные значения: Invalid, TopItems, TopPercent, BottomItems, BottomPercent.|1.6|
|[customConditionalFormat](/javascript/api/excel/excel.customconditionalformat)|_Связь_ > format|Возвращает объект формата, который содержит шрифт, заливку, границы и другие свойства условного форматирования. Только для чтения.|1.6|
|[customConditionalFormat](/javascript/api/excel/excel.customconditionalformat)|_Связь_ > rule|Представляет объект Rule в этом условном форматировании. Только для чтения.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Свойство_ > axisColor|HTML-код, представляющий цвет линии оси в формате #RRGGBB (например, FFA500) или в виде ключевого слова (например, orange).|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Свойство_ > axisFormat|Указывает, как определяется ось для гистограммы Excel. Возможные значения: Automatic, None, CellMidPoint.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Свойство_ > barDirection|Представляет направление, которое должна использовать гистограмма. Возможные значения: Context, LeftToRight, RightToLeft.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Свойство_ > showDataBarOnly|Значение true скрывает значения ячеек, где применяется гистограмма.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Связь_ > lowerBoundRule|Правило для нижней границы гистограммы (и как ее вычислить, если применимо).|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Связь_ > negativeFormat|Представление всех значений слева от оси в гистограмме Excel. Только для чтения.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Связь_ > positiveFormat|Представление всех значений справа от оси в гистограмме Excel. Только для чтения.|1.6|
|[dataBarConditionalFormat](/javascript/api/excel/excel.databarconditionalformat)|_Связь_ > upperBoundRule|Правило для верхней границы гистограммы (и как ее вычислить, если применимо).|1.6|
|[iconSetConditionalFormat](/javascript/api/excel/excel.iconsetconditionalformat)|_Свойство_ > reverseIconOrder|Значение true меняет порядок значков в наборе значков на обратный. Обратите внимание, что это значение нельзя задать, если используются специальные значки.|1.6|
|[iconSetConditionalFormat](/javascript/api/excel/excel.iconsetconditionalformat)|_Свойство_ > showIconOnly|Значение true скрывает значения и показывает только значки.|1.6|
|[iconSetConditionalFormat](/javascript/api/excel/excel.iconsetconditionalformat)|_Свойство_ > style|Отображает параметр условного форматирования IconSet. Возможные значения: Invalid, ThreeArrows, ThreeArrowsGray, ThreeFlags, ThreeTrafficLights1, ThreeTrafficLights2, ThreeSigns, ThreeSymbols, ThreeSymbols2, FourArrows, FourArrowsGray, FourRedToBlack, FourRating, FourTrafficLights, FiveArrows, FiveArrowsGray, FiveRating, FiveQuarters, ThreeStars, ThreeTriangles, FiveBoxes.|1.6|
|[iconSetConditionalFormat](/javascript/api/excel/excel.iconsetconditionalformat)|_Связь_ > criteria|Массив условий и наборов значков для правил и специальных значков для условий. Обратите внимание, что для первого условия можно изменить только специальный значок. Тип, формула и оператор будут игнорироваться.|1.6|
|[presetCriteriaConditionalFormat](/javascript/api/excel/excel.presetcriteriaconditionalformat)|_Связь_ > format|Возвращает объект формата, который содержит шрифт, заливку, границы и другие свойства условного форматирования. Только для чтения.|1.6|
|[presetCriteriaConditionalFormat](/javascript/api/excel/excel.presetcriteriaconditionalformat)|_Связь_ > rule|Правило условного форматирования.|1.6|
|[диапазон](/javascript/api/excel/excel.range)|_Связь_ > conditionalFormats|Коллекция объектов ConditionalFormats, которые объединяют по пересечению диапазон. Только для чтения.|1.6|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > calculate()|Вычисляет диапазон ячеек на листе.|1.6|
|[textConditionalFormat](/javascript/api/excel/excel.textconditionalformat)|_Связь_ > format|Возвращает объект формата, который содержит шрифт, заливку, границы и другие свойства условного форматирования. Только для чтения.|1.6|
|[textConditionalFormat](/javascript/api/excel/excel.textconditionalformat)|_Связь_ > rule|Правило условного форматирования.|1.6|
|[topBottomConditionalFormat](/javascript/api/excel/excel.topbottomconditionalformat)|_Связь_ > format|Возвращает объект формата, который содержит шрифт, заливку, границы и другие свойства условного форматирования. Только для чтения.|1.6|
|[topBottomConditionalFormat](/javascript/api/excel/excel.topbottomconditionalformat)|_Связь_ > rule|Условия условного форматирования TopBottom.|1.6|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > internalTest|Только для внутреннего использования. Только для чтения.|1.6|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > calculate(markAllDirty: bool)|Вычисляет все ячейки на листе.|1.6|

##  <a name="whats-new-in-excel-javascript-api-15"></a>Новые возможности API JavaScript для Excel 1.5

### <a name="custom-xml-part"></a>Настраиваемая XML-часть

* Добавление коллекции настраиваемых XML-частей к объекту книги.
* Получение настраиваемой XML-части по идентификатору
* Получение новой ограниченной коллекции настраиваемых XML-частей, пространства имен которых совпадают с указанным пространством имен.
* Получение строки XML, связанной с частью.
* Предоставление идентификатора и пространства имен части.
* Добавление новой настраиваемой XML-части к книге.
* Установка XML-части целиком.
* Удаление настраиваемой XML-части.
* Удаление атрибута с указанным именем из элемента, указанного по XPath.
* Запрос содержимого XML по XPath.
* Вставка, обновление и удаление атрибутов.

**Пример реализации:** [здесь](https://github.com/mandren/Excel-CustomXMLPart-Demo) вы найдете пример реализации, в котором показано, как можно использовать XML-части в надстройке.

### <a name="others"></a>Другие
* `range.getSurroundingRegion()` Метод возвращает объект Range, представляющий область вокруг данного диапазона. Это диапазон, ограниченный любым сочетанием пустых строк и столбцов относительно данного диапазона.
* `getNextColumn()` и `getPreviousColumn()`, `getLast() для столбца таблицы.
* `getActiveWorksheet()` в книге.
* `getRange(address: string)` вне книги.
* `getBoundingRange(ranges: )` Возвращает наименьший объект диапазона, включающий в себя заданные диапазоны. Например, ограничивающий диапазон между диапазонами "B2:C5" и "D10:E15" — "B2:E15".
* `getCount()` в различных коллекциях, таких как именованные элементы, листы, таблицы и т. д. для получения количества элементов в коллекции. `workbook.worksheets.getCount()`
* `getFirst()` и `getLast()` для различных коллекций, таких как листы, столбцы таблицы, точки диаграммы и представления диапазонов.
* `getNext()` и `getPrevious()` дли коллекций листов и столбцов таблиц.
* `getRangeR1C1()` Возвращает объект диапазона, начинающийся с определенного индекса строки и индекса столбца, и охватывает определенное количество строк и столбцов.

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[customXmlPart](/javascript/api/excel/excel.customxmlpart)|_Свойство_ > id|Идентификатор настраиваемой XML-части. Только для чтения.|1.5|
|[customXmlPart](/javascript/api/excel/excel.customxmlpart)|_Свойство_ > namespaceUri|URI пространства имен настраиваемой XML-части. Только для чтения.|1.5|
|[customXmlPart](/javascript/api/excel/excel.customxmlpart)|_Метод_ > delete()|Удаляет настраиваемую XML-часть.|1.5|
|[customXmlPart](/javascript/api/excel/excel.customxmlpart)|_Метод_ > getXml()|Получает полное содержимое настраиваемой XML-части.|1.5|
|[customXmlPart](/javascript/api/excel/excel.customxmlpart)|_Метод_ > setXml(xml: string)|Задает полное содержимое настраиваемой XML-части.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Свойство_ > items|Коллекция объектов customXmlPart. Только для чтения.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Метод_ > add(xml: string)|Добавление новой настраиваемой XML-части к книге.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Метод_ > getByNamespace(namespaceUri: string)|Получает новую ограниченную коллекцию настраиваемых XML-частей, пространства имен которых совпадают с указанным пространством имен.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Метод_ > getCount()|Возвращает количество частей CustomXml в коллекции.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Метод_ > getItem(id: string)|Возвращает настраиваемую XML-часть по идентификатору.|1.5|
|[customXmlPartCollection](/javascript/api/excel/excel.customxmlpartcollection)|_Метод_ > getItemOrNullObject(id: string)|Возвращает настраиваемую XML-часть по идентификатору.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Свойство_ > items|Коллекция объектов customXmlPartScoped. Только для чтения.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Метод_ > getCount()|Возвращает количество частей CustomXML в этой коллекции.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Метод_ > getItem(id: string)|Возвращает настраиваемую XML-часть по идентификатору.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Метод_ > getItemOrNullObject(id: string)|Возвращает настраиваемую XML-часть по идентификатору.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Метод_ > getOnlyItem()|Если коллекция содержит ровно один элемент, этот метод возвращает его.|1.5|
|[customXmlPartScopedCollection](/javascript/api/excel/excel.customxmlpartscopedcollection)|_Метод_ > getOnlyItemOrNullObject()|Если коллекция содержит ровно один элемент, этот метод возвращает его.|1.5|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > customXmlParts|Представляет коллекцию настраиваемых XML-частей, содержащихся в этой книге. Только для чтения.|1.5|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getNext(visibleOnly: bool)|Получает следующий лист. Если следующего листа нет, возникает ошибка.|1.5|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getNextOrNullObject(visibleOnly: bool)|Получает следующий лист. Если следующего листа нет, метод возвращает объект NULL.|1.5|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getPrevious(visibleOnly: bool)|Возвращает предыдущий лист. Если предыдущего листа нет, возникает ошибка.|1.5|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getPreviousOrNullObject(visibleOnly: bool)|Возвращает предыдущий лист. Если предыдущего листа нет, этот метод возвращает объект NULL.|1.5|
|[worksheetCollection](/javascript/api/excel/excel.worksheetcollection)|_Метод_ > getFirst(visibleOnly: bool)|Возвращает первый лист в коллекции.|1.5|
|[worksheetCollection](/javascript/api/excel/excel.worksheetcollection)|_Метод_ > getLast(visibleOnly: bool)|Возвращает последний лист в коллекции.|1.5|

## <a name="whats-new-in-excel-javascript-api-14"></a>Новые возможности API JavaScript для Excel 1.4
Ниже перечислено то, что было недавно добавлено в набор обязательных элементов 1.4, относящийся к API JavaScript для Excel.

### <a name="named-item-add-and-new-properties"></a>Именованный элемент add и новые свойства

Новые свойства:

* `comment`
* `scope` элементы, которые относятся к листу или книги
* `worksheet` возвращает лист, к которому относится именованный элемент.

Новые методы:

* `add(name: string, reference: Range or string, comment: string)`Добавляет новое имя в определенную коллекцию.
* `addFormulaLocal(name: string, formula: string, comment: string)` Добавляет новое имя в определенную коллекцию, применяя языковой стандарт пользователя для формулы.

### <a name="settings-api-in-in-excel-namespace"></a>Параметры API в пространстве имен Excel

Объект [Setting](/javascript/api/excel/excel.setting) представляет пару "ключ-значение" для параметра, хранящегося в документе. Мы добавили API, связанные с параметрами, в пространство имен Excel. Они не обеспечивают новую функциональность, но позволяют оставаться в пакетном синтаксисе API на основе обещаний и уменьшить зависимость от общих задач, связанных с API для Excel.

API включают `getItem()` для получения параметра с помощью ключа, `add()` для добавления указанной пары параметров "ключ:значение" в книгу.

### <a name="others"></a>Другие

* Задайте имя столбца таблицы (в предыдущей версии разрешено только чтение).
* Добавьте столбец в конец таблицы (в предыдущей версии столбец можно добавить в любом месте, кроме последнего).
* Добавьте в таблицу сразу несколько строк (в предыдущей версии можно добавлять только 1 строку за раз).
* `range.getColumnsAfter(count: number)` и `range.getColumnsBefore(count: number)`, чтобы вернуть определенное количество столбцов справа/слева от текущего объекта Range.
* Получение элемента или пустого объекта: Эта функция позволяет получить объект с помощью ключа. Если объект не существует, для свойства isNullObject возвращаемого объекта будет задано значение true. Это позволяет разработчикам проверить, существует ли объект, не обрабатывая его с помощью исключений. Доступно для листа, именованного элемента, привязки, ряда диаграммы и т. д.

    ```javascript
    worksheet.GetItemOrNullObject()
    ```

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > getCount()|Получает количество привязок в коллекции.|1.4|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > getItemOrNullObject(id: string)|Получает объект привязки по идентификатору. Если объект привязки не существует, возвращает пустой объект.|1.4|
|[chartCollection](/javascript/api/excel/excel.chartcollection)|_Метод_ > getCount()|Возвращает количество диаграмм на листе.|1.4|
|[chartCollection](/javascript/api/excel/excel.chartcollection)|_Метод_ > getItemOrNullObject(name: string)|Возвращает диаграмму по ее имени. Если одно и то же имя принадлежит нескольким диаграммам, будет возвращена первая из них.|1.4|
|[chartPointsCollection](/javascript/api/excel/excel.chartpointscollection)|_Метод_ > getCount()|Возвращает количество точек диаграммы в ряду.|1.4|
|[chartSeriesCollection](/javascript/api/excel/excel.chartseriescollection)|_Метод_ > getCount()|Возвращает количество рядов в коллекции.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Свойство_ > comment|Представляет примечание, связанное с этим именем.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Свойство_ > scope|Указывает, относится ли имя к книге или определенному листу. Только для чтения. Возможные значения: Equal, Greater, GreaterEqual, Less, LessEqual, NotEqual.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Связь_ > worksheet|Возвращает лист, к которому относится именованный элемент. Выдает ошибку, если элемент относится к книге. Только для чтения.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Связь_ > worksheetOrNullObject|Возвращает лист, к которому относится именованный элемент. Возвращает пустой объект, если элемент относится к книге. Только для чтения.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Метод_ > delete()|Удаляет заданное имя.|1.4|
|[namedItem](/javascript/api/excel/excel.nameditem)|_Метод_ > getRangeOrNullObject()|Возвращает объект диапазона, связанный с именем. Возвращает пустой объект, если именованный элемент не является диапазоном.|1.4|
|[namedItemCollection](/javascript/api/excel/excel.nameditemcollection)|_Метод_ > add(name: string, reference: Range or string, comment: string)|Добавляет новое имя в определенную коллекцию.|1.4|
|[namedItemCollection](/javascript/api/excel/excel.nameditemcollection)|_Метод_ > addFormulaLocal(name: string, formula: string, comment: string)|Добавляет новое имя в определенную коллекцию, применяя языковой стандарт пользователя для формулы.|1.4|
|[namedItemCollection](/javascript/api/excel/excel.nameditemcollection)|_Метод_ > getCount()|Получает количество именованных элементов в коллекции.|1.4|
|[namedItemCollection](/javascript/api/excel/excel.nameditemcollection)|_Метод_ > getItemOrNullObject(name: string)|Получает объект nameditem по имени. Если объект nameditem не существует, возвращает пустой объект.|1.4|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Метод_ > getCount()|Получает количество сводных таблиц в коллекции.|1.4|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Метод_ > getItemOrNullObject(name: string)|Получает сводную таблицу по имени. Если сводная таблица не существует, возвращает пустой объект.|1.4|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getIntersectionOrNullObject(anotherRange: Range or string)|Возвращает объект range, представляющий прямоугольное пересечение заданных диапазонов. Если пересечение не найдено, возвращает пустой объект.|1.4|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getUsedRangeOrNullObject(valuesOnly: bool)|Возвращает используемый диапазон заданного объекта диапазона. Если в диапазоне нет используемых ячеек, эта функция возвращает пустой объект.|1.4|
|[rangeViewCollection](/javascript/api/excel/excel.rangeviewcollection)|_Метод_ > getCount()|Получает количество объектов RangeView в коллекции.|1.4|
|[настройка](/javascript/api/excel/excel.setting)|_Свойство_ > key|Возвращает ключ, представляющий идентификатор setting. Только для чтения.|1.4|
|[настройка](/javascript/api/excel/excel.setting)|_Свойство_ > value|Представляет значение, сохраненное для этого параметра.|1.4|
|[настройка](/javascript/api/excel/excel.setting)|_Метод_ > delete()|Удаляет параметр.|1.4|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Свойство_ > items|Коллекция объектов setting. Только для чтения.|1.4|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > add(key: string, value: (any))|Устанавливает или добавляет указанный параметр в книгу.|1.4|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > getCount()|Возвращает количество параметров в коллекции.|1.4|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > getItem(key: string)|Возвращает объект Setting по ключу.|1.4|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > getItemOrNullObject(key: string)|Возвращает объект Setting по ключу. Если параметр не существует, возвращает пустой объект.|1.4|
|[settingsChangedEventArgs](/javascript/api/excel/excel.settingschangedeventargs)|_Связь_ > settings|Получает объект Setting, представляющий привязку, которая вызвала событие SettingsChanged.|1.4|
|[tableCollection](/javascript/api/excel/excel.tablecollection)|_Метод_ > getCount()]|Получает количество таблиц в коллекции.|1.4|
|[tableCollection](/javascript/api/excel/excel.tablecollection)|_Метод_ > getItemOrNullObject(key: number or string)|Получает таблицу по имени или идентификатору. Если таблица не существует, возвращает пустой объект.|1.4|
|[tableColumnCollection](/javascript/api/excel/excel.tablecolumncollection)|_Метод_ > getCount()|Получает количество столбцов в таблице.|1.4|
|[tableColumnCollection](/javascript/api/excel/excel.tablecolumncollection)|_Метод_ > getItemOrNullObject(key: number or string)|Возвращает объект столбца по имени или идентификатору. Если столбец не существует, возвращает пустой объект.|1.4|
|[tableRowCollection](/javascript/api/excel/excel.tablerowcollection)|_Метод_ > getCount()|Получает количество строк в таблице.|1.4|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > settings|Представляет коллекцию параметров, сопоставленных с книгой. Только для чтения.|1.4|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Связь_ > names|Коллекция имен, относящихся к текущему листу. Только для чтения.|1.4|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Метод_ > getUsedRangeOrNullObject(valuesOnly: bool)|Используемый диапазон — это наименьший диапазон, включающий в себя все ячейки, которые содержат значение или форматирование. Если весь лист пустой, эта функция возвращает пустой объект.|1.4|
|[worksheetCollection](/javascript/api/excel/excel.worksheetcollection)|_Метод_ > getCount(visibleOnly: bool)|Получает количество листов в коллекции.|1.4|
|[worksheetCollection](/javascript/api/excel/excel.worksheetcollection)|_Метод_ > getItemOrNullObject(key: string)|Получает объект листа по его имени или идентификатору. Если лист не существует, возвращает пустой объект.|1.4|

## <a name="whats-new-in-excel-javascript-api-13"></a>Новые возможности API JavaScript для Excel 1.3

Ниже перечислено то, что было недавно добавлено в набор обязательных элементов 1.3, относящийся к API JavaScript для Excel.

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[привязка](/javascript/api/excel/excel.binding)|_Метод_ > delete()|Удаляет привязку.|1.3|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > add(range: Range or string, bindingType: string, id: string)|Добавляет привязку к определенному объекту Range.|1.3|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > addFromNamedItem(name: string, bindingType: string, id: string)|Добавляет новую привязку с учетом именованного элемента в книге.|1.3|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > addFromSelection(bindingType: string, id: string)|Добавляет новую привязку с учетом выделенного в настоящий момент фрагмента.|1.3|
|[bindingCollection](/javascript/api/excel/excel.bindingcollection)|_Метод_ > getItemOrNull(id: string)|Возвращает объект binding по идентификатору. Если объект binding не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[chartCollection](/javascript/api/excel/excel.chartcollection)|_Метод_ > getItemOrNull(name: string)|Возвращает диаграмму по ее имени. Если одно и то же имя принадлежит нескольким диаграммам, будет возвращена первая из них.|1.3|
|[namedItemCollection](/javascript/api/excel/excel.nameditemcollection)|_Метод_ > getItemOrNull(name: string)|Возвращает объект nameditem по имени. Если объект nameditem не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Свойство_ > name|Имя сводной таблицы.|1.3|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Связь_ > worksheet|Лист, содержащий текущую сводную таблицу. Только для чтения.|1.3|
|[pivotTable](/javascript/api/excel/excel.pivottable)|_Метод_ > refresh()|Обновляет сводную таблицу.|1.3|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Свойство_ > items|Коллекция объектов pivotTable. Только для чтения.|1.3|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Метод_ > getItem(name: string)|Возвращает сводную таблицу по имени.|1.3|
|[pivotTableCollection](/javascript/api/excel/excel.pivottablecollection)|_Метод_ > getItemOrNull(name: string)|Возвращает сводную таблицу по имени. Если сводная таблица не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getIntersectionOrNull(anotherRange: Range or string)|Возвращает объект range, представляющий прямоугольное пересечение заданных диапазонов. Если пересечение не найдено, возвращает пустой объект.|1.3|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > getVisibleView()|Представляет видимые строки текущего диапазона.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > cellAddresses|Представляет адреса ячеек RangeView. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > columnCount|Возвращает количество видимых столбцов. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > formulas|Представляет формулу в формате A1.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > formulasLocal|Представляет формулу в формате A1 на языке пользователя и в соответствии с его языковым стандартом. Например, английская формула "=SUM(A1, introduced in 1.5)" превратится в "=СУММ(A1;1,5)" на русском языке.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > formulasR1C1|Представляет формулу в формате R1C1.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > index|Возвращает значение, представляющее индекс RangeView. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > numberFormat|Представляет код в числовом формате Excel для данной ячейки.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > rowCount|Возвращает количество видимых строк. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > text|Текстовые значения указанного диапазона. Текстовое значение не зависит от ширины ячейки. Замена знака #, которая происходит в настраиваемом интерфейсе Excel, не повлияет на текстовое значение, возвращаемое API. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > valueTypes|Представляет тип данных каждой ячейки. Только для чтения. Возможные значения: Unknown, Empty, String, Integer, Double, Boolean, Error.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Свойство_ > values|Представляет необработанные значения указанного объекта rangeView. Могут возвращаться строковые и числовые данные, а также логические значения. Ячейка, которая содержит ошибку, вернет строку ошибки.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Связь_ > rows|Представляет коллекцию объектов rangeView, сопоставленных с диапазоном. Только для чтения.|1.3|
|[rangeView](/javascript/api/excel/excel.rangeview)|_Метод_ > getRange()|Возвращает родительский диапазон, сопоставленный с текущим объектом RangeView.|1.3|
|[rangeViewCollection](/javascript/api/excel/excel.rangeviewcollection)|_Свойство_ > items|Коллекция объектов rangeView. Только для чтения.|1.3|
|[rangeViewCollection](/javascript/api/excel/excel.rangeviewcollection)|_Метод_ > getItemAt(index: number)|Возвращает строку RangeView по индексу. Используется нулевой индекс.|1.3|
|[настройка](/javascript/api/excel/excel.setting)|_Свойство_ > key|Возвращает ключ, представляющий идентификатор setting. Только для чтения.|1.3|
|[настройка](/javascript/api/excel/excel.setting)|_Метод_ > delete()|Удаляет параметр.|1.3|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Свойство_ > items|Коллекция объектов setting. Только для чтения.|1.3|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > getItem(key: string)|Возвращает объект Setting по ключу.|1.3|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > getItemOrNull(key: string)|Возвращает объект Setting по ключу. Если экземпляр Setting не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[SettingCollection](/javascript/api/excel/excel.settingcollection)|_Метод_ > set(key: string, value: string)|Устанавливает или добавляет указанный параметр в книгу.|1.3|
|[settingsChangedEventArgs](/javascript/api/excel/excel.settingschangedeventargs)|_Связь_ > settingCollection|Получает объект Setting, представляющий привязку, которая вызвала событие SettingsChanged.|1.3|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > highlightFirstColumn|Указывает, содержит ли первый столбец специальное форматирование.|1.3|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > highlightLastColumn|Указывает, содержит ли последний столбец специальное форматирование.|1.3|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > showBandedColumns|Указывает, чередуется ли форматирование четных и нечетных столбцов для более удобного просмотра таблицы.|1.3|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > showBandedRows|Указывает, чередуется ли форматирование четных и нечетных строк для более удобного просмотра таблицы.|1.3|
|[table](/javascript/api/excel/excel.table)|_Свойство_ > showFilterButton|Указывает, видны ли кнопки фильтрации в верхней части заголовков столбцов. Это свойство можно использовать, только если таблица содержит строку заголовков.|1.3|
|[tableCollection](/javascript/api/excel/excel.tablecollection)|_Метод_ > getItemOrNull(key: number or string)|Получает таблицу по имени или идентификатору. Если таблица не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[tableColumnCollection](/javascript/api/excel/excel.tablecolumncollection)|_Метод_ > getItemOrNull(key: number or string)|Возвращает объект column по имени или идентификатору. Если столбец не существует, у свойства isNull возвращаемого объекта будет значение true.|1.3|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > pivotTables|Представляет коллекцию сводных таблиц, сопоставленных с книгой. Только для чтения.|1.3|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > settings|Представляет коллекцию параметров, сопоставленных с книгой. Только для чтения.|1.3|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Связь_ > pivotTables|Коллекция сводных таблиц на листе. Только для чтения.|1.3|

## <a name="whats-new-in-excel-javascript-api-12"></a>Новые возможности API JavaScript для Excel 1.2

Ниже перечислено то, что было недавно добавлено в набор обязательных элементов 1.2, относящийся к API JavaScript для Excel.

|Объект| Что нового| Описание|Набор требований|
|:----|:----|:----|:----|
|[chart](/javascript/api/excel/excel.chart)|_Свойство_ > id|Возвращает диаграмму с учетом ее положения в коллекции. Только для чтения.|1.2|
|[chart](/javascript/api/excel/excel.chart)|_Связь_ > worksheet|Лист, содержащий текущую диаграмму. Только для чтения.|1.2|
|[chart](/javascript/api/excel/excel.chart)|_Метод_ > getImage(height: number, width: number, fittingMode: string)|Отрисовывает диаграмму в виде изображения с кодировкой Base64, масштабируя ее в соответствии с указанным размером.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Связь_ > criteria|Текущий фильтр, заданный для определенного столбца. Только для чтения.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > apply(criteria: FilterCriteria)|Применяет заданные условия фильтра для определенного столбца.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyBottomItemsFilter(count: number)|Применяет к столбцу фильтр по количеству элементов снизу.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyBottomPercentFilter(percent: number)]|Применяет к столбцу фильтр по проценту элементов снизу.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyCellColorFilter(color: string)|Применяет к столбцу фильтр по цвету ячеек.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyCustomFilter(criteria1: string, criteria2: string, oper: string)|Применяет фильтр "Значок" к столбцу для строк с заданными условиями.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyDynamicFilter(criteria: string)|Применяет к столбцу "Динамический" фильтр.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyFontColorFilter(color: string)|Применяет к столбцу фильтр "Цвет шрифта" по цвету шрифта.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyIconFilter(icon: Icon)|Применяет фильтр "Значок" к столбцу для данного значка.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyTopItemsFilter(count: number)|Применяет к столбцу фильтр по количеству элементов сверху.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyTopPercentFilter(percent: number)|Применяет к столбцу фильтр по проценту элементов сверху.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > applyValuesFilter(values: ())|Применяет к столбцу фильтр по значениям.|1.2|
|[filter](/javascript/api/excel/excel.filter)|_Метод_ > clear()|Сбрасывает фильтр для определенного столбца.|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > color|Строка цвета HTML, которая используется для фильтрации ячеек. Используется с фильтрацией типа "cellColor" и "fontColor".|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > criterion1|Первый критерий фильтрации данных. Используется в качестве оператора при фильтрации типа "custom".|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > criterion2|Второй критерий фильтрации данных. Используется в качестве оператора только при фильтрации типа "custom".|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > dynamicCriteria|Динамические критерии из набора Excel.DynamicFilterCriteria, которые необходимо применить к этому столбцу. Используется с фильтрацией типа "dynamic". Возможные значения: Unknown, AboveAverage, AllDatesInPeriodApril, AllDatesInPeriodAugust, AllDatesInPeriodDecember, AllDatesInPeriodFebruray, AllDatesInPeriodJanuary, AllDatesInPeriodJuly, AllDatesInPeriodJune, AllDatesInPeriodMarch, AllDatesInPeriodMay, AllDatesInPeriodNovember, AllDatesInPeriodOctober, AllDatesInPeriodQuarter1, AllDatesInPeriodQuarter2, AllDatesInPeriodQuarter3, AllDatesInPeriodQuarter4, AllDatesInPeriodSeptember, BelowAverage, LastMonth, LastQuarter, LastWeek, LastYear, NextMonth, NextQuarter, NextWeek, NextYear, ThisMonth, ThisQuarter, ThisWeek, ThisYear, Today, Tomorrow, YearToDate, Yesterday.|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > filterOn|Свойство, с помощью которого фильтр определяет, следует ли показывать значения. Возможные значения: BottomItems, BottomPercent, CellColor, Dynamic, FontColor, Values, TopItems, TopPercent, Icon, Custom.|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > operator|Оператор, который используется для объединения условий 1 и 2 при "настраиваемой" фильтрации. Возможные значения: And, Or.|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Свойство_ > values|Набор значений, который используется при фильтрации по значениям.|1.2|
|[filterCriteria](/javascript/api/excel/excel.filtercriteria)|_Связь_ > icon|Значок, используемый для фильтрации ячеек. Используется с фильтрацией типа "icon".|1.2|
|[filterDatetime](/javascript/api/excel/excel.filterdatetime)|_Свойство_ > date|Дата в формате ISO8601, используемая для фильтрации данных.|1.2|
|[filterDatetime](/javascript/api/excel/excel.filterdatetime)|_Свойство_ > specificity|Точность, с которой производится фильтрация данных на основе даты. Например, если указана дата 2005-04-02, а для свойства specificity задано значение month, после фильтрации останутся все строки, датированные апрелем 2009 г. Возможные значения: Year, Monday, Day, Hour, Minute, Second.|1.2|
|[formatProtection](/javascript/api/excel/excel.formatprotection)|_Свойство_ > formulaHidden|Указывает, скрывает ли Excel формулу для ячеек в диапазоне. Значение NULL указывает, что для всего диапазона не задан единый параметр скрытия формулы.|1.2|
|[formatProtection](/javascript/api/excel/excel.formatprotection)|locked monad startTag">_Propertylocked monad endTag">_ > locked|Указывает, блокирует ли Excel ячейки в объекте. Значение NULL указывает, что для всего диапазона не задан единый параметр блокировки.|1.2|
|[icon](/javascript/api/excel/excel.icon)|_Свойство_ > index|Представляет собой индекс значка данного набора.|1.2|
|[icon](/javascript/api/excel/excel.icon)|_Свойство_ > set|Представляет собой набор, в который входит значок. Возможные значения: Invalid, ThreeArrows, ThreeArrowsGray, ThreeFlags, ThreeTrafficLights1, ThreeTrafficLights2, ThreeSigns, ThreeSymbols, ThreeSymbols2, FourArrows, FourArrowsGray, FourRedToBlack, FourRating, FourTrafficLights, FiveArrows, FiveArrowsGray, FiveRating, FiveQuarters, ThreeStars, ThreeTriangles, FiveBoxes.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > columnHidden|Указывает, скрыты ли все столбцы текущего диапазона.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > formulasR1C1|Представляет формулу в формате R1C1.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > hidden|Указывает, скрыты ли все ячейки текущего диапазона. Только для чтения.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Свойство_ > rowHidden|Указывает, скрыты ли все строки текущего диапазона.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Связь_ > sort|Представляет порядок сортировки текущего диапазона. Только для чтения.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > merge(across: bool)|Объединяет ячейки диапазона в одну область на листе.|1.2|
|[диапазон](/javascript/api/excel/excel.range)|_Метод_ > unmerge()|Разъединяет ячейки диапазона на отдельные ячейки.|1.2|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Свойство_ > columnWidth|Возвращает или задает ширину всех столбцов в пределах диапазона. Если столбцы разной ширины, будет возвращено значение NULL.|1.2|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Свойство_ > rowHeight|Возвращает или задает высоту всех строк в диапазоне. Если строки разной высоты, будет возвращено значение NULL.|1.2|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Связь_ > protection|Возвращает объект защиты формата для диапазона. Только для чтения.|1.2|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Метод_ > autofitColumns()|Изменяет ширину столбцов текущего диапазона на оптимальную с учетом текущих данных в столбцах.|1.2|
|[rangeFormat](/javascript/api/excel/excel.rangeformat)|_Метод_ > autofitRows()|Изменяет высоту строк текущего диапазона на оптимальную с учетом текущих данных в столбцах.|1.2|
|[rangeReference](/javascript/api/excel/excel.rangereference)|_Свойство_ > address|Представляет видимые строки текущего диапазона.|1.2|
|[rangeSort](/javascript/api/excel/excel.rangesort)|_Метод_ > apply(fields: SortField, matchCase: bool, hasHeaders: bool, orientation: string, method: string)|Выполняет сортировку.|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Свойство_ > ascending|Указывает, выполняется ли сортировка по возрастанию.|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Свойство_ > color|Представляет цвет, определенный условием, при сортировке по цвету шрифта или ячеек.|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Свойство_ > dataOption|Представляет дополнительные параметры сортировки для этого поля. Возможные значения: Normal, TextAsNumber.|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Свойство_ > key|Представляет столбец (или строку в зависимости от ориентации сортировки), для которого задано условие. Представляется в виде расстояния от первого столбца (или строки).|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Свойство_ > sortOn|Представляет тип сортировки этого условия. Возможные значения: Value, CellColor, FontColor, Icon.|1.2|
|[sortField](/javascript/api/excel/excel.sortfield)|_Связь_ > icon|Представляет значок, определенный условием, при сортировке по значку ячейки.|1.2|
|[table](/javascript/api/excel/excel.table)|_Связь_ > sort|Представляет сортировку для таблицы. Только для чтения.|1.2|
|[table](/javascript/api/excel/excel.table)|_Связь_ > worksheet|Лист, содержащий текущую таблицу. Только для чтения.|1.2|
|[table](/javascript/api/excel/excel.table)|_Метод_ > clearFilters()|Удаляет все фильтры, примененные к таблице.|1.2|
|[table](/javascript/api/excel/excel.table)|_Метод_ > convertToRange()|Преобразовывает таблицу в обычный диапазон ячеек. Все данные сохраняются.|1.2|
|[table](/javascript/api/excel/excel.table)|_Метод_ > reapplyFilters()|Повторно применяет все текущие фильтры к таблице.|1.2|
|[tableColumn](/javascript/api/excel/excel.tablecolumn)|_Связь_ > filter|Возвращает фильтр, применяемый к столбцу. Только для чтения.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Свойство_ > matchCase|Указывает, учитывался ли регистр при последней сортировке таблице. Только для чтения.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Свойство_ > method|Указывает метод сортировки китайских символов, который использовался при последней сортировке таблицы. Только для чтения. Возможные значения: PinYin, StrokeCount.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Связь_ > fields|Указывает текущие условия, которые использовались при последней сортировке таблицы. Только для чтения.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Метод_ > apply(fields: SortField, matchCase: bool, method: string)|Выполняет сортировку.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Метод_ > clear()|Удаляет текущие параметры сортировки таблицы. При этом сбрасывается состояние кнопок в заголовках, но порядок сортировки таблицы остается неизменным.|1.2|
|[tableSort](/javascript/api/excel/excel.tablesort)|_Метод_ > reapply()|Повторно применяет текущие параметры сортировки к таблице.|1.2|
|[workbook](/javascript/api/excel/excel.workbook)|_Связь_ > functions|Представляет экземпляр приложения Excel, содержащий эту книгу. Только для чтения.|1.2|
|[worksheet](/javascript/api/excel/excel.worksheet)|_Связь_ > protection|Возвращает объект защиты листа. Только для чтения.|1.2|
|[worksheetProtection](/javascript/api/excel/excel.worksheetprotection)|_Свойство_ > protected|Указывает, защищен ли лист. Только для чтения. Только для чтения.|1.2|
|[worksheetProtection](/javascript/api/excel/excel.worksheetprotection)|_Связь_ > options|Параметры защиты листа. Только для чтения.|1.2|
|[worksheetProtection](/javascript/api/excel/excel.worksheetprotection)|_Метод_ > protect(options: WorksheetProtectionOptions)|Защищает лист. Выдает ошибку, если лист защищен.|1.2|
|[worksheetProtection](/javascript/api/excel/excel.worksheetprotection)|_Метод_ > unprotect()|Снимает защиту с листа.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowAutoFilter|Представляет параметр защиты листа, разрешающий использовать функцию автофильтра.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowDeleteColumns|Представляет параметр защиты листа, разрешающий удалять столбцы.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowDeleteRows|Представляет параметр защиты листа, разрешающий удалять строки.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowFormatCells|Представляет параметр защиты листа, разрешающий форматировать ячейки.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowFormatColumns|Представляет параметр защиты листа, разрешающий форматировать столбцы.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowFormatRows|Представляет параметр защиты листа, разрешающий форматировать строки.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowInsertColumns|Представляет параметр защиты листа, разрешающий вставлять столбцы.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowInsertHyperlinks|Представляет параметр защиты листа, разрешающий вставлять гиперссылки.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowInsertRows|Представляет параметр защиты листа, разрешающий вставлять строки.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowPivotTables|Представляет параметр защиты листа, разрешающий использовать функцию сводных таблиц.|1.2|
|[worksheetProtectionOptions](/javascript/api/excel/excel.worksheetprotectionoptions)|_Свойство_ > allowSort|Представляет параметр защиты листа, разрешающий использовать функцию сортировки.|1.2|

## <a name="excel-javascript-api-11"></a>API JavaScript для Excel 1.1

API 1.1 JavaScript для Excel — первая версия этого API. Дополнительные сведения об этом API см. в справочных статьях, посвященных [API JavaScript для Excel](/javascript/api/excel).

## <a name="see-also"></a>См. также

- [Версии Office и наборы обязательных элементов](https://docs.microsoft.com/office/dev/add-ins/develop/office-versions-and-requirement-sets)
- [Указание ведущих приложений Office и обязательных элементов API](https://docs.microsoft.com/office/dev/add-ins/develop/specify-office-hosts-and-api-requirements)
- [XML-манифест надстроек Office](https://docs.microsoft.com/office/dev/add-ins/develop/add-in-manifests)