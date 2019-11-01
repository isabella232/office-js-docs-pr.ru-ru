---
title: Office. Context. Mailbox — набор обязательных элементов 1,8
description: ''
ms.date: 10/31/2019
localization_priority: Normal
ms.openlocfilehash: 3f6d639cdf8bdff6f2df365622f58eba1c4b38e0
ms.sourcegitcommit: e989096f3d19761bf8477c585cde20b3f8e0b90d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "37902204"
---
# <a name="mailbox"></a><span data-ttu-id="69eb3-102">mailbox</span><span class="sxs-lookup"><span data-stu-id="69eb3-102">mailbox</span></span>

### <a name="officeofficemdcontextofficecontextmdmailbox"></a><span data-ttu-id="69eb3-103">[Office](Office.md)[.context](Office.context.md).mailbox</span><span class="sxs-lookup"><span data-stu-id="69eb3-103">[Office](Office.md)[.context](Office.context.md).mailbox</span></span>

<span data-ttu-id="69eb3-104">Предоставляет для Microsoft Outlook доступ к объектной модели надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="69eb3-104">Provides access to the Outlook add-in object model for Microsoft Outlook.</span></span>

##### <a name="requirements"></a><span data-ttu-id="69eb3-105">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-105">Requirements</span></span>

|<span data-ttu-id="69eb3-106">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-106">Requirement</span></span>| <span data-ttu-id="69eb3-107">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-107">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-108">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-108">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-109">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-109">1.0</span></span>|
|[<span data-ttu-id="69eb3-110">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-110">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-111">С ограничениями</span><span class="sxs-lookup"><span data-stu-id="69eb3-111">Restricted</span></span>|
|[<span data-ttu-id="69eb3-112">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-112">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-113">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-113">Compose or Read</span></span>|

##### <a name="members-and-methods"></a><span data-ttu-id="69eb3-114">Элементы и методы</span><span class="sxs-lookup"><span data-stu-id="69eb3-114">Members and methods</span></span>

| <span data-ttu-id="69eb3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="69eb3-115">Member</span></span> | <span data-ttu-id="69eb3-116">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-116">Type</span></span> |
|--------|------|
| [<span data-ttu-id="69eb3-117">ewsUrl</span><span class="sxs-lookup"><span data-stu-id="69eb3-117">ewsUrl</span></span>](#ewsurl-string) | <span data-ttu-id="69eb3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="69eb3-118">Member</span></span> |
| [<span data-ttu-id="69eb3-119">мастеркатегориес</span><span class="sxs-lookup"><span data-stu-id="69eb3-119">masterCategories</span></span>](#mastercategories-mastercategories) | <span data-ttu-id="69eb3-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="69eb3-120">Member</span></span> |
| [<span data-ttu-id="69eb3-121">restUrl</span><span class="sxs-lookup"><span data-stu-id="69eb3-121">restUrl</span></span>](#resturl-string) | <span data-ttu-id="69eb3-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="69eb3-122">Member</span></span> |
| [<span data-ttu-id="69eb3-123">addHandlerAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-123">addHandlerAsync</span></span>](#addhandlerasynceventtype-handler-options-callback) | <span data-ttu-id="69eb3-124">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-124">Method</span></span> |
| [<span data-ttu-id="69eb3-125">convertToEwsId</span><span class="sxs-lookup"><span data-stu-id="69eb3-125">convertToEwsId</span></span>](#converttoewsiditemid-restversion--string) | <span data-ttu-id="69eb3-126">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-126">Method</span></span> |
| [<span data-ttu-id="69eb3-127">convertToLocalClientTime</span><span class="sxs-lookup"><span data-stu-id="69eb3-127">convertToLocalClientTime</span></span>](#converttolocalclienttimetimevalue--localclienttime) | <span data-ttu-id="69eb3-128">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-128">Method</span></span> |
| [<span data-ttu-id="69eb3-129">convertToRestId</span><span class="sxs-lookup"><span data-stu-id="69eb3-129">convertToRestId</span></span>](#converttorestiditemid-restversion--string) | <span data-ttu-id="69eb3-130">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-130">Method</span></span> |
| [<span data-ttu-id="69eb3-131">convertToUtcClientTime</span><span class="sxs-lookup"><span data-stu-id="69eb3-131">convertToUtcClientTime</span></span>](#converttoutcclienttimeinput--date) | <span data-ttu-id="69eb3-132">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-132">Method</span></span> |
| [<span data-ttu-id="69eb3-133">displayAppointmentForm</span><span class="sxs-lookup"><span data-stu-id="69eb3-133">displayAppointmentForm</span></span>](#displayappointmentformitemid) | <span data-ttu-id="69eb3-134">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-134">Method</span></span> |
| [<span data-ttu-id="69eb3-135">displayMessageForm</span><span class="sxs-lookup"><span data-stu-id="69eb3-135">displayMessageForm</span></span>](#displaymessageformitemid) | <span data-ttu-id="69eb3-136">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-136">Method</span></span> |
| [<span data-ttu-id="69eb3-137">displayNewAppointmentForm</span><span class="sxs-lookup"><span data-stu-id="69eb3-137">displayNewAppointmentForm</span></span>](#displaynewappointmentformparameters) | <span data-ttu-id="69eb3-138">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-138">Method</span></span> |
| [<span data-ttu-id="69eb3-139">дисплайневмессажеформ</span><span class="sxs-lookup"><span data-stu-id="69eb3-139">displayNewMessageForm</span></span>](#displaynewmessageformparameters) | <span data-ttu-id="69eb3-140">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-140">Method</span></span> |
| [<span data-ttu-id="69eb3-141">getCallbackTokenAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-141">getCallbackTokenAsync</span></span>](#getcallbacktokenasyncoptions-callback) | <span data-ttu-id="69eb3-142">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-142">Method</span></span> |
| [<span data-ttu-id="69eb3-143">getCallbackTokenAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-143">getCallbackTokenAsync</span></span>](#getcallbacktokenasynccallback-usercontext) | <span data-ttu-id="69eb3-144">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-144">Method</span></span> |
| [<span data-ttu-id="69eb3-145">getUserIdentityTokenAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-145">getUserIdentityTokenAsync</span></span>](#getuseridentitytokenasynccallback-usercontext) | <span data-ttu-id="69eb3-146">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-146">Method</span></span> |
| [<span data-ttu-id="69eb3-147">makeEwsRequestAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-147">makeEwsRequestAsync</span></span>](#makeewsrequestasyncdata-callback-usercontext) | <span data-ttu-id="69eb3-148">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-148">Method</span></span> |
| [<span data-ttu-id="69eb3-149">removeHandlerAsync</span><span class="sxs-lookup"><span data-stu-id="69eb3-149">removeHandlerAsync</span></span>](#removehandlerasynceventtype-options-callback) | <span data-ttu-id="69eb3-150">Метод</span><span class="sxs-lookup"><span data-stu-id="69eb3-150">Method</span></span> |

### <a name="namespaces"></a><span data-ttu-id="69eb3-151">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="69eb3-151">Namespaces</span></span>

<span data-ttu-id="69eb3-152">[diagnostics](Office.context.mailbox.diagnostics.md). Предоставляет надстройке Outlook диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-152">[diagnostics](Office.context.mailbox.diagnostics.md): Provides diagnostic information to an Outlook add-in.</span></span>

<span data-ttu-id="69eb3-153">[item](Office.context.mailbox.item.md). Предоставляет методы и свойства для доступа к сообщению или встрече в надстройке Outlook.</span><span class="sxs-lookup"><span data-stu-id="69eb3-153">[item](Office.context.mailbox.item.md): Provides methods and properties for accessing a message or appointment in an Outlook add-in.</span></span>

<span data-ttu-id="69eb3-154">[userProfile](Office.context.mailbox.userProfile.md). Предоставляет сведения о пользователе в надстройке Outlook.</span><span class="sxs-lookup"><span data-stu-id="69eb3-154">[userProfile](Office.context.mailbox.userProfile.md): Provides information about the user in an Outlook add-in.</span></span>

### <a name="members"></a><span data-ttu-id="69eb3-155">Members</span><span class="sxs-lookup"><span data-stu-id="69eb3-155">Members</span></span>

#### <a name="ewsurl-string"></a><span data-ttu-id="69eb3-156">ewsUrl: String</span><span class="sxs-lookup"><span data-stu-id="69eb3-156">ewsUrl: String</span></span>

<span data-ttu-id="69eb3-p101">Получает URL-адрес конечной точки веб-служб Exchange (EWS) для этой учетной записи электронной почты. Только в режиме чтения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p101">Gets the URL of the Exchange Web Services (EWS) endpoint for this email account. Read mode only.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-159">Этот элемент не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-159">This member is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-p102">Удаленная служба может использовать значение `ewsUrl`, чтобы выполнять вызовы EWS для почтового ящика пользователя. Например, вы можете создать удаленную службу, чтобы [получить вложения из выбранного элемента](/outlook/add-ins/get-attachments-of-an-outlook-item).</span><span class="sxs-lookup"><span data-stu-id="69eb3-p102">The `ewsUrl` value can be used by a remote service to make EWS calls to the user's mailbox. For example, you can create a remote service to [get attachments from the selected item](/outlook/add-ins/get-attachments-of-an-outlook-item).</span></span>

<span data-ttu-id="69eb3-162">Чтобы вызвать элемент `ewsUrl` в режиме чтения, в манифесте приложения должно быть указано разрешение **ReadItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-162">Your app must have the **ReadItem** permission specified in its manifest to call the `ewsUrl` member in read mode.</span></span>

<span data-ttu-id="69eb3-p103">Перед использованием элемента `ewsUrl` в режиме создания необходимо вызвать метод [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback). Для вызова метода `saveAsync` приложение должно иметь разрешения **ReadWriteItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p103">In compose mode you must call the [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) method before you can use the `ewsUrl` member. Your app must have **ReadWriteItem** permissions to call the `saveAsync` method.</span></span>

##### <a name="type"></a><span data-ttu-id="69eb3-165">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-165">Type</span></span>

*   <span data-ttu-id="69eb3-166">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-166">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="69eb3-167">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-167">Requirements</span></span>

|<span data-ttu-id="69eb3-168">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-168">Requirement</span></span>| <span data-ttu-id="69eb3-169">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-169">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-170">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-170">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-171">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-171">1.0</span></span>|
|[<span data-ttu-id="69eb3-172">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-172">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-173">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-173">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-174">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-174">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-175">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-175">Compose or Read</span></span>|

<br>

---
---

#### <a name="mastercategories-mastercategoriesjavascriptapioutlookofficemastercategoriesviewoutlook-js-18"></a><span data-ttu-id="69eb3-176">Мастеркатегориес: [мастеркатегориес](/javascript/api/outlook/office.mastercategories?view=outlook-js-1.8)</span><span class="sxs-lookup"><span data-stu-id="69eb3-176">masterCategories: [MasterCategories](/javascript/api/outlook/office.mastercategories?view=outlook-js-1.8)</span></span>

<span data-ttu-id="69eb3-177">Получает объект, предоставляющий методы для управления главным списком категорий в этом почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="69eb3-177">Gets an object that provides methods to manage the categories master list on this mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-178">Этот элемент не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-178">This member is not supported in Outlook on iOS or Android.</span></span>

##### <a name="type"></a><span data-ttu-id="69eb3-179">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-179">Type</span></span>

*   [<span data-ttu-id="69eb3-180">MasterCategories</span><span class="sxs-lookup"><span data-stu-id="69eb3-180">MasterCategories</span></span>](/javascript/api/outlook/office.mastercategories?view=outlook-js-1.8)

##### <a name="requirements"></a><span data-ttu-id="69eb3-181">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-181">Requirements</span></span>

|<span data-ttu-id="69eb3-182">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-182">Requirement</span></span>| <span data-ttu-id="69eb3-183">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-183">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-184">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-184">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-185">1.8</span><span class="sxs-lookup"><span data-stu-id="69eb3-185">1.8</span></span> |
|[<span data-ttu-id="69eb3-186">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-186">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-187">ReadWriteMailbox</span><span class="sxs-lookup"><span data-stu-id="69eb3-187">ReadWriteMailbox</span></span> |
|[<span data-ttu-id="69eb3-188">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-188">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-189">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-189">Compose or Read</span></span> |

##### <a name="example"></a><span data-ttu-id="69eb3-190">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-190">Example</span></span>

<span data-ttu-id="69eb3-191">В этом примере показано получение сводного списка категорий для этого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="69eb3-191">This example gets the categories master list for this mailbox.</span></span>

```js
Office.context.mailbox.masterCategories.getAsync(function (asyncResult) {
  if (asyncResult.status === Office.AsyncResultStatus.Failed) {
    console.log("Action failed with error: " + asyncResult.error.message);
  } else {
    console.log("Master categories: " + JSON.stringify(asyncResult.value));
  }
});
```

<br>

---
---

#### <a name="resturl-string"></a><span data-ttu-id="69eb3-192">restUrl: String</span><span class="sxs-lookup"><span data-stu-id="69eb3-192">restUrl: String</span></span>

<span data-ttu-id="69eb3-193">Возвращает URL-адрес конечной точки REST для этой учетной записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="69eb3-193">Gets the URL of the REST endpoint for this email account.</span></span>

<span data-ttu-id="69eb3-194">С помощью значения `restUrl` можно выполнять вызовы [REST API](/outlook/rest/) для почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="69eb3-194">The `restUrl` value can be used to make [REST API](/outlook/rest/) calls to the user's mailbox.</span></span>

<span data-ttu-id="69eb3-195">Чтобы вызвать элемент `restUrl` в режиме чтения, в манифесте приложения необходимо указать разрешение **ReadItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-195">Your app must have the **ReadItem** permission specified in its manifest to call the `restUrl` member in read mode.</span></span>

<span data-ttu-id="69eb3-p104">Перед использованием элемента `restUrl` в режиме создания необходимо вызвать метод [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback). Для вызова метода `saveAsync` приложение должно иметь разрешения **ReadWriteItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p104">In compose mode you must call the [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) method before you can use the `restUrl` member. Your app must have **ReadWriteItem** permissions to call the `saveAsync` method.</span></span>

##### <a name="type"></a><span data-ttu-id="69eb3-198">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-198">Type</span></span>

*   <span data-ttu-id="69eb3-199">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-199">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="69eb3-200">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-200">Requirements</span></span>

|<span data-ttu-id="69eb3-201">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-201">Requirement</span></span>| <span data-ttu-id="69eb3-202">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-202">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-203">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-203">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-204">1.5</span><span class="sxs-lookup"><span data-stu-id="69eb3-204">1.5</span></span> |
|[<span data-ttu-id="69eb3-205">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-205">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-206">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-206">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-207">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-207">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-208">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-208">Compose or Read</span></span>|

### <a name="methods"></a><span data-ttu-id="69eb3-209">Методы</span><span class="sxs-lookup"><span data-stu-id="69eb3-209">Methods</span></span>

#### <a name="addhandlerasynceventtype-handler-options-callback"></a><span data-ttu-id="69eb3-210">addHandlerAsync(eventType, handler, [options], [callback])</span><span class="sxs-lookup"><span data-stu-id="69eb3-210">addHandlerAsync(eventType, handler, [options], [callback])</span></span>

<span data-ttu-id="69eb3-211">Добавляет обработчик для поддерживаемого события.</span><span class="sxs-lookup"><span data-stu-id="69eb3-211">Adds an event handler for a supported event.</span></span>

<span data-ttu-id="69eb3-212">В настоящее время поддерживаются типы событий `Office.EventType.ItemChanged` и `Office.EventType.OfficeThemeChanged`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-212">Currently, the supported event types are `Office.EventType.ItemChanged` and `Office.EventType.OfficeThemeChanged`.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-213">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-213">Parameters</span></span>

| <span data-ttu-id="69eb3-214">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-214">Name</span></span> | <span data-ttu-id="69eb3-215">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-215">Type</span></span> | <span data-ttu-id="69eb3-216">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-216">Attributes</span></span> | <span data-ttu-id="69eb3-217">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-217">Description</span></span> |
|---|---|---|---|
| `eventType` | [<span data-ttu-id="69eb3-218">Office.EventType</span><span class="sxs-lookup"><span data-stu-id="69eb3-218">Office.EventType</span></span>](office.md#eventtype-string) || <span data-ttu-id="69eb3-219">Событие, которое должно вызвать обработчик.</span><span class="sxs-lookup"><span data-stu-id="69eb3-219">The event that should invoke the handler.</span></span> |
| `handler` | <span data-ttu-id="69eb3-220">Function</span><span class="sxs-lookup"><span data-stu-id="69eb3-220">Function</span></span> || <span data-ttu-id="69eb3-p105">Функция для обработки события. Функция должна принимать один параметр, представляющий собой объектный литерал. Значение свойства `type` параметра совпадет со значением параметра `eventType`, переданного методу `addHandlerAsync`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p105">The function to handle the event. The function must accept a single parameter, which is an object literal. The `type` property on the parameter will match the `eventType` parameter passed to `addHandlerAsync`.</span></span> |
| `options` | <span data-ttu-id="69eb3-224">Объект</span><span class="sxs-lookup"><span data-stu-id="69eb3-224">Object</span></span> | <span data-ttu-id="69eb3-225">&lt;Необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-225">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-226">Объектный литерал, содержащий одно или несколько из указанных ниже свойств.</span><span class="sxs-lookup"><span data-stu-id="69eb3-226">An object literal that contains one or more of the following properties.</span></span> |
| `options.asyncContext` | <span data-ttu-id="69eb3-227">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-227">Object</span></span> | <span data-ttu-id="69eb3-228">&lt;Необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-228">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-229">Разработчики могут указать любой объект, к которому необходимо получить доступ, в методе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="69eb3-229">Developers can provide any object they wish to access in the callback method.</span></span> |
| `callback` | <span data-ttu-id="69eb3-230">функция</span><span class="sxs-lookup"><span data-stu-id="69eb3-230">function</span></span>| <span data-ttu-id="69eb3-231">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-231">&lt;optional&gt;</span></span>|<span data-ttu-id="69eb3-232">После применения метода функция, переданная в параметр `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-232">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-233">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-233">Requirements</span></span>

|<span data-ttu-id="69eb3-234">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-234">Requirement</span></span>| <span data-ttu-id="69eb3-235">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-235">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-236">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-236">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-237">1.5</span><span class="sxs-lookup"><span data-stu-id="69eb3-237">1.5</span></span> |
|[<span data-ttu-id="69eb3-238">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-238">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-239">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-239">ReadItem</span></span> |
|[<span data-ttu-id="69eb3-240">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-240">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-241">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-241">Compose or Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-242">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-242">Example</span></span>

```js
Office.initialize = function (reason) {
  $(document).ready(function () {
    Office.context.mailbox.addHandlerAsync(Office.EventType.ItemChanged, loadNewItem, function (result) {
      if (result.status === Office.AsyncResultStatus.Failed) {
        // Handle error.
      }
    });
  });
};

function loadNewItem(eventArgs) {
  // Load the properties of the newly selected item.
  loadProps(Office.context.mailbox.item);
}
```

<br>

---
---

#### <a name="converttoewsiditemid-restversion--string"></a><span data-ttu-id="69eb3-243">convertToEwsId(itemId, restVersion) → {String}</span><span class="sxs-lookup"><span data-stu-id="69eb3-243">convertToEwsId(itemId, restVersion) → {String}</span></span>

<span data-ttu-id="69eb3-244">Преобразовывает идентификатор элемента из формата REST в формат EWS.</span><span class="sxs-lookup"><span data-stu-id="69eb3-244">Converts an item ID formatted for REST into EWS format.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-245">Этот метод не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-245">This method is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-p106">Формат идентификаторов, извлекаемых через API REST (например, [API Почты Outlook](/previous-versions/office/office-365-api/api/version-2.0/mail-rest-operations) или [Microsoft Graph](https://graph.microsoft.io/)), отличается от формата веб-служб Exchange (EWS). Метод `convertToEwsId` преобразовывает идентификатор в формате REST в формат EWS.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p106">Item IDs retrieved via a REST API (such as the [Outlook Mail API](/previous-versions/office/office-365-api/api/version-2.0/mail-rest-operations) or the [Microsoft Graph](https://graph.microsoft.io/)) use a different format than the format used by Exchange Web Services (EWS). The `convertToEwsId` method converts a REST-formatted ID into the proper format for EWS.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-248">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-248">Parameters</span></span>

|<span data-ttu-id="69eb3-249">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-249">Name</span></span>| <span data-ttu-id="69eb3-250">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-250">Type</span></span>| <span data-ttu-id="69eb3-251">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-251">Description</span></span>|
|---|---|---|
|`itemId`| <span data-ttu-id="69eb3-252">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-252">String</span></span>|<span data-ttu-id="69eb3-253">Идентификатор элемента в формате REST API для Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-253">An item ID formatted for the Outlook REST APIs</span></span>|
|`restVersion`| [<span data-ttu-id="69eb3-254">Office.MailboxEnums.RestVersion</span><span class="sxs-lookup"><span data-stu-id="69eb3-254">Office.MailboxEnums.RestVersion</span></span>](/javascript/api/outlook/office.mailboxenums.restversion?view=outlook-js-1.8)|<span data-ttu-id="69eb3-255">Значение, определяющее версию REST API для Outlook, которая используется для извлечения идентификатора элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-255">A value indicating the version of the Outlook REST API used to retrieve the item ID.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-256">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-256">Requirements</span></span>

|<span data-ttu-id="69eb3-257">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-257">Requirement</span></span>| <span data-ttu-id="69eb3-258">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-258">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-259">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-259">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-260">1.3</span><span class="sxs-lookup"><span data-stu-id="69eb3-260">1.3</span></span>|
|[<span data-ttu-id="69eb3-261">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-261">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-262">С ограничениями</span><span class="sxs-lookup"><span data-stu-id="69eb3-262">Restricted</span></span>|
|[<span data-ttu-id="69eb3-263">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-263">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-264">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-264">Compose or Read</span></span>|

##### <a name="returns"></a><span data-ttu-id="69eb3-265">Возвращаемое значение:</span><span class="sxs-lookup"><span data-stu-id="69eb3-265">Returns:</span></span>

<span data-ttu-id="69eb3-266">Тип: String</span><span class="sxs-lookup"><span data-stu-id="69eb3-266">Type: String</span></span>

##### <a name="example"></a><span data-ttu-id="69eb3-267">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-267">Example</span></span>

```js
// Get an item's ID from a REST API.
var restId = 'AAMkAGVlOTZjNTM3LW...';

// Treat restId as coming from the v2.0 version of the Outlook Mail API.
var ewsId = Office.context.mailbox.convertToEwsId(restId, Office.MailboxEnums.RestVersion.v2_0);
```

<br>

---
---

#### <a name="converttolocalclienttimetimevalue--localclienttimejavascriptapioutlookofficelocalclienttimeviewoutlook-js-18"></a><span data-ttu-id="69eb3-268">convertToLocalClientTime(timeValue) → {[LocalClientTime](/javascript/api/outlook/office.LocalClientTime?view=outlook-js-1.8)}</span><span class="sxs-lookup"><span data-stu-id="69eb3-268">convertToLocalClientTime(timeValue) → {[LocalClientTime](/javascript/api/outlook/office.LocalClientTime?view=outlook-js-1.8)}</span></span>

<span data-ttu-id="69eb3-269">Получает словарь, содержащий сведения о локальном времени клиента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-269">Gets a dictionary containing time information in local client time.</span></span>

<span data-ttu-id="69eb3-p107">Почтовое приложение для классической версии Outlook или версии в Интернете может использовать разные часовые пояса для дат и времени. Классическое приложение Outlook использует часовой пояс клиентского компьютера. Outlook в Интернете использует часовой пояс, заданный в Центре администрирования Exchange (EAC). Значения даты и времени должны обрабатываться так, чтобы значения в пользовательском интерфейсе всегда согласовывались с часовым поясом, ожидаемым пользователем.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p107">A mail app for Outlook on a desktop or on the web can use different time zones for the dates and times. Outlook on a desktop uses the client computer time zone; Outlook on the web uses the time zone set on the Exchange Admin Center (EAC). You should handle date and time values so that the values you display on the user interface are always consistent with the time zone that the user expects.</span></span>

<span data-ttu-id="69eb3-p108">Если почтовое приложение работает в классическом клиенте Outlook, метод `convertToLocalClientTime` вернет объект словаря со значениями часового пояса клиентского компьютера. Если почтовое приложение работает в Outlook в Интернете, метод `convertToLocalClientTime` вернет объект словаря со значениями часового пояса, заданного в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p108">If the mail app is running in Outlook on a desktop client, the `convertToLocalClientTime` method will return a dictionary object with the values set to the client computer time zone. If the mail app is running in Outlook on the web, the `convertToLocalClientTime` method will return a dictionary object with the values set to the time zone specified in the EAC.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-275">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-275">Parameters</span></span>

|<span data-ttu-id="69eb3-276">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-276">Name</span></span>| <span data-ttu-id="69eb3-277">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-277">Type</span></span>| <span data-ttu-id="69eb3-278">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-278">Description</span></span>|
|---|---|---|
|`timeValue`| <span data-ttu-id="69eb3-279">Date</span><span class="sxs-lookup"><span data-stu-id="69eb3-279">Date</span></span>|<span data-ttu-id="69eb3-280">Объект Date</span><span class="sxs-lookup"><span data-stu-id="69eb3-280">A Date object</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-281">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-281">Requirements</span></span>

|<span data-ttu-id="69eb3-282">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-282">Requirement</span></span>| <span data-ttu-id="69eb3-283">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-283">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-284">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-284">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-285">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-285">1.0</span></span>|
|[<span data-ttu-id="69eb3-286">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-286">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-287">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-287">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-288">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-288">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-289">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-289">Compose or Read</span></span>|

##### <a name="returns"></a><span data-ttu-id="69eb3-290">Возвращаемое значение:</span><span class="sxs-lookup"><span data-stu-id="69eb3-290">Returns:</span></span>

<span data-ttu-id="69eb3-291">Тип: [LocalClientTime](/javascript/api/outlook/office.LocalClientTime?view=outlook-js-1.8)</span><span class="sxs-lookup"><span data-stu-id="69eb3-291">Type: [LocalClientTime](/javascript/api/outlook/office.LocalClientTime?view=outlook-js-1.8)</span></span>

<br>

---
---

#### <a name="converttorestiditemid-restversion--string"></a><span data-ttu-id="69eb3-292">convertToRestId(itemId, restVersion) → {String}</span><span class="sxs-lookup"><span data-stu-id="69eb3-292">convertToRestId(itemId, restVersion) → {String}</span></span>

<span data-ttu-id="69eb3-293">Преобразовывает идентификатор элемента в формате EWS в формат REST.</span><span class="sxs-lookup"><span data-stu-id="69eb3-293">Converts an item ID formatted for EWS into REST format.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-294">Этот метод не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-294">This method is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-p109">Формат идентификаторов, извлекаемых через EWS или свойство `itemId`, отличается от формата API REST (таких как [API Почты Outlook](/previous-versions/office/office-365-api/api/version-2.0/mail-rest-operations) или [Microsoft Graph](https://graph.microsoft.io/)). Метод `convertToRestId` преобразовывает идентификатор в формате EWS в формат REST.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p109">Item IDs retrieved via EWS or via the `itemId` property use a different format than the format used by REST APIs (such as the [Outlook Mail API](/previous-versions/office/office-365-api/api/version-2.0/mail-rest-operations) or the [Microsoft Graph](https://graph.microsoft.io/)). The `convertToRestId` method converts an EWS-formatted ID into the proper format for REST.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-297">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-297">Parameters</span></span>

|<span data-ttu-id="69eb3-298">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-298">Name</span></span>| <span data-ttu-id="69eb3-299">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-299">Type</span></span>| <span data-ttu-id="69eb3-300">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-300">Description</span></span>|
|---|---|---|
|`itemId`| <span data-ttu-id="69eb3-301">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-301">String</span></span>|<span data-ttu-id="69eb3-302">Идентификатор элемента в формате EWS</span><span class="sxs-lookup"><span data-stu-id="69eb3-302">An item ID formatted for Exchange Web Services (EWS)</span></span>|
|`restVersion`| [<span data-ttu-id="69eb3-303">Office.MailboxEnums.RestVersion</span><span class="sxs-lookup"><span data-stu-id="69eb3-303">Office.MailboxEnums.RestVersion</span></span>](/javascript/api/outlook/office.mailboxenums.restversion?view=outlook-js-1.8)|<span data-ttu-id="69eb3-304">Значение, определяющее версию REST API для Outlook, с которой будет использоваться преобразованный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="69eb3-304">A value indicating the version of the Outlook REST API that the converted ID will be used with.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-305">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-305">Requirements</span></span>

|<span data-ttu-id="69eb3-306">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-306">Requirement</span></span>| <span data-ttu-id="69eb3-307">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-307">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-308">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-308">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-309">1.3</span><span class="sxs-lookup"><span data-stu-id="69eb3-309">1.3</span></span>|
|[<span data-ttu-id="69eb3-310">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-310">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-311">С ограничениями</span><span class="sxs-lookup"><span data-stu-id="69eb3-311">Restricted</span></span>|
|[<span data-ttu-id="69eb3-312">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-312">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-313">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-313">Compose or Read</span></span>|

##### <a name="returns"></a><span data-ttu-id="69eb3-314">Возвращаемое значение:</span><span class="sxs-lookup"><span data-stu-id="69eb3-314">Returns:</span></span>

<span data-ttu-id="69eb3-315">Тип: String</span><span class="sxs-lookup"><span data-stu-id="69eb3-315">Type: String</span></span>

##### <a name="example"></a><span data-ttu-id="69eb3-316">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-316">Example</span></span>

```js
// Get the currently selected item's ID.
var ewsId = Office.context.mailbox.item.itemId;

// Convert to a REST ID for the v2.0 version of the Outlook Mail API.
var restId = Office.context.mailbox.convertToRestId(ewsId, Office.MailboxEnums.RestVersion.v2_0);
```

<br>

---
---

#### <a name="converttoutcclienttimeinput--date"></a><span data-ttu-id="69eb3-317">convertToUtcClientTime(input) → {Date}</span><span class="sxs-lookup"><span data-stu-id="69eb3-317">convertToUtcClientTime(input) → {Date}</span></span>

<span data-ttu-id="69eb3-318">Получает объект Date из словаря, содержащего сведения о времени.</span><span class="sxs-lookup"><span data-stu-id="69eb3-318">Gets a Date object from a dictionary containing time information.</span></span>

<span data-ttu-id="69eb3-319">Метод `convertToUtcClientTime` преобразует словарь, содержащий локальную дату и время, в объект Date с правильными значениями локальной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="69eb3-319">The `convertToUtcClientTime` method converts a dictionary containing a local date and time to a Date object with the correct values for the local date and time.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-320">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-320">Parameters</span></span>

|<span data-ttu-id="69eb3-321">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-321">Name</span></span>| <span data-ttu-id="69eb3-322">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-322">Type</span></span>| <span data-ttu-id="69eb3-323">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-323">Description</span></span>|
|---|---|---|
|`input`| [<span data-ttu-id="69eb3-324">LocalClientTime</span><span class="sxs-lookup"><span data-stu-id="69eb3-324">LocalClientTime</span></span>](/javascript/api/outlook/office.LocalClientTime?view=outlook-js-1.8)|<span data-ttu-id="69eb3-325">Значение локального времени для преобразования.</span><span class="sxs-lookup"><span data-stu-id="69eb3-325">The local time value to convert.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-326">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-326">Requirements</span></span>

|<span data-ttu-id="69eb3-327">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-327">Requirement</span></span>| <span data-ttu-id="69eb3-328">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-328">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-329">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-329">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-330">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-330">1.0</span></span>|
|[<span data-ttu-id="69eb3-331">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-331">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-332">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-332">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-333">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-333">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-334">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-334">Compose or Read</span></span>|

##### <a name="returns"></a><span data-ttu-id="69eb3-335">Возвращаемое значение:</span><span class="sxs-lookup"><span data-stu-id="69eb3-335">Returns:</span></span>

<span data-ttu-id="69eb3-336">Объект Date со временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="69eb3-336">A Date object with the time expressed in UTC.</span></span>

<span data-ttu-id="69eb3-337">Тип: Date</span><span class="sxs-lookup"><span data-stu-id="69eb3-337">Type: Date</span></span>

##### <a name="example"></a><span data-ttu-id="69eb3-338">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-338">Example</span></span>

```js
// Represents 3:37 PM PDT on Monday, August 26, 2019.
var input = {
  date: 26,
  hours: 15,
  milliseconds: 2,
  minutes: 37,
  month: 7,
  seconds: 2,
  timezoneOffset: -420,
  year: 2019
};

// result should be a Date object.
var result = Office.context.mailbox.convertToUtcClientTime(input);

// Output should be "2019-08-26T22:37:02.002Z".
console.log(result.toISOString());
```

<br>

---
---

#### <a name="displayappointmentformitemid"></a><span data-ttu-id="69eb3-339">displayAppointmentForm(itemId)</span><span class="sxs-lookup"><span data-stu-id="69eb3-339">displayAppointmentForm(itemId)</span></span>

<span data-ttu-id="69eb3-340">Отображает имеющуюся встречу из календаря.</span><span class="sxs-lookup"><span data-stu-id="69eb3-340">Displays an existing calendar appointment.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-341">Этот метод не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-341">This method is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-342">Метод `displayAppointmentForm` открывает новое окно на компьютере или диалоговое окно на мобильном устройстве, содержащее сведения календаря о существующей встрече.</span><span class="sxs-lookup"><span data-stu-id="69eb3-342">The `displayAppointmentForm` method opens an existing calendar appointment in a new window on the desktop or in a dialog box on mobile devices.</span></span>

<span data-ttu-id="69eb3-p110">В Outlook для Mac с помощью этого метода можно отобразить одну встречу, которая не является частью повторяющегося ряда, или основную встречу такого ряда, но не экземпляр из него, так как в Outlook для Mac невозможно получить доступ к свойствам экземпляра повторяющегося ряда (в том числе к идентификатору элемента).</span><span class="sxs-lookup"><span data-stu-id="69eb3-p110">In Outlook on Mac, you can use this method to display a single appointment that is not part of a recurring series, or the master appointment of a recurring series, but you cannot display an instance of the series. This is because in Outlook on Mac, you cannot access the properties (including the item ID) of instances of a recurring series.</span></span>

<span data-ttu-id="69eb3-345">В Outlook в Интернете этот метод открывает указанную форму, только если текст формы содержит символы размером не более 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="69eb3-345">In Outlook on the web, this method opens the specified form only if the body of the form is less than or equal to 32KB number of characters.</span></span>

<span data-ttu-id="69eb3-346">Если указанный идентификатор элемента не определяет существующую встречу, на клиентском компьютере или устройстве открывается пустая страница, и сообщение об ошибке не возвращается.</span><span class="sxs-lookup"><span data-stu-id="69eb3-346">If the specified item identifier does not identify an existing appointment, a blank pane opens on the client computer or device, and no error message will be returned.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-347">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-347">Parameters</span></span>

|<span data-ttu-id="69eb3-348">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-348">Name</span></span>| <span data-ttu-id="69eb3-349">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-349">Type</span></span>| <span data-ttu-id="69eb3-350">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-350">Description</span></span>|
|---|---|---|
|`itemId`| <span data-ttu-id="69eb3-351">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-351">String</span></span>|<span data-ttu-id="69eb3-352">Идентификатор веб-служб Exchange для существующей встречи в календаре.</span><span class="sxs-lookup"><span data-stu-id="69eb3-352">The Exchange Web Services (EWS) identifier for an existing calendar appointment.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-353">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-353">Requirements</span></span>

|<span data-ttu-id="69eb3-354">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-354">Requirement</span></span>| <span data-ttu-id="69eb3-355">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-355">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-356">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-356">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-357">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-357">1.0</span></span>|
|[<span data-ttu-id="69eb3-358">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-358">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-359">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-359">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-360">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-360">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-361">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-361">Compose or Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-362">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-362">Example</span></span>

```js
Office.context.mailbox.displayAppointmentForm(appointmentId);
```

<br>

---
---

#### <a name="displaymessageformitemid"></a><span data-ttu-id="69eb3-363">displayMessageForm(itemId)</span><span class="sxs-lookup"><span data-stu-id="69eb3-363">displayMessageForm(itemId)</span></span>

<span data-ttu-id="69eb3-364">Отображает имеющееся сообщение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-364">Displays an existing message.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-365">Этот метод не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-365">This method is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-366">Метод `displayMessageForm` открывает новое окно на компьютере или диалоговое окно на мобильном устройстве, содержащее существующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-366">The `displayMessageForm` method opens an existing message in a new window on the desktop or in a dialog box on mobile devices.</span></span>

<span data-ttu-id="69eb3-367">В Outlook в Интернете этот метод открывает указанную форму, только если текст формы содержит символы размером не более 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="69eb3-367">In Outlook on the web, this method opens the specified form only if the body of the form is less than or equal to 32 KB number of characters.</span></span>

<span data-ttu-id="69eb3-368">Если указанный идентификатор элемента не определяет существующее сообщение, окно на клиентском компьютере не открывается и сообщение об ошибке не возвращается.</span><span class="sxs-lookup"><span data-stu-id="69eb3-368">If the specified item identifier does not identify an existing message, no message will be displayed on the client computer, and no error message will be returned.</span></span>

<span data-ttu-id="69eb3-p111">Не используйте `displayMessageForm` с параметром `itemId`, который представляет собой встречу. Используйте метод `displayAppointmentForm`, чтобы отобразить сведения о существующей встрече, а метод `displayNewAppointmentForm` — для отображения формы создания встречи.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p111">Do not use the `displayMessageForm` with an `itemId` that represents an appointment. Use the `displayAppointmentForm` method to display an existing appointment, and `displayNewAppointmentForm` to display a form to create a new appointment.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-371">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-371">Parameters</span></span>

|<span data-ttu-id="69eb3-372">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-372">Name</span></span>| <span data-ttu-id="69eb3-373">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-373">Type</span></span>| <span data-ttu-id="69eb3-374">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-374">Description</span></span>|
|---|---|---|
|`itemId`| <span data-ttu-id="69eb3-375">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-375">String</span></span>|<span data-ttu-id="69eb3-376">Идентификатор веб-служб Exchange для существующего сообщения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-376">The Exchange Web Services (EWS) identifier for an existing message.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-377">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-377">Requirements</span></span>

|<span data-ttu-id="69eb3-378">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-378">Requirement</span></span>| <span data-ttu-id="69eb3-379">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-379">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-380">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-380">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-381">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-381">1.0</span></span>|
|[<span data-ttu-id="69eb3-382">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-382">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-383">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-383">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-384">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-384">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-385">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-385">Compose or Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-386">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-386">Example</span></span>

```js
Office.context.mailbox.displayMessageForm(messageId);
```

<br>

---
---

#### <a name="displaynewappointmentformparameters"></a><span data-ttu-id="69eb3-387">displayNewAppointmentForm(parameters)</span><span class="sxs-lookup"><span data-stu-id="69eb3-387">displayNewAppointmentForm(parameters)</span></span>

<span data-ttu-id="69eb3-388">Отображает форму для создания новой встречи в календаре.</span><span class="sxs-lookup"><span data-stu-id="69eb3-388">Displays a form for creating a new calendar appointment.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-389">Этот метод не поддерживается в Outlook для iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="69eb3-389">This method is not supported in Outlook on iOS or Android.</span></span>

<span data-ttu-id="69eb3-p112">Метод `displayNewAppointmentForm` открывает форму, в которой пользователь может создать встречу или собрание. Если параметры заданы, поля формы встречи автоматически заполняются их содержимым.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p112">The `displayNewAppointmentForm` method opens a form that enables the user to create a new appointment or meeting. If parameters are specified, the appointment form fields are automatically populated with the contents of the parameters.</span></span>

<span data-ttu-id="69eb3-p113">В Outlook в Интернете и на мобильных устройствах этот метод всегда отображает форму с полем участников. Если вы не укажете участников в качестве входных аргументов, метод отображает форму с кнопкой **Сохранить**. Если вы укажете участников, форма будет включать участников и кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p113">In Outlook on the web and mobile devices, this method always displays a form with an attendees field. If you do not specify any attendees as input arguments, the method displays a form with a **Save** button. If you have specified attendees, the form would include the attendees and a **Send** button.</span></span>

<span data-ttu-id="69eb3-p114">Если вы укажете участников или ресурсы с помощью параметра `requiredAttendees`, `optionalAttendees` или `resources` в клиенте Outlook с расширенными возможностями и Outlook RT, этот метод отобразит форму собрания с кнопкой **Отправить**. Если не указать получателей, этот метод отобразит форму встречи с кнопкой **Сохранить и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p114">In the Outlook rich client and Outlook RT, if you specify any attendees or resources in the `requiredAttendees`, `optionalAttendees`, or `resources` parameter, this method displays a meeting form with a **Send** button. If you don't specify any recipients, this method displays an appointment form with a **Save & Close** button.</span></span>

<span data-ttu-id="69eb3-397">Если параметры превышают указанные ограничения размера или если указано неизвестное имя параметра, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-397">If any of the parameters exceed the specified size limits, or if an unknown parameter name is specified, an exception is thrown.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-398">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-398">Parameters</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-399">Все параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="69eb3-399">All parameters are optional.</span></span>

|<span data-ttu-id="69eb3-400">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-400">Name</span></span>| <span data-ttu-id="69eb3-401">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-401">Type</span></span>| <span data-ttu-id="69eb3-402">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-402">Description</span></span>|
|---|---|---|
| `parameters` | <span data-ttu-id="69eb3-403">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-403">Object</span></span> | <span data-ttu-id="69eb3-404">Словарь параметров, описывающий новую встречу.</span><span class="sxs-lookup"><span data-stu-id="69eb3-404">A dictionary of parameters describing the new appointment.</span></span> |
| `parameters.requiredAttendees` | <span data-ttu-id="69eb3-405">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-405">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span></span> | <span data-ttu-id="69eb3-p115">Массив строк, содержащий электронные адреса, или массив, содержащий объекты `EmailAddressDetails` для каждого из обязательных участников встречи. Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p115">An array of strings containing the email addresses or an array containing an `EmailAddressDetails` object for each of the required attendees for the appointment. The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.optionalAttendees` | <span data-ttu-id="69eb3-408">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-408">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span></span> | <span data-ttu-id="69eb3-p116">Массив строк, содержащий электронные адреса, или массив, содержащий объекты `EmailAddressDetails` для каждого из необязательных участников встречи. Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p116">An array of strings containing the email addresses or an array containing an `EmailAddressDetails` object for each of the optional attendees for the appointment. The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.start` | <span data-ttu-id="69eb3-411">Date</span><span class="sxs-lookup"><span data-stu-id="69eb3-411">Date</span></span> | <span data-ttu-id="69eb3-412">Объект `Date`, указывающий дату и время начала встречи.</span><span class="sxs-lookup"><span data-stu-id="69eb3-412">A `Date` object specifying the start date and time of the appointment.</span></span> |
| `parameters.end` | <span data-ttu-id="69eb3-413">Date</span><span class="sxs-lookup"><span data-stu-id="69eb3-413">Date</span></span> | <span data-ttu-id="69eb3-414">Объект `Date`, указывающий дату и время окончания встречи.</span><span class="sxs-lookup"><span data-stu-id="69eb3-414">A `Date` object specifying the end date and time of the appointment.</span></span> |
| `parameters.location` | <span data-ttu-id="69eb3-415">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-415">String</span></span> | <span data-ttu-id="69eb3-p117">Строка со сведениями о месте встречи. Максимальное количество символов в строке — 255.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p117">A string containing the location of the appointment. The string is limited to a maximum of 255 characters.</span></span> |
| `parameters.resources` | <span data-ttu-id="69eb3-418">Array.&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-418">Array.&lt;String&gt;</span></span> | <span data-ttu-id="69eb3-p118">Массив строк, содержащий необходимые для встречи ресурсы. Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p118">An array of strings containing the resources required for the appointment. The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.subject` | <span data-ttu-id="69eb3-421">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-421">String</span></span> | <span data-ttu-id="69eb3-p119">Строка с темой встречи. Максимальное количество символов в строке — 255.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p119">A string containing the subject of the appointment. The string is limited to a maximum of 255 characters.</span></span> |
| `parameters.body` | <span data-ttu-id="69eb3-424">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-424">String</span></span> | <span data-ttu-id="69eb3-p120">Текст сообщения о встрече. Максимальный размер содержимого сообщения — 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p120">The body of the appointment. The body content is limited to a maximum size of 32 KB.</span></span> |

##### <a name="requirements"></a><span data-ttu-id="69eb3-427">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-427">Requirements</span></span>

|<span data-ttu-id="69eb3-428">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-428">Requirement</span></span>| <span data-ttu-id="69eb3-429">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-429">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-430">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-430">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-431">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-431">1.0</span></span>|
|[<span data-ttu-id="69eb3-432">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-432">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-433">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-433">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-434">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-434">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-435">Чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-435">Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-436">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-436">Example</span></span>

```js
var start = new Date();
var end = new Date();
end.setHours(start.getHours() + 1);

Office.context.mailbox.displayNewAppointmentForm(
  {
    requiredAttendees: ['bob@contoso.com'],
    optionalAttendees: ['sam@contoso.com'],
    start: start,
    end: end,
    location: 'Home',
    resources: ['projector@contoso.com'],
    subject: 'meeting',
    body: 'Hello World!'
  });
```

<br>

---
---

#### <a name="displaynewmessageformparameters"></a><span data-ttu-id="69eb3-437">Дисплайневмессажеформ (Parameters)</span><span class="sxs-lookup"><span data-stu-id="69eb3-437">displayNewMessageForm(parameters)</span></span>

<span data-ttu-id="69eb3-438">Отображает форму для создания нового сообщения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-438">Displays a form for creating a new message.</span></span>

<span data-ttu-id="69eb3-439">`displayNewMessageForm` Метод открывает форму, которая позволяет пользователю создать новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-439">The `displayNewMessageForm` method opens a form that enables the user to create a new message.</span></span> <span data-ttu-id="69eb3-440">Если указаны параметры, поля формы сообщения автоматически заполняются содержимым параметров.</span><span class="sxs-lookup"><span data-stu-id="69eb3-440">If parameters are specified, the message form fields are automatically populated with the contents of the parameters.</span></span>

<span data-ttu-id="69eb3-441">Если параметры превышают указанные ограничения размера или если указано неизвестное имя параметра, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-441">If any of the parameters exceed the specified size limits, or if an unknown parameter name is specified, an exception is thrown.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-442">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-442">Parameters</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-443">Все параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="69eb3-443">All parameters are optional.</span></span>

|<span data-ttu-id="69eb3-444">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-444">Name</span></span>| <span data-ttu-id="69eb3-445">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-445">Type</span></span>| <span data-ttu-id="69eb3-446">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-446">Description</span></span>|
|---|---|---|
| `parameters` | <span data-ttu-id="69eb3-447">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-447">Object</span></span> | <span data-ttu-id="69eb3-448">Словарь параметров, описывающих новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="69eb3-448">A dictionary of parameters describing the new message.</span></span> |
| `parameters.toRecipients` | <span data-ttu-id="69eb3-449">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-449">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span></span> | <span data-ttu-id="69eb3-450">Массив строк, содержащий адреса электронной почты или массив, содержащий `EmailAddressDetails` объект для каждого из получателей в строке "Кому".</span><span class="sxs-lookup"><span data-stu-id="69eb3-450">An array of strings containing the email addresses or an array containing an `EmailAddressDetails` object for each of the recipients on the To line.</span></span> <span data-ttu-id="69eb3-451">Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-451">The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.ccRecipients` | <span data-ttu-id="69eb3-452">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-452">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span></span> | <span data-ttu-id="69eb3-453">Массив строк, содержащий адреса электронной почты или массив, содержащий `EmailAddressDetails` объект для каждого получателя в строке "копия".</span><span class="sxs-lookup"><span data-stu-id="69eb3-453">An array of strings containing the email addresses or an array containing an `EmailAddressDetails` object for each of the recipients on the Cc line.</span></span> <span data-ttu-id="69eb3-454">Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-454">The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.bccRecipients` | <span data-ttu-id="69eb3-455">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-455">Array.&lt;String&gt; &#124; Array.&lt;[EmailAddressDetails](/javascript/api/outlook/office.emailaddressdetails?view=outlook-js-1.8)&gt;</span></span> | <span data-ttu-id="69eb3-456">Массив строк, содержащий адреса электронной почты или массив, содержащий `EmailAddressDetails` объект для каждого из получателей, указанных в строке "СК".</span><span class="sxs-lookup"><span data-stu-id="69eb3-456">An array of strings containing the email addresses or an array containing an `EmailAddressDetails` object for each of the recipients on the Bcc line.</span></span> <span data-ttu-id="69eb3-457">Массив может включать не более 100 записей.</span><span class="sxs-lookup"><span data-stu-id="69eb3-457">The array is limited to a maximum of 100 entries.</span></span> |
| `parameters.subject` | <span data-ttu-id="69eb3-458">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-458">String</span></span> | <span data-ttu-id="69eb3-459">Строка, содержащая тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-459">A string containing the subject of the message.</span></span> <span data-ttu-id="69eb3-460">Максимальное количество символов в строке — 255.</span><span class="sxs-lookup"><span data-stu-id="69eb3-460">The string is limited to a maximum of 255 characters.</span></span> |
| `parameters.htmlBody` | <span data-ttu-id="69eb3-461">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-461">String</span></span> | <span data-ttu-id="69eb3-462">Текст сообщения в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="69eb3-462">The HTML body of the message.</span></span> <span data-ttu-id="69eb3-463">Максимальный размер содержимого сообщения — 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="69eb3-463">The body content is limited to a maximum size of 32 KB.</span></span> |
| `parameters.attachments` | <span data-ttu-id="69eb3-464">Array.&lt;Object&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-464">Array.&lt;Object&gt;</span></span> | <span data-ttu-id="69eb3-465">Массив объектов JSON, представляющих собой вложенные файлы или элементы.</span><span class="sxs-lookup"><span data-stu-id="69eb3-465">An array of JSON objects that are either file or item attachments.</span></span> |
| `parameters.attachments.type` | <span data-ttu-id="69eb3-466">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-466">String</span></span> | <span data-ttu-id="69eb3-p127">Указывает тип вложения. Допустимые значения: `file` для вложенного файла и `item` для вложенного элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p127">Indicates the type of attachment. Must be `file` for a file attachment or `item` for an item attachment.</span></span> |
| `parameters.attachments.name` | <span data-ttu-id="69eb3-469">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-469">String</span></span> | <span data-ttu-id="69eb3-470">Строка, содержащая имя вложения, длиной до 255 символов.</span><span class="sxs-lookup"><span data-stu-id="69eb3-470">A string that contains the name of the attachment, up to 255 characters in length.</span></span>|
| `parameters.attachments.url` | <span data-ttu-id="69eb3-471">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-471">String</span></span> | <span data-ttu-id="69eb3-p128">Используется, только если свойству `type` задано значение `file`. URI расположения файла.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p128">Only used if `type` is set to `file`. The URI of the location for the file.</span></span> |
| `parameters.attachments.isInline` | <span data-ttu-id="69eb3-474">Логический</span><span class="sxs-lookup"><span data-stu-id="69eb3-474">Boolean</span></span> | <span data-ttu-id="69eb3-p129">Используется, только если свойству `type` задано значение `file`. Значение `true` указывает на то, что вложение будет встроено в текст сообщения и не должно отображаться в списке вложений.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p129">Only used if `type` is set to `file`. If `true`, indicates that the attachment will be shown inline in the message body, and should not be displayed in the attachment list.</span></span> |
| `parameters.attachments.itemId` | <span data-ttu-id="69eb3-477">Строка</span><span class="sxs-lookup"><span data-stu-id="69eb3-477">String</span></span> | <span data-ttu-id="69eb3-478">Используется, только если свойству `type` присвоено значение `item`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-478">Only used if `type` is set to `item`.</span></span> <span data-ttu-id="69eb3-479">Идентификатор элемента EWS существующего сообщения электронной почты, которое необходимо присоединить к новому сообщению.</span><span class="sxs-lookup"><span data-stu-id="69eb3-479">The EWS item id of the existing e-mail you want to attach to the new message.</span></span> <span data-ttu-id="69eb3-480">Это строка длиной до 100 символов.</span><span class="sxs-lookup"><span data-stu-id="69eb3-480">This is a string up to 100 characters.</span></span> |


##### <a name="requirements"></a><span data-ttu-id="69eb3-481">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-481">Requirements</span></span>

|<span data-ttu-id="69eb3-482">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-482">Requirement</span></span>| <span data-ttu-id="69eb3-483">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-483">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-484">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-484">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-485">1.6</span><span class="sxs-lookup"><span data-stu-id="69eb3-485">1.6</span></span> |
|[<span data-ttu-id="69eb3-486">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-486">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-487">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-487">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-488">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-488">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-489">Чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-489">Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-490">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-490">Example</span></span>

```js
Office.context.mailbox.displayNewMessageForm(
  {
    // Copy the To line from current item.
    toRecipients: Office.context.mailbox.item.to,
    ccRecipients: ['sam@contoso.com'],
    subject: 'Outlook add-ins are cool!',
    htmlBody: 'Hello <b>World</b>!<br/><img src="cid:image.png"></i>',
    attachments: [
      {
        type: 'file',
        name: 'image.png',
        url: 'http://contoso.com/image.png',
        isInline: true
      }
    ]
  });
```

<br>

---
---

#### <a name="getcallbacktokenasyncoptions-callback"></a><span data-ttu-id="69eb3-491">getCallbackTokenAsync([options], callback)</span><span class="sxs-lookup"><span data-stu-id="69eb3-491">getCallbackTokenAsync([options], callback)</span></span>

<span data-ttu-id="69eb3-492">Возвращает строку, содержащую маркер, который используется для вызова интерфейсов REST API или веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="69eb3-492">Gets a string that contains a token used to call REST APIs or Exchange Web Services.</span></span>

<span data-ttu-id="69eb3-p131">Метод `getCallbackTokenAsync` совершает асинхронный вызов, чтобы получить непрозрачный маркер с сервера Exchange Server, на котором размещен почтовый ящик пользователя. Время существования маркера обратного вызова составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p131">The `getCallbackTokenAsync` method makes an asynchronous call to get an opaque token from the Exchange Server that hosts the user's mailbox. The lifetime of the callback token is 5 minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-495">Рекомендуем сделать так, чтобы по мере возможности надстройки использовали интерфейсы REST API, а не веб-службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="69eb3-495">It is recommended that add-ins use the REST APIs instead of Exchange Web Services whenever possible.</span></span>

<span data-ttu-id="69eb3-496">Для вызова метода `getCallbackTokenAsync` в режиме чтения требуется минимальный уровень разрешения **ReadItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-496">Calling the `getCallbackTokenAsync` method in read mode requires a minimum permission level of **ReadItem**.</span></span>

<span data-ttu-id="69eb3-497">Для вызова `getCallbackTokenAsync` в режиме создания сообщения требуется сохранить элемент.</span><span class="sxs-lookup"><span data-stu-id="69eb3-497">Calling `getCallbackTokenAsync` in compose mode requires you to have saved the item.</span></span> <span data-ttu-id="69eb3-498">Для метода [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) требуется минимальный уровень разрешения **ReadWriteItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-498">The [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) method requires a minimum permission level of **ReadWriteItem**.</span></span>

<span data-ttu-id="69eb3-499">**Маркеры REST**</span><span class="sxs-lookup"><span data-stu-id="69eb3-499">**REST Tokens**</span></span>

<span data-ttu-id="69eb3-p133">Если запрашивается маркер REST (`options.isRest = true`), полученный маркер не подойдет для проверки подлинности при вызовах веб-служб Exchange. Область действия маркера будет ограничена доступом только для чтения к текущему элементу и его вложениям, если в манифесте надстройки не указано разрешение [`ReadWriteMailbox`](/outlook/add-ins/understanding-outlook-add-in-permissions#readwritemailbox-permission). Если указано разрешение `ReadWriteMailbox`, полученный маркер предоставит доступ на чтение и запись к почте, календарю и контактам, включая возможность отправки почты.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p133">When a REST token is requested (`options.isRest = true`), the resulting token will not work to authenticate Exchange Web Services calls. The token will be limited in scope to read-only access to the current item and its attachments, unless the add-in has specified the [`ReadWriteMailbox`](/outlook/add-ins/understanding-outlook-add-in-permissions#readwritemailbox-permission) permission in its manifest. If the `ReadWriteMailbox` permission is specified, the resulting token will grant read/write access to mail, calendar, and contacts, including the ability to send mail.</span></span>

<span data-ttu-id="69eb3-503">С помощью свойства `restUrl` надстройка должна определить правильный URL-адрес для вызовов REST API.</span><span class="sxs-lookup"><span data-stu-id="69eb3-503">The add-in should use the `restUrl` property to determine the correct URL to use when making REST API calls.</span></span>

<span data-ttu-id="69eb3-504">**Маркеры EWS**</span><span class="sxs-lookup"><span data-stu-id="69eb3-504">**EWS Tokens**</span></span>

<span data-ttu-id="69eb3-p134">Если запрашивается маркер EWS (`options.isRest = false`), полученный маркер не подойдет для проверки подлинности при вызовах REST API. Область действия маркера будет ограничена доступом к текущему элементу.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p134">When an EWS token is requested (`options.isRest = false`), the resulting token will not work to authenticate REST API calls. The token will be limited in scope to accessing the current item.</span></span>

<span data-ttu-id="69eb3-507">С помощью свойства `ewsUrl` надстройка должна определить правильный URL-адрес для вызовов EWS.</span><span class="sxs-lookup"><span data-stu-id="69eb3-507">The add-in should use the `ewsUrl` property to determine the correct URL to use when making EWS calls.</span></span>

<span data-ttu-id="69eb3-508">Вы можете передать сторонней системе маркер и идентификатор вложения или элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-508">You can pass both the token and either an attachment identifier or item identifier to a third-party system.</span></span> <span data-ttu-id="69eb3-509">Третья система использует маркер в качестве маркера авторизации носителя, чтобы вызвать операцию [GetAttachment](/exchange/client-developer/web-service-reference/getattachment-operation) [или GetItem](/exchange/client-developer/web-service-reference/getitem-operation) веб-служб Exchange (EWS) для получения вложения или элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-509">The third-party system uses the token as a bearer authorization token to call the Exchange Web Services (EWS) [GetAttachment](/exchange/client-developer/web-service-reference/getattachment-operation) operation or [GetItem](/exchange/client-developer/web-service-reference/getitem-operation) operation to retrieve an attachment or item.</span></span> <span data-ttu-id="69eb3-510">Например, вы можете создать удаленную службу, чтобы [получить вложения из выбранного элемента](/outlook/add-ins/get-attachments-of-an-outlook-item).</span><span class="sxs-lookup"><span data-stu-id="69eb3-510">For example, you can create a remote service to [get attachments from the selected item](/outlook/add-ins/get-attachments-of-an-outlook-item).</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-511">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-511">Parameters</span></span>

|<span data-ttu-id="69eb3-512">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-512">Name</span></span>| <span data-ttu-id="69eb3-513">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-513">Type</span></span>| <span data-ttu-id="69eb3-514">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-514">Attributes</span></span>| <span data-ttu-id="69eb3-515">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-515">Description</span></span>|
|---|---|---|---|
| `options` | <span data-ttu-id="69eb3-516">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-516">Object</span></span> | <span data-ttu-id="69eb3-517">&lt;Необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-517">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-518">Объектный литерал, содержащий одно или несколько из указанных ниже свойств.</span><span class="sxs-lookup"><span data-stu-id="69eb3-518">An object literal that contains one or more of the following properties.</span></span> |
| `options.isRest` | <span data-ttu-id="69eb3-519">Boolean</span><span class="sxs-lookup"><span data-stu-id="69eb3-519">Boolean</span></span> |  <span data-ttu-id="69eb3-520">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-520">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-p136">Определяет, будет ли предоставленный маркер использоваться для интерфейсов REST API Outlook или веб-служб Exchange. Значение по умолчанию: `false`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p136">Determines if the token provided will be used for the Outlook REST APIs or Exchange Web Services. Default value is `false`.</span></span> |
| `options.asyncContext` | <span data-ttu-id="69eb3-523">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-523">Object</span></span> |  <span data-ttu-id="69eb3-524">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-524">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-525">Данные о состоянии, передаваемые в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="69eb3-525">Any state data that is passed to the asynchronous method.</span></span> |
|`callback`| <span data-ttu-id="69eb3-526">функция</span><span class="sxs-lookup"><span data-stu-id="69eb3-526">function</span></span>||<span data-ttu-id="69eb3-527">После выполнения метода функция, переданная в параметре `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-527">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span><br/><br/><span data-ttu-id="69eb3-528">Маркер указывается в виде строки в свойстве `asyncResult.value`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-528">The token is provided as a string in the `asyncResult.value` property.</span></span><br><br><span data-ttu-id="69eb3-529">При наличии ошибки свойства `asyncResult.error` и `asyncResult.diagnostics` могут предоставлять дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-529">If there was an error, the `asyncResult.error` and `asyncResult.diagnostics` properties may provide additional information.</span></span>|

##### <a name="errors"></a><span data-ttu-id="69eb3-530">Ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-530">Errors</span></span>

|<span data-ttu-id="69eb3-531">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-531">Error code</span></span>|<span data-ttu-id="69eb3-532">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-532">Description</span></span>|
|------------|-------------|
|`HTTPRequestFailure`|<span data-ttu-id="69eb3-533">Не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="69eb3-533">The request has failed.</span></span> <span data-ttu-id="69eb3-534">Просмотрите объект диагностики для кода ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="69eb3-534">Please look at the diagnostics object for the HTTP error code.</span></span>|
|`InternalServerError`|<span data-ttu-id="69eb3-535">Сервер Exchange Server вернул ошибку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-535">The Exchange server returned an error.</span></span> <span data-ttu-id="69eb3-536">Для получения дополнительных сведений просмотрите объект диагностики.</span><span class="sxs-lookup"><span data-stu-id="69eb3-536">Please look at the diagnostics object for more information.</span></span>|
|`NetworkError`|<span data-ttu-id="69eb3-537">Пользователь отключен от сети.</span><span class="sxs-lookup"><span data-stu-id="69eb3-537">The user is no longer connected to the network.</span></span> <span data-ttu-id="69eb3-538">Проверьте сетевое подключение и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-538">Please check your network connection and try again.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-539">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-539">Requirements</span></span>

|<span data-ttu-id="69eb3-540">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-540">Requirement</span></span>| <span data-ttu-id="69eb3-541">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-541">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-542">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-542">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-543">1.5</span><span class="sxs-lookup"><span data-stu-id="69eb3-543">1.5</span></span> |
|[<span data-ttu-id="69eb3-544">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-544">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-545">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-545">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-546">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-546">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-547">Создание и чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-547">Compose and read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-548">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-548">Example</span></span>

```js
function getCallbackToken() {
  var options = {
    isRest: true,
    asyncContext: { message: 'Hello World!' }
  };

  Office.context.mailbox.getCallbackTokenAsync(options, cb);
}

function cb(asyncResult) {
  var token = asyncResult.value;
}
```

<br>

---
---

#### <a name="getcallbacktokenasynccallback-usercontext"></a><span data-ttu-id="69eb3-549">getCallbackTokenAsync(callback, [userContext])</span><span class="sxs-lookup"><span data-stu-id="69eb3-549">getCallbackTokenAsync(callback, [userContext])</span></span>

<span data-ttu-id="69eb3-550">Получает строку, содержащую маркер, используемый для получения вложения или элемента с Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="69eb3-550">Gets a string that contains a token used to get an attachment or item from an Exchange Server.</span></span>

<span data-ttu-id="69eb3-p140">Метод `getCallbackTokenAsync` совершает асинхронный вызов, чтобы получить непрозрачный маркер с сервера Exchange Server, на котором размещен почтовый ящик пользователя. Время существования маркера обратного вызова составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="69eb3-p140">The `getCallbackTokenAsync` method makes an asynchronous call to get an opaque token from the Exchange Server that hosts the user's mailbox. The lifetime of the callback token is 5 minutes.</span></span>

<span data-ttu-id="69eb3-553">Вы можете передать сторонней системе маркер и идентификатор вложения или элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-553">You can pass both the token and either an attachment identifier or item identifier to a third-party system.</span></span> <span data-ttu-id="69eb3-554">Сторонняя система использует этот маркер как маркер авторизации, чтобы вызвать операцию [GetAttachment](/exchange/client-developer/web-service-reference/getattachment-operation) или [GetItem](/exchange/client-developer/web-service-reference/getitem-operation) веб-служб Exchange для возврата вложения или элемента.</span><span class="sxs-lookup"><span data-stu-id="69eb3-554">The third-party system uses the token as a bearer authorization token to call the Exchange Web Services (EWS) [GetAttachment](/exchange/client-developer/web-service-reference/getattachment-operation) operation or [GetItem](/exchange/client-developer/web-service-reference/getitem-operation) operation to return an attachment or item.</span></span> <span data-ttu-id="69eb3-555">Например, вы можете создать удаленную службу, чтобы [получить вложения из выбранного элемента](/outlook/add-ins/get-attachments-of-an-outlook-item).</span><span class="sxs-lookup"><span data-stu-id="69eb3-555">For example, you can create a remote service to [get attachments from the selected item](/outlook/add-ins/get-attachments-of-an-outlook-item).</span></span>

<span data-ttu-id="69eb3-556">Для вызова метода `getCallbackTokenAsync` в режиме чтения требуется минимальный уровень разрешения **ReadItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-556">Calling the `getCallbackTokenAsync` method in read mode requires a minimum permission level of **ReadItem**.</span></span>

<span data-ttu-id="69eb3-557">Для вызова `getCallbackTokenAsync` в режиме создания сообщения требуется сохранить элемент.</span><span class="sxs-lookup"><span data-stu-id="69eb3-557">Calling `getCallbackTokenAsync` in compose mode requires you to have saved the item.</span></span> <span data-ttu-id="69eb3-558">Для метода [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) требуется минимальный уровень разрешения **ReadWriteItem**.</span><span class="sxs-lookup"><span data-stu-id="69eb3-558">The [`saveAsync`](Office.context.mailbox.item.md#saveasyncoptions-callback) method requires a minimum permission level of **ReadWriteItem**.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-559">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-559">Parameters</span></span>

|<span data-ttu-id="69eb3-560">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-560">Name</span></span>| <span data-ttu-id="69eb3-561">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-561">Type</span></span>| <span data-ttu-id="69eb3-562">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-562">Attributes</span></span>| <span data-ttu-id="69eb3-563">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-563">Description</span></span>|
|---|---|---|---|
|`callback`| <span data-ttu-id="69eb3-564">функция</span><span class="sxs-lookup"><span data-stu-id="69eb3-564">function</span></span>||<span data-ttu-id="69eb3-565">После выполнения метода функция, переданная в параметре `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-565">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span><br/><br/><span data-ttu-id="69eb3-566">Маркер указывается в виде строки в свойстве `asyncResult.value`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-566">The token is provided as a string in the `asyncResult.value` property.</span></span><br><br><span data-ttu-id="69eb3-567">При наличии ошибки свойства `asyncResult.error` и `asyncResult.diagnostics` могут предоставлять дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-567">If there was an error, the `asyncResult.error` and `asyncResult.diagnostics` properties may provide additional information.</span></span>|
|`userContext`| <span data-ttu-id="69eb3-568">Объект</span><span class="sxs-lookup"><span data-stu-id="69eb3-568">Object</span></span>| <span data-ttu-id="69eb3-569">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-569">&lt;optional&gt;</span></span>|<span data-ttu-id="69eb3-570">Данные о состоянии, передаваемые в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="69eb3-570">Any state data that is passed to the asynchronous method.</span></span>|

##### <a name="errors"></a><span data-ttu-id="69eb3-571">Ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-571">Errors</span></span>

|<span data-ttu-id="69eb3-572">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-572">Error code</span></span>|<span data-ttu-id="69eb3-573">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-573">Description</span></span>|
|------------|-------------|
|`HTTPRequestFailure`|<span data-ttu-id="69eb3-574">Не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="69eb3-574">The request has failed.</span></span> <span data-ttu-id="69eb3-575">Просмотрите объект диагностики для кода ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="69eb3-575">Please look at the diagnostics object for the HTTP error code.</span></span>|
|`InternalServerError`|<span data-ttu-id="69eb3-576">Сервер Exchange Server вернул ошибку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-576">The Exchange server returned an error.</span></span> <span data-ttu-id="69eb3-577">Для получения дополнительных сведений просмотрите объект диагностики.</span><span class="sxs-lookup"><span data-stu-id="69eb3-577">Please look at the diagnostics object for more information.</span></span>|
|`NetworkError`|<span data-ttu-id="69eb3-578">Пользователь отключен от сети.</span><span class="sxs-lookup"><span data-stu-id="69eb3-578">The user is no longer connected to the network.</span></span> <span data-ttu-id="69eb3-579">Проверьте сетевое подключение и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-579">Please check your network connection and try again.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-580">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-580">Requirements</span></span>

|<span data-ttu-id="69eb3-581">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-581">Requirement</span></span>|||
|---|---|---|
|[<span data-ttu-id="69eb3-582">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-582">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-583">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-583">1.0</span></span> | <span data-ttu-id="69eb3-584">1.3</span><span class="sxs-lookup"><span data-stu-id="69eb3-584">1.3</span></span> |
|[<span data-ttu-id="69eb3-585">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-585">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-586">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-586">ReadItem</span></span> | <span data-ttu-id="69eb3-587">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-587">ReadItem</span></span> |
|[<span data-ttu-id="69eb3-588">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-588">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-589">Чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-589">Read</span></span> | <span data-ttu-id="69eb3-590">Создание</span><span class="sxs-lookup"><span data-stu-id="69eb3-590">Compose</span></span> |

##### <a name="example"></a><span data-ttu-id="69eb3-591">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-591">Example</span></span>

```js
function getCallbackToken() {
  Office.context.mailbox.getCallbackTokenAsync(cb);
}

function cb(asyncResult) {
  var token = asyncResult.value;
}
```

<br>

---
---

#### <a name="getuseridentitytokenasynccallback-usercontext"></a><span data-ttu-id="69eb3-592">getUserIdentityTokenAsync(callback, [userContext])</span><span class="sxs-lookup"><span data-stu-id="69eb3-592">getUserIdentityTokenAsync(callback, [userContext])</span></span>

<span data-ttu-id="69eb3-593">Получает маркер, идентифицирующий пользователя и надстройку Office.</span><span class="sxs-lookup"><span data-stu-id="69eb3-593">Gets a token identifying the user and the Office Add-in.</span></span>

<span data-ttu-id="69eb3-594">Метод `getUserIdentityTokenAsync` возвращает маркер, который можно использовать для идентификации, а также [проверки подлинности надстройки и пользователя в сторонней системе](/outlook/add-ins/authentication).</span><span class="sxs-lookup"><span data-stu-id="69eb3-594">The `getUserIdentityTokenAsync` method returns a token that you can use to identify and [authenticate the add-in and user with a third-party system](/outlook/add-ins/authentication).</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-595">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-595">Parameters</span></span>

|<span data-ttu-id="69eb3-596">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-596">Name</span></span>| <span data-ttu-id="69eb3-597">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-597">Type</span></span>| <span data-ttu-id="69eb3-598">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-598">Attributes</span></span>| <span data-ttu-id="69eb3-599">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-599">Description</span></span>|
|---|---|---|---|
|`callback`| <span data-ttu-id="69eb3-600">функция</span><span class="sxs-lookup"><span data-stu-id="69eb3-600">function</span></span>||<span data-ttu-id="69eb3-601">После выполнения метода функция, переданная в параметре `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-601">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span><br/><br/><span data-ttu-id="69eb3-602">Маркер указывается в виде строки в свойстве `asyncResult.value`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-602">The token is provided as a string in the `asyncResult.value` property.</span></span><br><br><span data-ttu-id="69eb3-603">При наличии ошибки свойства `asyncResult.error` и `asyncResult.diagnostics` могут предоставлять дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="69eb3-603">If there was an error, the `asyncResult.error` and `asyncResult.diagnostics` properties may provide additional information.</span></span>|
|`userContext`| <span data-ttu-id="69eb3-604">Объект</span><span class="sxs-lookup"><span data-stu-id="69eb3-604">Object</span></span>| <span data-ttu-id="69eb3-605">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-605">&lt;optional&gt;</span></span>|<span data-ttu-id="69eb3-606">Данные о состоянии, передаваемые в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="69eb3-606">Any state data that is passed to the asynchronous method.</span></span>|

##### <a name="errors"></a><span data-ttu-id="69eb3-607">Ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-607">Errors</span></span>

|<span data-ttu-id="69eb3-608">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="69eb3-608">Error code</span></span>|<span data-ttu-id="69eb3-609">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-609">Description</span></span>|
|------------|-------------|
|`HTTPRequestFailure`|<span data-ttu-id="69eb3-610">Не удалось выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="69eb3-610">The request has failed.</span></span> <span data-ttu-id="69eb3-611">Просмотрите объект диагностики для кода ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="69eb3-611">Please look at the diagnostics object for the HTTP error code.</span></span>|
|`InternalServerError`|<span data-ttu-id="69eb3-612">Сервер Exchange Server вернул ошибку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-612">The Exchange server returned an error.</span></span> <span data-ttu-id="69eb3-613">Для получения дополнительных сведений просмотрите объект диагностики.</span><span class="sxs-lookup"><span data-stu-id="69eb3-613">Please look at the diagnostics object for more information.</span></span>|
|`NetworkError`|<span data-ttu-id="69eb3-614">Пользователь отключен от сети.</span><span class="sxs-lookup"><span data-stu-id="69eb3-614">The user is no longer connected to the network.</span></span> <span data-ttu-id="69eb3-615">Проверьте сетевое подключение и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="69eb3-615">Please check your network connection and try again.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-616">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-616">Requirements</span></span>

|<span data-ttu-id="69eb3-617">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-617">Requirement</span></span>| <span data-ttu-id="69eb3-618">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-618">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-619">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-619">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-620">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-620">1.0</span></span>|
|[<span data-ttu-id="69eb3-621">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-621">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-622">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-622">ReadItem</span></span>|
|[<span data-ttu-id="69eb3-623">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-623">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-624">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-624">Compose or Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-625">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-625">Example</span></span>

```js
function getIdentityToken() {
  Office.context.mailbox.getUserIdentityTokenAsync(cb);
}

function cb(asyncResult) {
  var token = asyncResult.value;
}
```

<br>

---
---

#### <a name="makeewsrequestasyncdata-callback-usercontext"></a><span data-ttu-id="69eb3-626">makeEwsRequestAsync(data, callback, [userContext])</span><span class="sxs-lookup"><span data-stu-id="69eb3-626">makeEwsRequestAsync(data, callback, [userContext])</span></span>

<span data-ttu-id="69eb3-627">Выполняет асинхронный запрос для веб-служб Exchange (EWS) на сервере Exchange Server, на котором размещен почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="69eb3-627">Makes an asynchronous request to an Exchange Web Services (EWS) service on the Exchange server that hosts the user’s mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-628">Этот метод не поддерживается в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="69eb3-628">This method is not supported in the following scenarios.</span></span>
> - <span data-ttu-id="69eb3-629">В Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="69eb3-629">In Outlook on iOS or Android</span></span>
> - <span data-ttu-id="69eb3-630">Если надстройка загружается в почтовый ящик Gmail.</span><span class="sxs-lookup"><span data-stu-id="69eb3-630">When the add-in is loaded in a Gmail mailbox</span></span>
> 
> <span data-ttu-id="69eb3-631">В таких случаях надстройка должна [использовать REST API](/outlook/add-ins/use-rest-api) для доступа к почтовому ящику пользователя.</span><span class="sxs-lookup"><span data-stu-id="69eb3-631">In these cases, add-ins should [use REST APIs](/outlook/add-ins/use-rest-api) to access the user's mailbox instead.</span></span>

<span data-ttu-id="69eb3-632">Метод `makeEwsRequestAsync` отправляет запрос EWS от имени надстройки в Exchange.</span><span class="sxs-lookup"><span data-stu-id="69eb3-632">The `makeEwsRequestAsync` method sends an EWS request on behalf of the add-in to Exchange.</span></span> <span data-ttu-id="69eb3-633">Список поддерживаемых операций EWS см. в статье [Вызов веб-служб из надстройки Outlook](/outlook/add-ins/web-services#ews-operations-that-add-ins-support).</span><span class="sxs-lookup"><span data-stu-id="69eb3-633">See [Call web services from an Outlook add-in](/outlook/add-ins/web-services#ews-operations-that-add-ins-support) for a list of the supported EWS operations.</span></span>

<span data-ttu-id="69eb3-634">С помощью метода `makeEwsRequestAsync` невозможно запрашивать элементы, связанные с папкой.</span><span class="sxs-lookup"><span data-stu-id="69eb3-634">You cannot request Folder Associated Items with the `makeEwsRequestAsync` method.</span></span>

<span data-ttu-id="69eb3-635">В запросе XML должна быть указана кодировка UTF-8.</span><span class="sxs-lookup"><span data-stu-id="69eb3-635">The XML request must specify UTF-8 encoding.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
```

<span data-ttu-id="69eb3-p150">У вашей надстройки должно быть разрешение **ReadWriteMailbox** для использования метода `makeEwsRequestAsync`. Сведения об использовании разрешения **ReadWriteMailbox** и операций EWS, которые можно вызывать с помощью метода `makeEwsRequestAsync`, см. в статье [Указание разрешений для доступа почтовой надстройки к почтовому ящику пользователя](/outlook/add-ins/understanding-outlook-add-in-permissions).</span><span class="sxs-lookup"><span data-stu-id="69eb3-p150">Your add-in must have the **ReadWriteMailbox** permission to use the `makeEwsRequestAsync` method. For information about using the **ReadWriteMailbox** permission and the EWS operations that you can call with the `makeEwsRequestAsync` method, see [Specify permissions for mail add-in access to the user's mailbox](/outlook/add-ins/understanding-outlook-add-in-permissions).</span></span>

> [!NOTE]
> <span data-ttu-id="69eb3-638">Администратор сервера должен установить значение true для параметра `OAuthAuthentication` в каталоге сервера клиентского доступа EWS, чтобы метод `makeEwsRequestAsync` мог выполнять запросы EWS.</span><span class="sxs-lookup"><span data-stu-id="69eb3-638">The server administrator must set `OAuthAuthentication` to true on the Client Access Server EWS directory to enable the `makeEwsRequestAsync` method to make EWS requests.</span></span>

##### <a name="version-differences"></a><span data-ttu-id="69eb3-639">Различия версий</span><span class="sxs-lookup"><span data-stu-id="69eb3-639">Version differences</span></span>

<span data-ttu-id="69eb3-640">Если вы используете метод `makeEwsRequestAsync` в почтовых приложениях, которые выполняются в Outlook версии более ранней, чем 15.0.4535.1004, указывайте кодировку `ISO-8859-1`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-640">When you use the `makeEwsRequestAsync` method in mail apps running in Outlook versions earlier than version 15.0.4535.1004, you should set the encoding value to `ISO-8859-1`.</span></span>

```xml
<?xml version="1.0" encoding="iso-8859-1"?>
```

<span data-ttu-id="69eb3-641">Значение кодировки не нужно указывать, если почтовое приложение выполняется в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="69eb3-641">You do not need to set the encoding value when your mail app is running in Outlook on the web.</span></span> <span data-ttu-id="69eb3-642">Вы можете определить, работает ли почтовое приложение в Outlook в Интернете или на настольном клиенте с помощью свойства Mailbox. Diagnostics. hostName.</span><span class="sxs-lookup"><span data-stu-id="69eb3-642">You can determine whether your mail app is running in Outlook on the web or a desktop client by using the mailbox.diagnostics.hostName property.</span></span> <span data-ttu-id="69eb3-643">Используемую версию Outlook можно определить с помощью свойства mailbox.diagnostics.hostVersion.</span><span class="sxs-lookup"><span data-stu-id="69eb3-643">You can determine what version of Outlook is running by using the mailbox.diagnostics.hostVersion property.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-644">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-644">Parameters</span></span>

|<span data-ttu-id="69eb3-645">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-645">Name</span></span>| <span data-ttu-id="69eb3-646">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-646">Type</span></span>| <span data-ttu-id="69eb3-647">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-647">Attributes</span></span>| <span data-ttu-id="69eb3-648">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-648">Description</span></span>|
|---|---|---|---|
|`data`| <span data-ttu-id="69eb3-649">String</span><span class="sxs-lookup"><span data-stu-id="69eb3-649">String</span></span>||<span data-ttu-id="69eb3-650">Запрос EWS.</span><span class="sxs-lookup"><span data-stu-id="69eb3-650">The EWS request.</span></span>|
|`callback`| <span data-ttu-id="69eb3-651">function</span><span class="sxs-lookup"><span data-stu-id="69eb3-651">function</span></span>||<span data-ttu-id="69eb3-652">После выполнения метода функция, переданная в параметре `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-652">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span><br/><br/><span data-ttu-id="69eb3-653">Результат XML вызова EWS указывается в виде строки в свойстве `asyncResult.value`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-653">The XML result of the EWS call is provided as a string in the `asyncResult.value` property.</span></span> <span data-ttu-id="69eb3-654">Если размер результата превышает 1 МБ, возвращается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="69eb3-654">If the result exceeds 1 MB in size, an error message is returned instead.</span></span>|
|`userContext`| <span data-ttu-id="69eb3-655">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-655">Object</span></span>| <span data-ttu-id="69eb3-656">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-656">&lt;optional&gt;</span></span>|<span data-ttu-id="69eb3-657">Данные о состоянии, передаваемые в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="69eb3-657">Any state data that is passed to the asynchronous method.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-658">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-658">Requirements</span></span>

|<span data-ttu-id="69eb3-659">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-659">Requirement</span></span>| <span data-ttu-id="69eb3-660">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-660">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-661">Версия минимального набора требований к почтовому ящику</span><span class="sxs-lookup"><span data-stu-id="69eb3-661">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-662">1.0</span><span class="sxs-lookup"><span data-stu-id="69eb3-662">1.0</span></span>|
|[<span data-ttu-id="69eb3-663">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-663">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-664">ReadWriteMailbox</span><span class="sxs-lookup"><span data-stu-id="69eb3-664">ReadWriteMailbox</span></span>|
|[<span data-ttu-id="69eb3-665">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-665">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-666">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-666">Compose or Read</span></span>|

##### <a name="example"></a><span data-ttu-id="69eb3-667">Пример</span><span class="sxs-lookup"><span data-stu-id="69eb3-667">Example</span></span>

<span data-ttu-id="69eb3-668">В приведенном ниже примере вызывается `makeEwsRequestAsync` для получения темы элемента с помощью операции `GetItem`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-668">The following example calls `makeEwsRequestAsync` to use the `GetItem` operation to get the subject of an item.</span></span>

```js
function getSubjectRequest(id) {
  // Return a GetItem operation request for the subject of the specified item.
  var request =
    '<?xml version="1.0" encoding="utf-8"?>' +
    '<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"' +
    '               xmlns:xsd="http://www.w3.org/2001/XMLSchema"' +
    '               xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/"' +
    '               xmlns:t="http://schemas.microsoft.com/exchange/services/2006/types">' +
    '  <soap:Header>' +
    '    <RequestServerVersion Version="Exchange2013" xmlns="http://schemas.microsoft.com/exchange/services/2006/types" soap:mustUnderstand="0" />' +
    '  </soap:Header>' +
    '  <soap:Body>' +
    '    <GetItem xmlns="http://schemas.microsoft.com/exchange/services/2006/messages">' +
    '      <ItemShape>' +
    '        <t:BaseShape>IdOnly</t:BaseShape>' +
    '        <t:AdditionalProperties>' +
    '            <t:FieldURI FieldURI="item:Subject"/>' +
    '        </t:AdditionalProperties>' +
    '      </ItemShape>' +
    '      <ItemIds><t:ItemId Id="' + id + '"/></ItemIds>' +
    '    </GetItem>' +
    '  </soap:Body>' +
    '</soap:Envelope>';

  return request;
}

function sendRequest() {
  // Create a local variable that contains the mailbox.
  Office.context.mailbox.makeEwsRequestAsync(
    getSubjectRequest(mailbox.item.itemId), callback);
}

function callback(asyncResult)  {
  var result = asyncResult.value;
  var context = asyncResult.asyncContext;

  // Process the returned response here.
}
```

<br>

---
---

#### <a name="removehandlerasynceventtype-options-callback"></a><span data-ttu-id="69eb3-669">removeHandlerAsync(eventType, [options], [callback])</span><span class="sxs-lookup"><span data-stu-id="69eb3-669">removeHandlerAsync(eventType, [options], [callback])</span></span>

<span data-ttu-id="69eb3-670">Удаляет обработчиков для поддерживаемого типа события.</span><span class="sxs-lookup"><span data-stu-id="69eb3-670">Removes the event handlers for a supported event type.</span></span>

<span data-ttu-id="69eb3-671">В настоящее время поддерживаются типы событий `Office.EventType.ItemChanged` и `Office.EventType.OfficeThemeChanged`.</span><span class="sxs-lookup"><span data-stu-id="69eb3-671">Currently, the supported event types are `Office.EventType.ItemChanged` and `Office.EventType.OfficeThemeChanged`.</span></span>

##### <a name="parameters"></a><span data-ttu-id="69eb3-672">Параметры</span><span class="sxs-lookup"><span data-stu-id="69eb3-672">Parameters</span></span>

| <span data-ttu-id="69eb3-673">Имя</span><span class="sxs-lookup"><span data-stu-id="69eb3-673">Name</span></span> | <span data-ttu-id="69eb3-674">Тип</span><span class="sxs-lookup"><span data-stu-id="69eb3-674">Type</span></span> | <span data-ttu-id="69eb3-675">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69eb3-675">Attributes</span></span> | <span data-ttu-id="69eb3-676">Описание</span><span class="sxs-lookup"><span data-stu-id="69eb3-676">Description</span></span> |
|---|---|---|---|
| `eventType` | [<span data-ttu-id="69eb3-677">Office.EventType</span><span class="sxs-lookup"><span data-stu-id="69eb3-677">Office.EventType</span></span>](office.md#eventtype-string) || <span data-ttu-id="69eb3-678">Событие, которое должно отменить обработчик.</span><span class="sxs-lookup"><span data-stu-id="69eb3-678">The event that should revoke the handler.</span></span> |
| `options` | <span data-ttu-id="69eb3-679">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-679">Object</span></span> | <span data-ttu-id="69eb3-680">&lt;Необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-680">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-681">Объектный литерал, содержащий одно или несколько из указанных ниже свойств.</span><span class="sxs-lookup"><span data-stu-id="69eb3-681">An object literal that contains one or more of the following properties.</span></span> |
| `options.asyncContext` | <span data-ttu-id="69eb3-682">Object</span><span class="sxs-lookup"><span data-stu-id="69eb3-682">Object</span></span> | <span data-ttu-id="69eb3-683">&lt;Необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-683">&lt;optional&gt;</span></span> | <span data-ttu-id="69eb3-684">Разработчики могут указать любой объект, к которому необходимо получить доступ, в методе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="69eb3-684">Developers can provide any object they wish to access in the callback method.</span></span> |
| `callback` | <span data-ttu-id="69eb3-685">функция</span><span class="sxs-lookup"><span data-stu-id="69eb3-685">function</span></span>| <span data-ttu-id="69eb3-686">&lt;необязательно&gt;</span><span class="sxs-lookup"><span data-stu-id="69eb3-686">&lt;optional&gt;</span></span>|<span data-ttu-id="69eb3-687">После применения метода функция, переданная в параметр `callback`, вызывается с помощью параметра `asyncResult`, который представляет собой объект [`AsyncResult`](/javascript/api/office/office.asyncresult).</span><span class="sxs-lookup"><span data-stu-id="69eb3-687">When the method completes, the function passed in the `callback` parameter is called with a single parameter, `asyncResult`, which is an [`AsyncResult`](/javascript/api/office/office.asyncresult) object.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="69eb3-688">Требования</span><span class="sxs-lookup"><span data-stu-id="69eb3-688">Requirements</span></span>

|<span data-ttu-id="69eb3-689">Требование</span><span class="sxs-lookup"><span data-stu-id="69eb3-689">Requirement</span></span>| <span data-ttu-id="69eb3-690">Значение</span><span class="sxs-lookup"><span data-stu-id="69eb3-690">Value</span></span>|
|---|---|
|[<span data-ttu-id="69eb3-691">Минимальная версия набора обязательных элементов для почтового ящика</span><span class="sxs-lookup"><span data-stu-id="69eb3-691">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="69eb3-692">1.5</span><span class="sxs-lookup"><span data-stu-id="69eb3-692">1.5</span></span> |
|[<span data-ttu-id="69eb3-693">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="69eb3-693">Minimum permission level</span></span>](/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="69eb3-694">ReadItem</span><span class="sxs-lookup"><span data-stu-id="69eb3-694">ReadItem</span></span> |
|[<span data-ttu-id="69eb3-695">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="69eb3-695">Applicable Outlook mode</span></span>](/outlook/add-ins/#extension-points)| <span data-ttu-id="69eb3-696">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="69eb3-696">Compose or Read</span></span>|