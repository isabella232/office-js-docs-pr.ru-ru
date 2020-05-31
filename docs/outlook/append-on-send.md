---
title: Реализация добавления при отправке в надстройке Outlook (Предварительная версия)
description: Узнайте, как реализовать функцию "присоединение к передаче" в надстройке Outlook.
ms.topic: article
ms.date: 05/26/2020
localization_priority: Normal
ms.openlocfilehash: ecbc1e043b6af2a0e0a6cd89de8cf4bfcec03943
ms.sourcegitcommit: 3a72d13c82b3d627691f4712d0d24b9e71bae9dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44415905"
---
# <a name="implement-append-on-send-in-your-outlook-add-in-preview"></a><span data-ttu-id="f59bf-103">Реализация добавления при отправке в надстройке Outlook (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f59bf-103">Implement append on send in your Outlook add-in (preview)</span></span>

<span data-ttu-id="f59bf-104">По завершении этого пошагового руководства у вас будет надстройка Outlook, которая может вставить заявление об отказе при отправке сообщения.</span><span class="sxs-lookup"><span data-stu-id="f59bf-104">By the end of this walkthrough, you'll have an Outlook add-in that can insert a disclaimer when a message is sent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f59bf-105">Эта функция в настоящее время поддерживается для [предварительной версии](../reference/objectmodel/preview-requirement-set/outlook-requirement-set-preview.md) в Outlook в Интернете и Windows с подпиской на Office 365.</span><span class="sxs-lookup"><span data-stu-id="f59bf-105">This feature is currently supported for [preview](../reference/objectmodel/preview-requirement-set/outlook-requirement-set-preview.md) in Outlook on the web and Windows with an Office 365 subscription.</span></span> <span data-ttu-id="f59bf-106">Узнайте [, как выполнить предварительный просмотр функции присоединения при отправке](#how-to-preview-the-append-on-send-feature) в этой статье для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="f59bf-106">See [How to preview the append-on-send feature](#how-to-preview-the-append-on-send-feature) in this article for more details.</span></span>
>
> <span data-ttu-id="f59bf-107">Так как функции предварительного просмотра могут быть изменены без предварительного уведомления, они не должны использоваться в производственных надстройках.</span><span class="sxs-lookup"><span data-stu-id="f59bf-107">Because preview features are subject to change without notice, they shouldn't be used in production add-ins.</span></span>

## <a name="how-to-preview-the-append-on-send-feature"></a><span data-ttu-id="f59bf-108">Предварительный просмотр функции присоединения при отправке</span><span class="sxs-lookup"><span data-stu-id="f59bf-108">How to preview the append-on-send feature</span></span>

<span data-ttu-id="f59bf-109">Мы приглашаем вас испытать функцию "дописывать от отправки"!</span><span class="sxs-lookup"><span data-stu-id="f59bf-109">We invite you to try out the append-on-send feature!</span></span> <span data-ttu-id="f59bf-110">Сообщите нам о своих сценариях и способах их усовершенствования, предоставив отзыв на сайте GitHub (обратитесь к разделу **Отзывы** в конце этой страницы).</span><span class="sxs-lookup"><span data-stu-id="f59bf-110">Let us know your scenarios and how we can improve by giving us feedback through GitHub (see the **Feedback** section at the end of this page).</span></span>

<span data-ttu-id="f59bf-111">Чтобы просмотреть эту функцию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f59bf-111">To preview this feature:</span></span>

- <span data-ttu-id="f59bf-112">Ссылка на **бета-** библиотеку в сети CDN ( https://appsforoffice.microsoft.com/lib/beta/hosted/office.js) .</span><span class="sxs-lookup"><span data-stu-id="f59bf-112">Reference the **beta** library on the CDN (https://appsforoffice.microsoft.com/lib/beta/hosted/office.js).</span></span> <span data-ttu-id="f59bf-113">[Файл определения типа](https://appsforoffice.microsoft.com/lib/beta/hosted/office.d.ts) для компиляции TypeScript и IntelliSense находится в сети CDN и [DefinitelyTyped](https://raw.githubusercontent.com/DefinitelyTyped/DefinitelyTyped/master/types/office-js-preview/index.d.ts).</span><span class="sxs-lookup"><span data-stu-id="f59bf-113">The [type definition file](https://appsforoffice.microsoft.com/lib/beta/hosted/office.d.ts) for TypeScript compilation and IntelliSense is found at the CDN and [DefinitelyTyped](https://raw.githubusercontent.com/DefinitelyTyped/DefinitelyTyped/master/types/office-js-preview/index.d.ts).</span></span> <span data-ttu-id="f59bf-114">Вы можете установить эти типы с помощью `npm install --save-dev @types/office-js-preview` .</span><span class="sxs-lookup"><span data-stu-id="f59bf-114">You can install these types with `npm install --save-dev @types/office-js-preview`.</span></span>
- <span data-ttu-id="f59bf-115">Для Windows вы можете присоединиться к [программе предварительной оценки Office](https://insider.office.com) , чтобы получить доступ к последним сборкам Office.</span><span class="sxs-lookup"><span data-stu-id="f59bf-115">For Windows, you may need to join the [Office Insider program](https://insider.office.com) to access more recent Office builds.</span></span>
- <span data-ttu-id="f59bf-116">Для Outlook в Интернете [Настройте целевой выпуск на клиенте Microsoft 365](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide#set-up-the-release-option-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f59bf-116">For Outlook on the web, [configure targeted release on your Microsoft 365 tenant](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide#set-up-the-release-option-in-the-admin-center).</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="f59bf-117">Настройка среды</span><span class="sxs-lookup"><span data-stu-id="f59bf-117">Set up your environment</span></span>

<span data-ttu-id="f59bf-118">Завершите работу с [быстрым запуском Outlook](../quickstarts/outlook-quickstart.md?tabs=yeomangenerator) , который создает проект надстройки с помощью генератора Yeoman для надстроек Office.</span><span class="sxs-lookup"><span data-stu-id="f59bf-118">Complete the [Outlook quick start](../quickstarts/outlook-quickstart.md?tabs=yeomangenerator) which creates an add-in project with the Yeoman generator for Office Add-ins.</span></span>

## <a name="configure-the-manifest"></a><span data-ttu-id="f59bf-119">Настройка манифеста</span><span class="sxs-lookup"><span data-stu-id="f59bf-119">Configure the manifest</span></span>

<span data-ttu-id="f59bf-120">Чтобы включить функцию Append-on-Send в надстройке, необходимо включить `AppendOnSend` разрешение в коллекцию [екстендедпермиссионс](../reference/manifest/extendedpermissions.md).</span><span class="sxs-lookup"><span data-stu-id="f59bf-120">To enable the append-on-send feature in your add-in, you must include the `AppendOnSend` permission in the collection of [ExtendedPermissions](../reference/manifest/extendedpermissions.md).</span></span>

<span data-ttu-id="f59bf-121">В этом сценарии вместо того, чтобы запускать `action` функцию при нажатии кнопки **выполнить действие** , вы заработаете `appendOnSend` функцию.</span><span class="sxs-lookup"><span data-stu-id="f59bf-121">For this scenario, instead of running the `action` function on choosing the **Perform an action** button, you'll be running the `appendOnSend` function.</span></span>

1. <span data-ttu-id="f59bf-122">В редакторе кода откройте Быстрый запуск проекта.</span><span class="sxs-lookup"><span data-stu-id="f59bf-122">In your code editor, open the quick start project.</span></span>

1. <span data-ttu-id="f59bf-123">Откройте файл **manifest. XML** , расположенный в корневом каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="f59bf-123">Open the **manifest.xml** file located at the root of your project.</span></span>

1. <span data-ttu-id="f59bf-124">Выберите весь `<VersionOverrides>` узел (включая открывающие и закрывающие теги) и замените его следующим XML-документом.</span><span class="sxs-lookup"><span data-stu-id="f59bf-124">Select the entire `<VersionOverrides>` node (including open and close tags) and replace it with the following XML.</span></span>

    ```XML
    <VersionOverrides xmlns="http://schemas.microsoft.com/office/mailappversionoverrides" xsi:type="VersionOverridesV1_0">
      <VersionOverrides xmlns="http://schemas.microsoft.com/office/mailappversionoverrides/1.1" xsi:type="VersionOverridesV1_1">
        <Requirements>
          <bt:Sets DefaultMinVersion="1.3">
            <bt:Set Name="Mailbox" />
          </bt:Sets>
        </Requirements>
        <Hosts>
          <Host xsi:type="MailHost">
            <DesktopFormFactor>
              <FunctionFile resid="Commands.Url" />
              <ExtensionPoint xsi:type="MessageComposeCommandSurface">
                <OfficeTab id="TabDefault">
                  <Group id="msgComposeGroup">
                    <Label resid="GroupLabel" />
                    <Control xsi:type="Button" id="msgComposeOpenPaneButton">
                      <Label resid="TaskpaneButton.Label" />
                      <Supertip>
                        <Title resid="TaskpaneButton.Label" />
                        <Description resid="TaskpaneButton.Tooltip" />
                      </Supertip>
                      <Icon>
                        <bt:Image size="16" resid="Icon.16x16" />
                        <bt:Image size="32" resid="Icon.32x32" />
                        <bt:Image size="80" resid="Icon.80x80" />
                      </Icon>
                      <Action xsi:type="ShowTaskpane">
                        <SourceLocation resid="Taskpane.Url" />
                      </Action>
                    </Control>
                    <Control xsi:type="Button" id="ActionButton">
                      <Label resid="ActionButton.Label"/>
                      <Supertip>
                        <Title resid="ActionButton.Label"/>
                        <Description resid="ActionButton.Tooltip"/>
                      </Supertip>
                      <Icon>
                        <bt:Image size="16" resid="Icon.16x16"/>
                        <bt:Image size="32" resid="Icon.32x32"/>
                        <bt:Image size="80" resid="Icon.80x80"/>
                      </Icon>
                      <Action xsi:type="ExecuteFunction">
                        <FunctionName>appendDisclaimerOnSend</FunctionName>
                      </Action>
                    </Control>
                  </Group>
                </OfficeTab>
              </ExtensionPoint>

              <!-- Configure AppointmentOrganizerCommandSurface extension point to support
              append on sending a new appointment. -->

            </DesktopFormFactor>
          </Host>
        </Hosts>
        <Resources>
          <bt:Images>
            <bt:Image id="Icon.16x16" DefaultValue="https://localhost:3000/assets/icon-16.png"/>
            <bt:Image id="Icon.32x32" DefaultValue="https://localhost:3000/assets/icon-32.png"/>
            <bt:Image id="Icon.80x80" DefaultValue="https://localhost:3000/assets/icon-80.png"/>
          </bt:Images>
          <bt:Urls>
            <bt:Url id="Commands.Url" DefaultValue="https://localhost:3000/commands.html" />
            <bt:Url id="Taskpane.Url" DefaultValue="https://localhost:3000/taskpane.html" />
            <bt:Url id="WebViewRuntime.Url" DefaultValue="https://localhost:3000/commands.html" />
            <bt:Url id="JSRuntime.Url" DefaultValue="https://localhost:3000/runtime.js" />
          </bt:Urls>
          <bt:ShortStrings>
            <bt:String id="GroupLabel" DefaultValue="Contoso Add-in"/>
            <bt:String id="TaskpaneButton.Label" DefaultValue="Show Taskpane"/>
            <bt:String id="ActionButton.Label" DefaultValue="Perform an action"/>
          </bt:ShortStrings>
          <bt:LongStrings>
            <bt:String id="TaskpaneButton.Tooltip" DefaultValue="Opens a pane displaying all available properties."/>
            <bt:String id="ActionButton.Tooltip" DefaultValue="Perform an action when clicked."/>
          </bt:LongStrings>
        </Resources>
        <ExtendedPermissions>
          <ExtendedPermission>AppendOnSend</ExtendedPermission>
        </ExtendedPermissions>
      </VersionOverrides>
    </VersionOverrides>
    ```

> [!TIP]
> <span data-ttu-id="f59bf-125">Чтобы узнать больше о манифестах для надстроек Outlook, ознакомьтесь с разделом [манифесты надстроек Outlook](manifests.md).</span><span class="sxs-lookup"><span data-stu-id="f59bf-125">To learn more about manifests for Outlook add-ins, see [Outlook add-in manifests](manifests.md).</span></span>

## <a name="implement-append-on-send-handling"></a><span data-ttu-id="f59bf-126">Реализация обработки при отправке по требованию</span><span class="sxs-lookup"><span data-stu-id="f59bf-126">Implement append-on-send handling</span></span>

<span data-ttu-id="f59bf-127">Затем реализуйте Добавление в событие Send.</span><span class="sxs-lookup"><span data-stu-id="f59bf-127">Next, implement appending on the send event.</span></span>

<span data-ttu-id="f59bf-128">В этом сценарии вы реализуете Добавление заявления об отказе для элемента при отправке пользователя.</span><span class="sxs-lookup"><span data-stu-id="f59bf-128">For this scenario, you'll implement appending a disclaimer to the item when the user sends.</span></span>

1. <span data-ttu-id="f59bf-129">В проекте быстрого запуска откройте файл **./СРК/коммандс/коммандс.ЖС** в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="f59bf-129">From the same quick start project, open the file **./src/commands/commands.js** in your code editor.</span></span>

1. <span data-ttu-id="f59bf-130">После `action` функции вставьте следующую функцию JavaScript.</span><span class="sxs-lookup"><span data-stu-id="f59bf-130">After the `action` function, insert the following JavaScript function.</span></span>

    ```js
    function appendDisclaimerOnSend(event) {
      var appendText =
        '<p style = "color:blue"> <i>This and subsequent emails on the same topic are for discussion and information purposes only. Only those matters set out in a fully executed agreement are legally binding. This email may contain confidential information and should not be shared with any third party without the prior written agreement of Contoso. If you are not the intended recipient, take no action and contact the sender immediately.<br><br>Contoso Limited (company number 01624297) is a company registered in England and Wales whose registered office is at Contoso Campus, Thames Valley Park, Reading RG6 1WG</i></p>';  
      /**
        *************************************************************
         Ideal Usage - Call the getBodyType API. Use the coercionType
         it returns as the parameter value below.
        *************************************************************
      */
      Office.context.mailbox.item.body.appendOnSendAsync(
        appendText,
        {
          coercionType: Office.CoercionType.Html
        },
        function(asyncResult) {
          console.log(asyncResult);
        }
      );

      event.completed();
    }
    ```

1. <span data-ttu-id="f59bf-131">В конце файла добавьте следующий оператор:</span><span class="sxs-lookup"><span data-stu-id="f59bf-131">At the end of the file, add the following statement.</span></span>

    ```js
    g.appendDisclaimerOnSend = appendDisclaimerOnSend;
    ```

## <a name="try-it-out"></a><span data-ttu-id="f59bf-132">Проверка</span><span class="sxs-lookup"><span data-stu-id="f59bf-132">Try it out</span></span>

1. <span data-ttu-id="f59bf-133">Выполните следующую команду в корневом каталоге своего проекта.</span><span class="sxs-lookup"><span data-stu-id="f59bf-133">Run the following command in the root directory of your project.</span></span> <span data-ttu-id="f59bf-134">При выполнении этой команды локальный веб-сервер запустится, если он еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="f59bf-134">When you run this command, the local web server will start if it's not already running.</span></span>

    ```command&nbsp;line
    npm run dev-server
    ```

1. <span data-ttu-id="f59bf-135">Следуйте инструкциям в статье [Загрузка неопубликованных надстройки Outlook для тестирования](sideload-outlook-add-ins-for-testing.md).</span><span class="sxs-lookup"><span data-stu-id="f59bf-135">Follow the instructions in [Sideload Outlook add-ins for testing](sideload-outlook-add-ins-for-testing.md).</span></span>

1. <span data-ttu-id="f59bf-136">Создайте новое сообщение и добавьте себя в строку " **Кому** ".</span><span class="sxs-lookup"><span data-stu-id="f59bf-136">Create a new message, and add yourself to the **To** line.</span></span>

1. <span data-ttu-id="f59bf-137">В меню лента или переполнение выберите команду **выполнить действие**.</span><span class="sxs-lookup"><span data-stu-id="f59bf-137">From the ribbon or overflow menu, choose **Perform an action**.</span></span>

1. <span data-ttu-id="f59bf-138">Отправьте сообщение, а затем откройте его в папке **"Входящие" или "** **Отправленные** ", чтобы просмотреть добавленное заявление об отказе.</span><span class="sxs-lookup"><span data-stu-id="f59bf-138">Send the message, then open it from your **Inbox** or **Sent Items** folder to view the appended disclaimer.</span></span>

    ![Снимок экрана с примером сообщения с сообщением об отказе, добавленном при отправке в Outlook в Интернете.](../images/outlook-web-append-disclaimer.png)

## <a name="see-also"></a><span data-ttu-id="f59bf-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f59bf-140">See also</span></span>

[<span data-ttu-id="f59bf-141">Манифесты надстроек Outlook</span><span class="sxs-lookup"><span data-stu-id="f59bf-141">Outlook add-in manifests</span></span>](manifests.md)