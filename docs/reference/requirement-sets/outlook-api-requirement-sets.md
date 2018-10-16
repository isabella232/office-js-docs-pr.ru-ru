# <a name="outlook-javascript-api-requirement-sets"></a><span data-ttu-id="35e6e-101">Наборы обязательных элементов API JavaScript для Outlook</span><span class="sxs-lookup"><span data-stu-id="35e6e-101">Understanding Outlook API requirement sets</span></span>

<span data-ttu-id="35e6e-102">Для надстроек Outlook требуются определенные версии API, которые указываются в элементе [Requirements](/office/dev/add-ins/reference/manifest/requirements) их [манифестов](https://docs.microsoft.com/office/dev/add-ins/develop/add-in-manifests).</span><span class="sxs-lookup"><span data-stu-id="35e6e-102">Outlook Add-ins declare what API versions they require by using the [Requirements](/office/dev/add-ins/reference/manifest/requirements) element in their [manifest](https://docs.microsoft.com/office/dev/add-ins/develop/add-in-manifests).</span></span> <span data-ttu-id="35e6e-103">Надстройки Outlook всегда включают элемент [Set](/office/dev/add-ins/reference/manifest/set), где для атрибута `Name` задано значение `Mailbox`, а в атрибуте `MinVersion` указан минимальный набор обязательных элементов API, поддерживающий сценарии надстройки.</span><span class="sxs-lookup"><span data-stu-id="35e6e-103">Outlook add-ins always include a [Set](/office/dev/add-ins/reference/manifest/set) element with a `Name` attribute set to `Mailbox` and a `MinVersion` attribute set to the minimum API requirement set that supports the add-in's scenarios.</span></span>

<span data-ttu-id="35e6e-104">Например, в следующем фрагменте манифеста указан минимальный набор обязательных элементов 1.1:</span><span class="sxs-lookup"><span data-stu-id="35e6e-104">For example, the following manifest snippet indicates a minimum requirement set of 1.1:</span></span>

```xml
<Requirements>
  <Sets>
    <Set Name="MailBox" MinVersion="1.1" />
  </Sets>
</Requirements>
```

<span data-ttu-id="35e6e-105">Все API Outlook относятся к `Mailbox`  [набору обязательных элементов](https://docs.microsoft.com/office/dev/add-ins/develop/specify-office-hosts-and-api-requirements).</span><span class="sxs-lookup"><span data-stu-id="35e6e-105">All Outlook APIs belong to the `Mailbox` [requirement set](https://docs.microsoft.com/office/dev/add-ins/develop/specify-office-hosts-and-api-requirements).</span></span> <span data-ttu-id="35e6e-106">Существуют разные версии набора обязательных элементов `Mailbox`. Каждый новый набор API, который мы выпускаем, относится к более высокой версии набора.</span><span class="sxs-lookup"><span data-stu-id="35e6e-106">The `Mailbox` requirement set has versions, and each new set of APIs that we release belongs to a higher version of the set.</span></span> <span data-ttu-id="35e6e-107">Не все клиенты Outlook поддерживают самый новый набор API, но если для клиента Outlook объявлена поддержка определенного набора обязательных элементов, то он поддерживает все API из этого набора.</span><span class="sxs-lookup"><span data-stu-id="35e6e-107">Not all Outlook clients support the newest set of APIs, but if an Outlook client declares support for a requirement set, it supports all of the APIs in that requirement set.</span></span>

<span data-ttu-id="35e6e-p103">Задайте версию минимального набора обязательных элементов в манифесте, чтобы указать клиент Outlook, в котором появится надстройка. Если клиент не поддерживает минимальный набор обязательных элементов, он не загружает надстройку. Например, если указана версия набора обязательных элементов 1.3, надстройка не отобразится в каком-либо клиенте Outlook, который не поддерживает версии 1.3. и ниже.</span><span class="sxs-lookup"><span data-stu-id="35e6e-p103">Setting a minimum requirement set version in the manifest controls which Outlook client the add-in will appear in. If a client does not support the minimum requirement set, it does not load the add-in. For example, if requirement set version 1.3 is specified, this means the add-in will not show up in any Outlook client that doesn't support at least 1.3.</span></span>

## <a name="using-apis-from-later-requirement-sets"></a><span data-ttu-id="35e6e-111">Использование API из наборов обязательных элементов более поздних версий</span><span class="sxs-lookup"><span data-stu-id="35e6e-111">Using APIs from later requirement sets</span></span>

<span data-ttu-id="35e6e-112">Установка набора обязательных элементов не ограничивают доступные API, можно использовать надстройку.</span><span class="sxs-lookup"><span data-stu-id="35e6e-112">Setting a requirement set does not limit the available APIs that the add-in can use.</span></span> <span data-ttu-id="35e6e-113">Например, если надстройка указывает набор обязательных элементов версии 1.1, но она работает в клиенте Outlook, который поддерживает версию 1.3, надстройка может использовать API-интерфейсы из набора обязательных элементов версии 1.3.</span><span class="sxs-lookup"><span data-stu-id="35e6e-113">Setting a requirement set does not limit the available APIs that the add-in can use. For example, if the add-in specifies requirement set 1.1, but it is running in an Outlook client which support 1.3, the add-in can use APIs from requirement set 1.3</span></span>

<span data-ttu-id="35e6e-114">Чтобы использовать более новые API, разработчики могут просто проверить их наличие с помощью стандартных методов JavaScript.</span><span class="sxs-lookup"><span data-stu-id="35e6e-114">To use newer APIs, developers can just check for their existence by using standard JavaScript technique</span></span>

```js
if (item.somePropertyOrFunction !== undefined) {
  item.somePropertyOrFunction ...
}
```

<span data-ttu-id="35e6e-115">Такие проверки не нужно выполнять для API-интерфейсов, присутствующих в версии набора обязательных элементов, указанной в манифесте.</span><span class="sxs-lookup"><span data-stu-id="35e6e-115">No such checks are necessary for any APIs which are present in the requirement set version specified in in the manifest.</span></span>

## <a name="choosing-a-minimum-requirement-set"></a><span data-ttu-id="35e6e-116">Выбор минимального набора обязательных элементов</span><span class="sxs-lookup"><span data-stu-id="35e6e-116">Choosing a minimum requirement set</span></span>

<span data-ttu-id="35e6e-117">Разработчикам следует использовать набор обязательных элементов самой ранней версии, содержащий набор критически важных API для сценария их работы, без которого надстройка не будет работать.</span><span class="sxs-lookup"><span data-stu-id="35e6e-117">Developers should use the earliest requirement set that contains the critical set of APIs for their scenario, without which the add-in won't work.</span></span>

## <a name="clients"></a><span data-ttu-id="35e6e-118">Клиенты</span><span class="sxs-lookup"><span data-stu-id="35e6e-118">Clients</span></span>

<span data-ttu-id="35e6e-119">Указанные ниже клиенты поддерживают надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="35e6e-119">The following clients support Outlook add-ins.</span></span>

| <span data-ttu-id="35e6e-120">Клиент</span><span class="sxs-lookup"><span data-stu-id="35e6e-120">Client</span></span> | <span data-ttu-id="35e6e-121">Поддерживаемые наборы обязательных элементов API</span><span class="sxs-lookup"><span data-stu-id="35e6e-121">Supported API requirement sets</span></span> |
| --- | --- |
| <span data-ttu-id="35e6e-122">Outlook 2019 для Windows</span><span class="sxs-lookup"><span data-stu-id="35e6e-122">Outlook for Windows: </span></span> | <span data-ttu-id="35e6e-123">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6), [1.7](/office/dev/add-ins/reference/objectmodel/requirement-set-1.7/outlook-requirement-set-1.7)</span><span class="sxs-lookup"><span data-stu-id="35e6e-123">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6), [1.7](/office/dev/add-ins/reference/objectmodel/requirement-set-1.7/outlook-requirement-set-1.7)</span></span> |
| <span data-ttu-id="35e6e-124">Outlook 2019 для Mac</span><span class="sxs-lookup"><span data-stu-id="35e6e-124">Outlook for Mac</span></span> | <span data-ttu-id="35e6e-125">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span><span class="sxs-lookup"><span data-stu-id="35e6e-125">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span></span> |
| <span data-ttu-id="35e6e-126">Outlook 2016 (Click-to-Run) для Windows</span><span class="sxs-lookup"><span data-stu-id="35e6e-126">Outlook 2016 (Click-to-Run) for Windows</span></span> | <span data-ttu-id="35e6e-127">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6), [1.7](/office/dev/add-ins/reference/objectmodel/requirement-set-1.7/outlook-requirement-set-1.7)</span><span class="sxs-lookup"><span data-stu-id="35e6e-127">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6), [1.7](/office/dev/add-ins/reference/objectmodel/requirement-set-1.7/outlook-requirement-set-1.7)</span></span> |
| <span data-ttu-id="35e6e-128">Outlook 2016 (MSI) для Windows</span><span class="sxs-lookup"><span data-stu-id="35e6e-128">Outlook 2016 (MSI) for Windows</span></span> | <span data-ttu-id="35e6e-129">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4)</span><span class="sxs-lookup"><span data-stu-id="35e6e-129">1.1, 1.2, 1.3, 1.4</span></span> |
| <span data-ttu-id="35e6e-130">Outlook 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="35e6e-130">Outlook 2016 for Mac</span></span> | <span data-ttu-id="35e6e-131">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span><span class="sxs-lookup"><span data-stu-id="35e6e-131">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span></span> |
| <span data-ttu-id="35e6e-132">Outlook 2013 для Windows</span><span class="sxs-lookup"><span data-stu-id="35e6e-132">Outlook 2013 for Windows</span></span> | <span data-ttu-id="35e6e-133">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4)</span><span class="sxs-lookup"><span data-stu-id="35e6e-133">1.1, 1.2, 1.3, 1.4</span></span> |
| <span data-ttu-id="35e6e-134">Outlook для iPhone</span><span class="sxs-lookup"><span data-stu-id="35e6e-134">Outlook for iPhone</span></span> | <span data-ttu-id="35e6e-135">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5)</span><span class="sxs-lookup"><span data-stu-id="35e6e-135">1.1, 1.2, 1.3, 1.4, 1.5</span></span> |
| <span data-ttu-id="35e6e-136">Outlook для Android</span><span class="sxs-lookup"><span data-stu-id="35e6e-136">Outlook for Android</span></span> | <span data-ttu-id="35e6e-137">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5)</span><span class="sxs-lookup"><span data-stu-id="35e6e-137">1.1, 1.2, 1.3, 1.4, 1.5</span></span> |
| <span data-ttu-id="35e6e-138">Outlook в Интернете (Office 365 и Outlook.com)</span><span class="sxs-lookup"><span data-stu-id="35e6e-138">Outlook on the web (Office 365 and Outlook.com)</span></span> | <span data-ttu-id="35e6e-139">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span><span class="sxs-lookup"><span data-stu-id="35e6e-139">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3), [1.4](/office/dev/add-ins/reference/objectmodel/requirement-set-1.4/outlook-requirement-set-1.4), [1.5](/office/dev/add-ins/reference/objectmodel/requirement-set-1.5/outlook-requirement-set-1.5), [1.6](/office/dev/add-ins/reference/objectmodel/requirement-set-1.6/outlook-requirement-set-1.6)</span></span> |
| <span data-ttu-id="35e6e-140">Outlook Web App (Exchange 2013 в локальной среде)</span><span class="sxs-lookup"><span data-stu-id="35e6e-140">Outlook Web App (Exchange 2013 On-Premise)</span></span> | [<span data-ttu-id="35e6e-141">1.1</span><span class="sxs-lookup"><span data-stu-id="35e6e-141">1.1</span></span>](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1) |
| <span data-ttu-id="35e6e-142">Outlook Web App (Exchange 2016 в локальной среде)</span><span class="sxs-lookup"><span data-stu-id="35e6e-142">Outlook Web App (Exchange 2016 On-Premise)</span></span> | <span data-ttu-id="35e6e-143">[1.1](/office/dev/add-ins/reference/objectmodel/requirement-set-1.1/outlook-requirement-set-1.1), [1.2](/office/dev/add-ins/reference/objectmodel/requirement-set-1.2/outlook-requirement-set-1.2), [1.3](/office/dev/add-ins/reference/objectmodel/requirement-set-1.3/outlook-requirement-set-1.3)</span><span class="sxs-lookup"><span data-stu-id="35e6e-143">1.1, 1.2. 1.3</span></span> |

> [!NOTE]
> <span data-ttu-id="35e6e-144">Поддержка версии 1.3 в Outlook 2013 добавлена в рамках [обновления для Outlook 2013 (KB3114349) от 8 декабря 2015 г.](https://support.microsoft.com/kb/3114349).</span><span class="sxs-lookup"><span data-stu-id="35e6e-144">Note Support for 1.3 in Outlook 2013 was added as part of the [December 8, 2015, update for Outlook 2013 (KB3114349)](https://support.microsoft.com/kb/3114349)</span></span> <span data-ttu-id="35e6e-145">Поддержка версии 1.4 в Outlook 2013 добавлена в рамках [обновления для Outlook 2013 (KB3118280) от 13 декабря 2016 г.](https://support.microsoft.com/help/3118280).</span><span class="sxs-lookup"><span data-stu-id="35e6e-145">Note Support for 1.3 in Outlook 2013 was added as part of the [December 8, 2015, update for Outlook 2013 (KB3114349)](https://support.microsoft.com/help/3118280)</span></span>