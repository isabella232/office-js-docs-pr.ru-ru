
# <a name="context"></a><span data-ttu-id="3a34a-101">context</span><span class="sxs-lookup"><span data-stu-id="3a34a-101">context</span></span>

### <span data-ttu-id="3a34a-p101">[Office](Office.md).context</span><span class="sxs-lookup"><span data-stu-id="3a34a-p101">[Office](Office.md). context</span></span>

<span data-ttu-id="3a34a-p102">Пространство имен Office.context содержит общие интерфейсы, которые используются надстройками всех приложений Office. В этот список входят только интерфейсы, используемые надстройками Outlook. Полный список интерфейсов пространства имен Office.context см. в статье [Ссылка на пространство имен Office.context в общем API](/javascript/api/office/office.context).</span><span class="sxs-lookup"><span data-stu-id="3a34a-p102">The Office.context namespace provides shared interfaces that are used by add-ins in all of the Office apps. This listing documents only those interfaces that are used by Outlook add-ins. For a full listing of the Office.context namespace, see the [Office.context reference in the Shared API](/javascript/api/office/office.context).</span></span>


##### <a name="requirements"></a><span data-ttu-id="3a34a-106">Требования</span><span class="sxs-lookup"><span data-stu-id="3a34a-106">Requirements</span></span>

|<span data-ttu-id="3a34a-107">Требование</span><span class="sxs-lookup"><span data-stu-id="3a34a-107">Requirement</span></span>| <span data-ttu-id="3a34a-108">Значение</span><span class="sxs-lookup"><span data-stu-id="3a34a-108">Value</span></span>|
|---|---|
|[<span data-ttu-id="3a34a-109">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="3a34a-109">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="3a34a-110">1.0</span><span class="sxs-lookup"><span data-stu-id="3a34a-110">1.0</span></span>|
|[<span data-ttu-id="3a34a-111">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="3a34a-111">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="3a34a-112">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="3a34a-112">Compose or read</span></span>|

### <a name="namespaces"></a><span data-ttu-id="3a34a-113">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="3a34a-113">Namespaces</span></span>

<span data-ttu-id="3a34a-114">[mailbox](office.context.mailbox.md): предоставляет для Microsoft Outlook и Microsoft Outlook в Интернете доступ к объектной модели надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="3a34a-114">[mailbox](office.context.mailbox.md) - Provides access to the Outlook Add-in object model for Microsoft Outlook and Microsoft Outlook on the web.</span></span>

### <a name="members"></a><span data-ttu-id="3a34a-115">Члены</span><span class="sxs-lookup"><span data-stu-id="3a34a-115">Members</span></span>

####  <a name="displaylanguage-string"></a><span data-ttu-id="3a34a-116">displayLanguage :String</span><span class="sxs-lookup"><span data-stu-id="3a34a-116">displayLanguage :String</span></span>

<span data-ttu-id="3a34a-117">Получает определенный пользователем языковой стандарт в формате обозначений языка RFC 1766 для пользовательского интерфейса ведущего приложения Office.</span><span class="sxs-lookup"><span data-stu-id="3a34a-117">Gets the locale (language) in RFC 1766 Language tag format specified by the user for the UI of the Office host application.</span></span>

<span data-ttu-id="3a34a-118">Значение `displayLanguage` отображает текущий параметр **Язык интерфейса**, заданный в разделе **Файл > Параметры > Язык** ведущего приложения Office.</span><span class="sxs-lookup"><span data-stu-id="3a34a-118">The `displayLanguage` value reflects the current **Display Language** setting specified with **File > Options > Language** in the Office host application.</span></span>

##### <a name="type"></a><span data-ttu-id="3a34a-119">Тип:</span><span class="sxs-lookup"><span data-stu-id="3a34a-119">Type:</span></span>

*   <span data-ttu-id="3a34a-120">String</span><span class="sxs-lookup"><span data-stu-id="3a34a-120">String</span></span>

##### <a name="requirements"></a><span data-ttu-id="3a34a-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3a34a-121">Requirements</span></span>

|<span data-ttu-id="3a34a-122">Требование</span><span class="sxs-lookup"><span data-stu-id="3a34a-122">Requirement</span></span>| <span data-ttu-id="3a34a-123">Значение</span><span class="sxs-lookup"><span data-stu-id="3a34a-123">Value</span></span>|
|---|---|
|[<span data-ttu-id="3a34a-124">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="3a34a-124">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="3a34a-125">1.0</span><span class="sxs-lookup"><span data-stu-id="3a34a-125">1.0</span></span>|
|[<span data-ttu-id="3a34a-126">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="3a34a-126">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="3a34a-127">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="3a34a-127">Compose or read</span></span>|

##### <a name="example"></a><span data-ttu-id="3a34a-128">Пример</span><span class="sxs-lookup"><span data-stu-id="3a34a-128">Example</span></span>

```js
function sayHelloWithDisplayLanguage() {
  var myDisplayLanguage = Office.context.displayLanguage;
  switch (myDisplayLanguage) {
    case 'en-US':
      write('Hello!');
      break;
    case 'en-NZ':
      write('G\'day mate!');
      break;
  }
}
// Function that writes to a div with id='message' on the page.
function write(message){
  document.getElementById('message').innerText += message;
}
```

####  <a name="roamingsettings-roamingsettingsjavascriptapioutlook12officeroamingsettings"></a><span data-ttu-id="3a34a-129">roamingSettings :[RoamingSettings](/javascript/api/outlook_1_2/office.RoamingSettings)</span><span class="sxs-lookup"><span data-stu-id="3a34a-129">roamingSettings :[RoamingSettings](/javascript/api/outlook_1_2/office.RoamingSettings)</span></span>

<span data-ttu-id="3a34a-130">Получает объект, представляющий настраиваемые параметры или состояние надстройки почты, сохраненное в почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a34a-130">Gets an object that represents the custom settings or state of a mail add-in saved to a user's mailbox.</span></span>

<span data-ttu-id="3a34a-131">Объект `RoamingSettings` позволяет сохранять данные для надстройки почты, записанные в почтовом ящике пользователя, и получать к ним доступ, таким образом делая их доступными для этой надстройки, когда она запускается из любого клиентского ведущего приложения, используемого для доступа к этому почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="3a34a-131">The `RoamingSettings` object lets you store and access data for a mail add-in that is stored in a user's mailbox, so that is available to that add-in when it is running from any host client application used to access that mailbox.</span></span>

##### <a name="type"></a><span data-ttu-id="3a34a-132">Тип:</span><span class="sxs-lookup"><span data-stu-id="3a34a-132">Type:</span></span>

*   [<span data-ttu-id="3a34a-133">RoamingSettings</span><span class="sxs-lookup"><span data-stu-id="3a34a-133">RoamingSettings</span></span>](/javascript/api/outlook_1_2/office.RoamingSettings)

##### <a name="requirements"></a><span data-ttu-id="3a34a-134">Требования</span><span class="sxs-lookup"><span data-stu-id="3a34a-134">Requirements</span></span>

|<span data-ttu-id="3a34a-135">Требование</span><span class="sxs-lookup"><span data-stu-id="3a34a-135">Requirement</span></span>| <span data-ttu-id="3a34a-136">Значение</span><span class="sxs-lookup"><span data-stu-id="3a34a-136">Value</span></span>|
|---|---|
|[<span data-ttu-id="3a34a-137">Версия минимального набора требований для почтового ящика (mailbox)</span><span class="sxs-lookup"><span data-stu-id="3a34a-137">Minimum mailbox requirement set version</span></span>](/office/dev/add-ins/reference/requirement-sets/outlook-api-requirement-sets)| <span data-ttu-id="3a34a-138">1.0</span><span class="sxs-lookup"><span data-stu-id="3a34a-138">1.0</span></span>|
|[<span data-ttu-id="3a34a-139">Минимальный уровень разрешений</span><span class="sxs-lookup"><span data-stu-id="3a34a-139">Minimum permission level</span></span>](https://docs.microsoft.com/outlook/add-ins/understanding-outlook-add-in-permissions)| <span data-ttu-id="3a34a-140">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="3a34a-140">Restricted</span></span>|
|[<span data-ttu-id="3a34a-141">Применимый режим Outlook</span><span class="sxs-lookup"><span data-stu-id="3a34a-141">Applicable Outlook mode</span></span>](https://docs.microsoft.com/outlook/add-ins/#extension-points)| <span data-ttu-id="3a34a-142">Создание или чтение</span><span class="sxs-lookup"><span data-stu-id="3a34a-142">Compose or read</span></span>|