 

# <a name="office"></a><span data-ttu-id="30d2e-101">Office</span><span class="sxs-lookup"><span data-stu-id="30d2e-101">Office</span></span>

<span data-ttu-id="30d2e-p101">Пространство имен Office содержит общие интерфейсы, которые используются надстройками всех приложений Office. В этот список входят только интерфейсы, используемые надстройками Outlook. Полный список интерфейсов пространства имен Office см. в статье [Общий API](/javascript/api/office).</span><span class="sxs-lookup"><span data-stu-id="30d2e-p101">The Office namespace provides shared interfaces that are used by add-ins in all of the Office apps. This listing documents only those interfaces that are used by Outlook add-ins. For a full listing of the Office namespace, see the [Shared API](/javascript/api/office).</span></span>

##### <a name="requirements"></a><span data-ttu-id="30d2e-104">Требования</span><span class="sxs-lookup"><span data-stu-id="30d2e-104">Requirements</span></span>

|<span data-ttu-id="30d2e-105">Требование</span><span class="sxs-lookup"><span data-stu-id="30d2e-105">Requirement</span></span>| <span data-ttu-id="30d2e-106">Значение</span><span class="sxs-lookup"><span data-stu-id="30d2e-106">Value</span></span>|
|---|---|
|[<span data-ttu-id="30d2e-107">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="30d2e-107">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="30d2e-108">1.0</span><span class="sxs-lookup"><span data-stu-id="30d2e-108">1.0</span></span>|
|[<span data-ttu-id="30d2e-109">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="30d2e-109">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="30d2e-110">Compose или read</span><span class="sxs-lookup"><span data-stu-id="30d2e-110">Compose or read</span></span>|

##### <a name="members-and-methods"></a><span data-ttu-id="30d2e-111">Члены и методы</span><span class="sxs-lookup"><span data-stu-id="30d2e-111">Members and methods</span></span>

| <span data-ttu-id="30d2e-112">Член</span><span class="sxs-lookup"><span data-stu-id="30d2e-112">Member</span></span> | <span data-ttu-id="30d2e-113">Тип</span><span class="sxs-lookup"><span data-stu-id="30d2e-113">Type</span></span> |
|--------|------|
| [<span data-ttu-id="30d2e-114">AsyncResultStatus</span><span class="sxs-lookup"><span data-stu-id="30d2e-114">AsyncResultStatus</span></span>](#asyncresultstatus-string) | <span data-ttu-id="30d2e-115">Член</span><span class="sxs-lookup"><span data-stu-id="30d2e-115">Member</span></span> |
| [<span data-ttu-id="30d2e-116">CoercionType</span><span class="sxs-lookup"><span data-stu-id="30d2e-116">CoercionType</span></span>](#coerciontype-string) | <span data-ttu-id="30d2e-117">Член</span><span class="sxs-lookup"><span data-stu-id="30d2e-117">Member</span></span> |
| [<span data-ttu-id="30d2e-118">EventType</span><span class="sxs-lookup"><span data-stu-id="30d2e-118">EventType</span></span>](#eventtype-string) | <span data-ttu-id="30d2e-119">Член</span><span class="sxs-lookup"><span data-stu-id="30d2e-119">Member</span></span> |
| [<span data-ttu-id="30d2e-120">SourceProperty</span><span class="sxs-lookup"><span data-stu-id="30d2e-120">SourceProperty</span></span>](#sourceproperty-string) | <span data-ttu-id="30d2e-121">Член</span><span class="sxs-lookup"><span data-stu-id="30d2e-121">Member</span></span> |

### <a name="namespaces"></a><span data-ttu-id="30d2e-122">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="30d2e-122">Namespaces</span></span>

<span data-ttu-id="30d2e-123">[context](office.context.md) — предоставляет общие интерфейсы из контекстного пространства имен API надстроек Office для использования в API надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="30d2e-123">[context](office.context.md): Provides shared interfaces from the Office add-ins API's context namespace for use in the Outlook add-in API.</span></span>

<span data-ttu-id="30d2e-124">[MailboxEnums](/javascript/api/outlook_1_7/office.mailboxenums.attachmenttype) — включает перечисления ItemType, EntityType, AttachmentType, RecipientType, ResponseType и ItemNotificationMessageType.</span><span class="sxs-lookup"><span data-stu-id="30d2e-124">[MailboxEnums](/javascript/api/outlook_1_7/office.mailboxenums.attachmenttype): Includes the ItemType, EntityType, AttachmentType, RecipientType, ResponseType, and ItemNotificationMessageType enumerations.</span></span>

### <a name="members"></a><span data-ttu-id="30d2e-125">Члены</span><span class="sxs-lookup"><span data-stu-id="30d2e-125">Members</span></span>

####  <a name="asyncresultstatus-string"></a><span data-ttu-id="30d2e-126">AsyncResultStatus :String</span><span class="sxs-lookup"><span data-stu-id="30d2e-126">AsyncResultStatus :String</span></span>

<span data-ttu-id="30d2e-127">Указывает результат асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="30d2e-127">Specifies the result of an asynchronous call.</span></span>

##### <a name="type"></a><span data-ttu-id="30d2e-128">Тип:</span><span class="sxs-lookup"><span data-stu-id="30d2e-128">Type:</span></span>

*   <span data-ttu-id="30d2e-129">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-129">String</span></span>

##### <a name="properties"></a><span data-ttu-id="30d2e-130">Свойства:</span><span class="sxs-lookup"><span data-stu-id="30d2e-130">Properties:</span></span>

|<span data-ttu-id="30d2e-131">Имя</span><span class="sxs-lookup"><span data-stu-id="30d2e-131">Name</span></span>| <span data-ttu-id="30d2e-132">Тип</span><span class="sxs-lookup"><span data-stu-id="30d2e-132">Type</span></span>| <span data-ttu-id="30d2e-133">Описание</span><span class="sxs-lookup"><span data-stu-id="30d2e-133">Description</span></span>|
|---|---|---|
|`Succeeded`| <span data-ttu-id="30d2e-134">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-134">String</span></span>|<span data-ttu-id="30d2e-135">Вызов завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="30d2e-135">The call succeeded.</span></span>|
|`Failed`| <span data-ttu-id="30d2e-136">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-136">String</span></span>|<span data-ttu-id="30d2e-137">Вызов не удался.</span><span class="sxs-lookup"><span data-stu-id="30d2e-137">The call failed.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="30d2e-138">Требования</span><span class="sxs-lookup"><span data-stu-id="30d2e-138">Requirements</span></span>

|<span data-ttu-id="30d2e-139">Требование</span><span class="sxs-lookup"><span data-stu-id="30d2e-139">Requirement</span></span>| <span data-ttu-id="30d2e-140">Значение</span><span class="sxs-lookup"><span data-stu-id="30d2e-140">Value</span></span>|
|---|---|
|[<span data-ttu-id="30d2e-141">Версия минимального набора обязательных элементов для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="30d2e-141">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="30d2e-142">1.0</span><span class="sxs-lookup"><span data-stu-id="30d2e-142">1.0</span></span>|
|[<span data-ttu-id="30d2e-143">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="30d2e-143">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="30d2e-144">Compose или read</span><span class="sxs-lookup"><span data-stu-id="30d2e-144">Compose or read</span></span>|

---

####  <a name="coerciontype-string"></a><span data-ttu-id="30d2e-145">CoercionType :String</span><span class="sxs-lookup"><span data-stu-id="30d2e-145">CoercionType :String</span></span>

<span data-ttu-id="30d2e-146">Указывает способ приведения данных, возвращаемых или задаваемых вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="30d2e-146">Specifies how to coerce data returned or set by the invoked method.</span></span>

##### <a name="type"></a><span data-ttu-id="30d2e-147">Тип:</span><span class="sxs-lookup"><span data-stu-id="30d2e-147">Type:</span></span>

*   <span data-ttu-id="30d2e-148">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-148">String</span></span>

##### <a name="properties"></a><span data-ttu-id="30d2e-149">Свойства:</span><span class="sxs-lookup"><span data-stu-id="30d2e-149">Properties:</span></span>

|<span data-ttu-id="30d2e-150">Имя</span><span class="sxs-lookup"><span data-stu-id="30d2e-150">Name</span></span>| <span data-ttu-id="30d2e-151">Тип</span><span class="sxs-lookup"><span data-stu-id="30d2e-151">Type</span></span>| <span data-ttu-id="30d2e-152">Описание</span><span class="sxs-lookup"><span data-stu-id="30d2e-152">Description</span></span>|
|---|---|---|
|`Html`| <span data-ttu-id="30d2e-153">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-153">String</span></span>|<span data-ttu-id="30d2e-154">Запрашивает возврат данных в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="30d2e-154">Requests the data be returned in HTML format.</span></span>|
|`Text`| <span data-ttu-id="30d2e-155">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-155">String</span></span>|<span data-ttu-id="30d2e-156">Запрашивает возврат данных в формате текста.</span><span class="sxs-lookup"><span data-stu-id="30d2e-156">Requests the data be returned in text format.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="30d2e-157">Требования</span><span class="sxs-lookup"><span data-stu-id="30d2e-157">Requirements</span></span>

|<span data-ttu-id="30d2e-158">Требование</span><span class="sxs-lookup"><span data-stu-id="30d2e-158">Requirement</span></span>| <span data-ttu-id="30d2e-159">Значение</span><span class="sxs-lookup"><span data-stu-id="30d2e-159">Value</span></span>|
|---|---|
|[<span data-ttu-id="30d2e-160">Версия минимального набора обязательных элементов для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="30d2e-160">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="30d2e-161">1.0</span><span class="sxs-lookup"><span data-stu-id="30d2e-161">1.0</span></span>|
|[<span data-ttu-id="30d2e-162">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="30d2e-162">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="30d2e-163">Compose или read</span><span class="sxs-lookup"><span data-stu-id="30d2e-163">Compose or read</span></span>|

---

####  <a name="eventtype-string"></a><span data-ttu-id="30d2e-164">EventType :String</span><span class="sxs-lookup"><span data-stu-id="30d2e-164">EventType :String</span></span>

<span data-ttu-id="30d2e-165">Указывает событие, связанное с обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="30d2e-165">Specifies the event associated with an event handler.</span></span>

##### <a name="type"></a><span data-ttu-id="30d2e-166">Тип:</span><span class="sxs-lookup"><span data-stu-id="30d2e-166">Type:</span></span>

*   <span data-ttu-id="30d2e-167">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-167">String</span></span>

##### <a name="properties"></a><span data-ttu-id="30d2e-168">Свойства:</span><span class="sxs-lookup"><span data-stu-id="30d2e-168">Properties:</span></span>

| <span data-ttu-id="30d2e-169">Имя</span><span class="sxs-lookup"><span data-stu-id="30d2e-169">Name</span></span> | <span data-ttu-id="30d2e-170">Тип</span><span class="sxs-lookup"><span data-stu-id="30d2e-170">Type</span></span> | <span data-ttu-id="30d2e-171">Описание</span><span class="sxs-lookup"><span data-stu-id="30d2e-171">Description</span></span> | <span data-ttu-id="30d2e-172">Минимальный набор требований</span><span class="sxs-lookup"><span data-stu-id="30d2e-172">Minimum mailbox requirement set version</span></span> |
|---|---|---|---|
|`AppointmentTimeChanged`| <span data-ttu-id="30d2e-173">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-173">String</span></span> | <span data-ttu-id="30d2e-174">Дата или время выбранной встречи или серии была изменена.</span><span class="sxs-lookup"><span data-stu-id="30d2e-174">The date or time of the selected appointment or series has changed.</span></span> | <span data-ttu-id="30d2e-175">1.7</span><span class="sxs-lookup"><span data-stu-id="30d2e-175">17 </span></span> |
|`ItemChanged`| <span data-ttu-id="30d2e-176">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-176">String</span></span> | <span data-ttu-id="30d2e-177">Выбранный элемент изменился.</span><span class="sxs-lookup"><span data-stu-id="30d2e-177">The selected item has changed.</span></span> | <span data-ttu-id="30d2e-178">1.5</span><span class="sxs-lookup"><span data-stu-id="30d2e-178">1.5</span></span> |
|`RecipientsChanged`| <span data-ttu-id="30d2e-179">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-179">String</span></span> | <span data-ttu-id="30d2e-180">Список получателей в выбранном элементе или расположение встречи изменен(-о).</span><span class="sxs-lookup"><span data-stu-id="30d2e-180">The recipient list of the selected item or appointment location has changed.</span></span> | <span data-ttu-id="30d2e-181">1.7</span><span class="sxs-lookup"><span data-stu-id="30d2e-181">17 </span></span> |
|`RecurrenceChanged`| <span data-ttu-id="30d2e-182">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-182">String</span></span> | <span data-ttu-id="30d2e-183">Расписание повторения выбранной серии было изменено.</span><span class="sxs-lookup"><span data-stu-id="30d2e-183">The recurrence pattern of the selected series has changed.</span></span> | <span data-ttu-id="30d2e-184">1.7</span><span class="sxs-lookup"><span data-stu-id="30d2e-184">17 </span></span> |

##### <a name="requirements"></a><span data-ttu-id="30d2e-185">Требования</span><span class="sxs-lookup"><span data-stu-id="30d2e-185">Requirements</span></span>

|<span data-ttu-id="30d2e-186">Требование</span><span class="sxs-lookup"><span data-stu-id="30d2e-186">Requirement</span></span>| <span data-ttu-id="30d2e-187">Значение</span><span class="sxs-lookup"><span data-stu-id="30d2e-187">Value</span></span>|
|---|---|
|[<span data-ttu-id="30d2e-188">Версия минимального набора обязательных элементов для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="30d2e-188">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="30d2e-189">1.5</span><span class="sxs-lookup"><span data-stu-id="30d2e-189">1.5</span></span> |
|[<span data-ttu-id="30d2e-190">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="30d2e-190">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="30d2e-191">Compose или read</span><span class="sxs-lookup"><span data-stu-id="30d2e-191">Compose or read</span></span> |

---

####  <a name="sourceproperty-string"></a><span data-ttu-id="30d2e-192">SourceProperty :String</span><span class="sxs-lookup"><span data-stu-id="30d2e-192">SourceProperty :String</span></span>

<span data-ttu-id="30d2e-193">Указывает источник данных, возвращаемых вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="30d2e-193">Specifies the source of the data returned by the invoked method.</span></span>

##### <a name="type"></a><span data-ttu-id="30d2e-194">Тип:</span><span class="sxs-lookup"><span data-stu-id="30d2e-194">Type:</span></span>

*   <span data-ttu-id="30d2e-195">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-195">String</span></span>

##### <a name="properties"></a><span data-ttu-id="30d2e-196">Свойства:</span><span class="sxs-lookup"><span data-stu-id="30d2e-196">Properties:</span></span>

|<span data-ttu-id="30d2e-197">Имя</span><span class="sxs-lookup"><span data-stu-id="30d2e-197">Name</span></span>| <span data-ttu-id="30d2e-198">Тип</span><span class="sxs-lookup"><span data-stu-id="30d2e-198">Type</span></span>| <span data-ttu-id="30d2e-199">Описание</span><span class="sxs-lookup"><span data-stu-id="30d2e-199">Description</span></span>|
|---|---|---|
|`Body`| <span data-ttu-id="30d2e-200">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-200">String</span></span>|<span data-ttu-id="30d2e-201">Источник данных — текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="30d2e-201">The source of the data is from the body of a message.</span></span>|
|`Subject`| <span data-ttu-id="30d2e-202">String</span><span class="sxs-lookup"><span data-stu-id="30d2e-202">String</span></span>|<span data-ttu-id="30d2e-203">Источник данных — тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="30d2e-203">The source of the data is from the subject of a message.</span></span>|

##### <a name="requirements"></a><span data-ttu-id="30d2e-204">Требования</span><span class="sxs-lookup"><span data-stu-id="30d2e-204">Requirements</span></span>

|<span data-ttu-id="30d2e-205">Требование</span><span class="sxs-lookup"><span data-stu-id="30d2e-205">Requirement</span></span>| <span data-ttu-id="30d2e-206">Значение</span><span class="sxs-lookup"><span data-stu-id="30d2e-206">Value</span></span>|
|---|---|
|[<span data-ttu-id="30d2e-207">Версия минимального набора обязательных элементов для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="30d2e-207">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="30d2e-208">1.0</span><span class="sxs-lookup"><span data-stu-id="30d2e-208">1.0</span></span>|
|[<span data-ttu-id="30d2e-209">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="30d2e-209">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="30d2e-210">Compose или read</span><span class="sxs-lookup"><span data-stu-id="30d2e-210">Compose or read</span></span>|