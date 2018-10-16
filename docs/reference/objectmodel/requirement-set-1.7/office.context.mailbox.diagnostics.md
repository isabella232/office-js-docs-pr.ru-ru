
# <a name="diagnostics"></a><span data-ttu-id="63ba9-101">diagnostics</span><span class="sxs-lookup"><span data-stu-id="63ba9-101">diagnostics</span></span>

### <span data-ttu-id="63ba9-p101">[Office](Office.md)[.context](Office.context.md)[.mailbox](Office.context.mailbox.md). diagnostics</span><span class="sxs-lookup"><span data-stu-id="63ba9-p101">[Office](Office.md)[.context](Office.context.md)[.mailbox](Office.context.mailbox.md). diagnostics</span></span>

<span data-ttu-id="63ba9-104">Предоставляет надстройке Outlook диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="63ba9-104">Provides diagnostic information to an Outlook add-in.</span></span>

##### <a name="requirements"></a><span data-ttu-id="63ba9-105">Требования</span><span class="sxs-lookup"><span data-stu-id="63ba9-105">Requirements</span></span>

|<span data-ttu-id="63ba9-106">Требование</span><span class="sxs-lookup"><span data-stu-id="63ba9-106">Requirement</span></span>| <span data-ttu-id="63ba9-107">Значение</span><span class="sxs-lookup"><span data-stu-id="63ba9-107">Value</span></span>|
|---|---|
|[<span data-ttu-id="63ba9-108">Версия минимального набора  требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="63ba9-108">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="63ba9-109">1.0</span><span class="sxs-lookup"><span data-stu-id="63ba9-109">1.0</span></span>|
|[<span data-ttu-id="63ba9-110">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="63ba9-110">Minimum permission level</span></span>](https://docs.microsoft.com/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="63ba9-111">ReadItem</span><span class="sxs-lookup"><span data-stu-id="63ba9-111">ReadItem</span></span>|
|[<span data-ttu-id="63ba9-112">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="63ba9-112">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="63ba9-113">Cоздание или чтение</span><span class="sxs-lookup"><span data-stu-id="63ba9-113">Compose or read</span></span>|

##### <a name="members-and-methods"></a><span data-ttu-id="63ba9-114">Члены и методы</span><span class="sxs-lookup"><span data-stu-id="63ba9-114">Members and methods</span></span>

| <span data-ttu-id="63ba9-115">Член</span><span class="sxs-lookup"><span data-stu-id="63ba9-115">Member</span></span> | <span data-ttu-id="63ba9-116">Тип</span><span class="sxs-lookup"><span data-stu-id="63ba9-116">Type</span></span> |
|--------|------|
| [<span data-ttu-id="63ba9-117">hostName</span><span class="sxs-lookup"><span data-stu-id="63ba9-117">hostName</span></span>](#hostname-string) | <span data-ttu-id="63ba9-118">Член</span><span class="sxs-lookup"><span data-stu-id="63ba9-118">Member</span></span> |
| [<span data-ttu-id="63ba9-119">hostVersion</span><span class="sxs-lookup"><span data-stu-id="63ba9-119">hostVersion</span></span>](#hostversion-string) | <span data-ttu-id="63ba9-120">Член</span><span class="sxs-lookup"><span data-stu-id="63ba9-120">Member</span></span> |
| [<span data-ttu-id="63ba9-121">OWAView</span><span class="sxs-lookup"><span data-stu-id="63ba9-121">OWAView</span></span>](#owaview-string) | <span data-ttu-id="63ba9-122">Член</span><span class="sxs-lookup"><span data-stu-id="63ba9-122">Member</span></span> |

### <a name="members"></a><span data-ttu-id="63ba9-123">Члены</span><span class="sxs-lookup"><span data-stu-id="63ba9-123">Members</span></span>

####  <a name="hostname-string"></a><span data-ttu-id="63ba9-124">hostName :String</span><span class="sxs-lookup"><span data-stu-id="63ba9-124">hostName :String</span></span>

<span data-ttu-id="63ba9-125">Получает строку, представляющую имя ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="63ba9-125">Gets a string that represents the name of the host application.</span></span>

<span data-ttu-id="63ba9-126">Строка, которая может быть одним из следующих значений: `Outlook`, `Mac Outlook`, `OutlookIOS` или `OutlookWebApp`.</span><span class="sxs-lookup"><span data-stu-id="63ba9-126">A string that can be one of the following values: `Outlook`, `Mac Outlook`, `OutlookIOS`, or `OutlookWebApp`.</span></span>

##### <a name="type"></a><span data-ttu-id="63ba9-127">Тип:</span><span class="sxs-lookup"><span data-stu-id="63ba9-127">Type:</span></span>

*   <span data-ttu-id="63ba9-128">String</span><span class="sxs-lookup"><span data-stu-id="63ba9-128">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="63ba9-129">Требования</span><span class="sxs-lookup"><span data-stu-id="63ba9-129">Requirements</span></span>

|<span data-ttu-id="63ba9-130">Требование</span><span class="sxs-lookup"><span data-stu-id="63ba9-130">Requirement</span></span>| <span data-ttu-id="63ba9-131">Значение</span><span class="sxs-lookup"><span data-stu-id="63ba9-131">Value</span></span>|
|---|---|
|[<span data-ttu-id="63ba9-132">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="63ba9-132">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="63ba9-133">1.0</span><span class="sxs-lookup"><span data-stu-id="63ba9-133">1.0</span></span>|
|[<span data-ttu-id="63ba9-134">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="63ba9-134">Minimum permission level</span></span>](https://docs.microsoft.com/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="63ba9-135">ReadItem</span><span class="sxs-lookup"><span data-stu-id="63ba9-135">ReadItem</span></span>|
|[<span data-ttu-id="63ba9-136">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="63ba9-136">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="63ba9-137">Cоздание или чтение</span><span class="sxs-lookup"><span data-stu-id="63ba9-137">Compose or read</span></span>|

####  <a name="hostversion-string"></a><span data-ttu-id="63ba9-138">hostVersion :String</span><span class="sxs-lookup"><span data-stu-id="63ba9-138">hostVersion :String</span></span>

<span data-ttu-id="63ba9-139">Получает строку, которая представляет версию ведущего приложения или Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="63ba9-139">Gets a string that represents the version of either the host application or the Exchange Server.</span></span>

<span data-ttu-id="63ba9-p102">Если почтовая надстройка запущена в классическом клиенте Outlook или Outlook для iOS, свойство `hostVersion` возвращает версию ведущего приложения — Outlook. В Outlook Web App это свойство возвращает версию Exchange Server. Например, строка `15.0.468.0`.</span><span class="sxs-lookup"><span data-stu-id="63ba9-p102">If the mail add-in is running on the Outlook desktop client or Outlook for iOS, the `hostVersion` property returns the version of the host application, Outlook. In Outlook Web App, the property returns the version of the Exchange Server. An example is the string `15.0.468.0`.</span></span>

##### <a name="type"></a><span data-ttu-id="63ba9-143">Тип:</span><span class="sxs-lookup"><span data-stu-id="63ba9-143">Type:</span></span>

*   <span data-ttu-id="63ba9-144">String</span><span class="sxs-lookup"><span data-stu-id="63ba9-144">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="63ba9-145">Требования</span><span class="sxs-lookup"><span data-stu-id="63ba9-145">Requirements</span></span>

|<span data-ttu-id="63ba9-146">Требование</span><span class="sxs-lookup"><span data-stu-id="63ba9-146">Requirement</span></span>| <span data-ttu-id="63ba9-147">Значение</span><span class="sxs-lookup"><span data-stu-id="63ba9-147">Value</span></span>|
|---|---|
|[<span data-ttu-id="63ba9-148">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="63ba9-148">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="63ba9-149">1.0</span><span class="sxs-lookup"><span data-stu-id="63ba9-149">1.0</span></span>|
|[<span data-ttu-id="63ba9-150">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="63ba9-150">Minimum permission level</span></span>](https://docs.microsoft.com/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="63ba9-151">ReadItem</span><span class="sxs-lookup"><span data-stu-id="63ba9-151">ReadItem</span></span>|
|[<span data-ttu-id="63ba9-152">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="63ba9-152">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="63ba9-153">Cоздание или чтение</span><span class="sxs-lookup"><span data-stu-id="63ba9-153">Compose or read</span></span>|

####  <a name="owaview-string"></a><span data-ttu-id="63ba9-154">OWAView :String</span><span class="sxs-lookup"><span data-stu-id="63ba9-154">OWAView :String</span></span>

<span data-ttu-id="63ba9-155">Получает строку, отображающую текущее представление Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="63ba9-155">Gets a string that represents the current view of Outlook Web App.</span></span>

<span data-ttu-id="63ba9-156">Возвращаемая строка может иметь одно из следующих значений: `OneColumn`, `TwoColumns` или `ThreeColumns`.</span><span class="sxs-lookup"><span data-stu-id="63ba9-156">The returned string can be one of the following values: `OneColumn`, `TwoColumns`, or `ThreeColumns`.</span></span>

<span data-ttu-id="63ba9-157">Если ведущее приложение — не Outlook Web App, тогда при получении доступа к этому свойству будет выдаваться значение `undefined`.</span><span class="sxs-lookup"><span data-stu-id="63ba9-157">If the host application is not Outlook Web App, then accessing this property results in `undefined`.</span></span>

<span data-ttu-id="63ba9-158">Outlook Web App включает три представления, которые соответствуют ширине экрана и окна, а также числу отображаемых столбцов:</span><span class="sxs-lookup"><span data-stu-id="63ba9-158">Outlook Web App has three views that correspond to the width of the screen and the window, and the number of columns that can be displayed:</span></span>

*   <span data-ttu-id="63ba9-p103">`OneColumn`, которое используется в случае узкого экрана. Outlook Web App использует этот макет размером в один столбец на экране смартфона.</span><span class="sxs-lookup"><span data-stu-id="63ba9-p103">`OneColumn`, which is displayed when the screen is narrow. Outlook Web App uses this single-column layout on the entire screen of a smartphone.</span></span>
*   <span data-ttu-id="63ba9-p104">`TwoColumns`, которое используется в случае более широкого экрана. Outlook Web App использует это представление на большинстве планшетных ПК.</span><span class="sxs-lookup"><span data-stu-id="63ba9-p104">`TwoColumns`, which is displayed when the screen is wider. Outlook Web App uses this view on most tablets.</span></span>
*   <span data-ttu-id="63ba9-p105">`ThreeColumns`, которое используется в случае широкого экрана. Например, Outlook Web App использует это представление в полноэкранном режиме на настольных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="63ba9-p105">`ThreeColumns`, which is displayed when the screen is wide. For example, Outlook Web App uses this view in a full screen window on a desktop computer.</span></span>

##### <a name="type"></a><span data-ttu-id="63ba9-165">Тип:</span><span class="sxs-lookup"><span data-stu-id="63ba9-165">Type:</span></span>

*   <span data-ttu-id="63ba9-166">String</span><span class="sxs-lookup"><span data-stu-id="63ba9-166">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="63ba9-167">Требования</span><span class="sxs-lookup"><span data-stu-id="63ba9-167">Requirements</span></span>

|<span data-ttu-id="63ba9-168">Требование</span><span class="sxs-lookup"><span data-stu-id="63ba9-168">Requirement</span></span>| <span data-ttu-id="63ba9-169">Значение</span><span class="sxs-lookup"><span data-stu-id="63ba9-169">Value</span></span>|
|---|---|
|[<span data-ttu-id="63ba9-170">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="63ba9-170">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="63ba9-171">1.0</span><span class="sxs-lookup"><span data-stu-id="63ba9-171">1.0</span></span>|
|[<span data-ttu-id="63ba9-172">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="63ba9-172">Minimum permission level</span></span>](https://docs.microsoft.com/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="63ba9-173">ReadItem</span><span class="sxs-lookup"><span data-stu-id="63ba9-173">ReadItem</span></span>|
|[<span data-ttu-id="63ba9-174">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="63ba9-174">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="63ba9-175">Cоздание или чтение</span><span class="sxs-lookup"><span data-stu-id="63ba9-175">Compose or read</span></span>|