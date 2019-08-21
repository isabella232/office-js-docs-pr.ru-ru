---
title: Обзор проверки подлинности и авторизации в надстройках Office
description: ''
ms.date: 08/07/2019
localization_priority: Priority
ms.openlocfilehash: 2733f8af9f236347e52269c9e73b322b4310e2a9
ms.sourcegitcommit: 1dc1bb0befe06d19b587961da892434bd0512fb5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "36302965"
---
# <a name="overview-of-authentication-and-authorization-in-office-add-ins"></a><span data-ttu-id="9e195-102">Обзор проверки подлинности и авторизации в надстройках Office</span><span class="sxs-lookup"><span data-stu-id="9e195-102">Overview of identity, authentication, and authorization in Office 2013</span></span>

<span data-ttu-id="9e195-103">Веб-приложения и, следовательно, надстройки Office по умолчанию поддерживают анонимный доступ, но вы можете требовать проверку подлинности пользователей с помощью входа.</span><span class="sxs-lookup"><span data-stu-id="9e195-103">Web applications and, hence, Office Add-ins allow anonymous access by default, but you can require users to authenticate with a login.</span></span> <span data-ttu-id="9e195-104">В частности, вы можете требовать, чтобы пользователи выполняли вход с помощью учетной записи Майкрософт либо рабочей или учебной учетной записи (Office 365).</span><span class="sxs-lookup"><span data-stu-id="9e195-104">In particular, you can require that your users be logged in with either a Microsoft Account or a Work or School (Office 365) account.</span></span> <span data-ttu-id="9e195-105">Эта задача называется проверкой подлинности пользователей, так как она позволяет надстройке определить пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e195-105">This task is called user authentication because it enables the add-in to know who the user is.</span></span>

<span data-ttu-id="9e195-106">Ваша надстройка также может получать согласие пользователя на доступ к данным Microsoft Graph (например, к профилю Office 365, файлам OneDrive и данным SharePoint) или данным в других внешних источниках, таких как Google, Facebook, LinkedIn, SalesForce и GitHub.</span><span class="sxs-lookup"><span data-stu-id="9e195-106">Your add-in can also get the user's consent to access their Microsoft Graph data (such as their Office 365 profile, OneDrive files, and SharePoint data) or to data in other external sources such as Google, Facebook, LinkedIn, SalesForce, and GitHub.</span></span> <span data-ttu-id="9e195-107">Эта задача называется авторизацией надстройки (или приложения), так как выполняется авторизация *надстройки*, а не пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e195-107">This task is called add-in (or app) authorization, because it is the *add-in* that is being authorized, not the user.</span></span>

<span data-ttu-id="9e195-108">Можно выбрать один из двух способов выполнения этих проверок подлинности.</span><span class="sxs-lookup"><span data-stu-id="9e195-108">You have a choice of two ways to accomplish these authentications.</span></span>

- <span data-ttu-id="9e195-109">**Единый вход (SSO) Office** — система, *в настоящий момент доступная в предварительной версии*, позволяющая использовать вход пользователя в Office в качестве входа в надстройку.</span><span class="sxs-lookup"><span data-stu-id="9e195-109">**Office Single Sign-on (SSO)**: A system, *currently in preview*, that enables the user's login to Office to also function as a login to the add-in.</span></span> <span data-ttu-id="9e195-110">При необходимости надстройка также может использовать учетные данные пользователя Office для своей авторизации в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="9e195-110">Optionally, the add-in can also use the user's Office credentials to authorize the add-in to Microsoft Graph.</span></span> <span data-ttu-id="9e195-111">(Источники, отличные от Майкрософт, не поддерживаются в этой системе.)</span><span class="sxs-lookup"><span data-stu-id="9e195-111">(Non-Microsoft sources are not accessible through this system.)</span></span>
- <span data-ttu-id="9e195-112">**Проверка подлинности и авторизация веб-приложения с помощью Azure Active Directory**. Это не новое решение,</span><span class="sxs-lookup"><span data-stu-id="9e195-112">**Web Application Authentication and Authorization with Azure Active Directory**: This isn't something new or special.</span></span> <span data-ttu-id="9e195-113">а просто способ, которым надстройка Office (и другие веб-приложения) проверяла подлинность пользователей и авторизовала приложения до появления системы единого входа Office. Он по-прежнему используется в сценариях, не поддерживающих единый вход.</span><span class="sxs-lookup"><span data-stu-id="9e195-113">It's just the way Office add-in (and other web apps) authenticated users and authorized apps before there was an Office SSO system and is still used in scenarios where Office SSO cannot be.</span></span>

<span data-ttu-id="9e195-114">На следующей блок-схеме показаны решения, которые нужно принять разработчику надстройки.</span><span class="sxs-lookup"><span data-stu-id="9e195-114">The following flowchart shows you the decisions that you need to make as an add-in developer.</span></span> <span data-ttu-id="9e195-115">Подробные сведения см. далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9e195-115">Site feeds are explained later in this article.</span></span>

![Изображение с блок-схемой решений для включения проверки подлинности и авторизации в надстройках Office](../images/auth-decisions-flowchart.gif)

## <a name="user-authentication-without-sso"></a><span data-ttu-id="9e195-117">Проверка подлинности пользователей без единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-117">User authentication without SSO</span></span>

<span data-ttu-id="9e195-118">Вы можете проверить подлинность пользователя в надстройке Office с помощью Azure Active Directory (AAD), как и в любом другом веб-приложении с одним исключением: служба AAD не разрешает открывать свою страницу входа в элементе iframe.</span><span class="sxs-lookup"><span data-stu-id="9e195-118">You can authenticate a user in an Office Add-in with Azure Active Directory (AAD) as you would any in any other web application with one exception: AAD does not allow its login page to open in an iframe.</span></span> <span data-ttu-id="9e195-119">При работе с надстройкой Office в *Office в Интернете* область задач является элементом iframe.</span><span class="sxs-lookup"><span data-stu-id="9e195-119">When an Office Add-in is running on *Office on the web*, the task pane is an iframe.</span></span> <span data-ttu-id="9e195-120">Это означает, что вам потребуется открыть экран входа в AAD в диалоговом окне, вызванном с помощью Dialog API для Office.</span><span class="sxs-lookup"><span data-stu-id="9e195-120">This means that you will need to open the AAD login screen in a dialog opened with the Office Dialog API.</span></span> <span data-ttu-id="9e195-121">Это влияет на способ использования библиотек помощника проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9e195-121">This affects how you use authentication helper libraries.</span></span> <span data-ttu-id="9e195-122">Дополнительные сведения см. в статье [Проверка подлинности с помощью Dialog API для Office](auth-with-office-dialog-api.md).</span><span class="sxs-lookup"><span data-stu-id="9e195-122">For more information, see [Authentication with the Office Dialog API](auth-with-office-dialog-api.md).</span></span>

<span data-ttu-id="9e195-123">Сведения о программной проверке подлинности с помощью AAD см. в статье [Общие сведения о платформе удостоверений Майкрософт (версии 2.0)](/azure/active-directory/develop/v2-overview).</span><span class="sxs-lookup"><span data-stu-id="9e195-123">For information about programming authentication with AAD, begin with [Microsoft identity platform (v2.0) overview](/azure/active-directory/develop/v2-overview).</span></span> <span data-ttu-id="9e195-124">В этом наборе документов содержится много руководств и инструкций, а также ссылки на соответствующие примеры и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9e195-124">There are many tutorials and guides in that documentation set, as well as links to relevant samples and libraries.</span></span> <span data-ttu-id="9e195-125">Как описано в статье [Проверка подлинности с помощью Dialog API для Office ](auth-with-office-dialog-api.md), вам может потребоваться изменить код из примеров, чтобы запустить его в диалоговом окне Office.</span><span class="sxs-lookup"><span data-stu-id="9e195-125">As explained in [Authentication with the Office Dialog API](auth-with-office-dialog-api.md), you may need to adjust the code in the samples to run in the Office Dialog.</span></span>

## <a name="access-to-microsoft-graph-without-sso"></a><span data-ttu-id="9e195-126">Доступ к Microsoft Graph без единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-126">Access to Microsoft Graph without SSO</span></span>

<span data-ttu-id="9e195-127">Вы можете получить для надстройки разрешение на доступ к данным Microsoft Graph, получив маркер доступа к Graph из Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="9e195-127">You can get authorization to Microsoft Graph data for your add-in by obtaining an access token to Graph from Azure Active Directory (AAD).</span></span> <span data-ttu-id="9e195-128">Это можно сделать без использования единого входа Office.</span><span class="sxs-lookup"><span data-stu-id="9e195-128">You can do this without relying on Office SSO.</span></span> <span data-ttu-id="9e195-129">Дополнительные сведения об этом см. в статье [Доступ к Microsoft Graph без единого входа](authorize-to-microsoft-graph-without-sso.md), содержащей подробности и ссылки на примеры.</span><span class="sxs-lookup"><span data-stu-id="9e195-129">For more information about how, see [Access to Microsoft Graph without SSO](authorize-to-microsoft-graph-without-sso.md) which has more details and links to samples.</span></span>

## <a name="user-authentication-with-sso"></a><span data-ttu-id="9e195-130">Проверка подлинности пользователей с помощью единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-130">User authentication with SSO</span></span>

<span data-ttu-id="9e195-131">Чтобы использовать единый вход для проверки подлинности пользователей, код в области задач или файл функции вызывает метод [getAccessTokenAsync](/javascript/api/office/office.auth#getaccesstokenasync-options--callback-).</span><span class="sxs-lookup"><span data-stu-id="9e195-131">To use SSO to authenticate the user, your code in a task pane or function file calls the [getAccessTokenAsync](/javascript/api/office/office.auth#getaccesstokenasync-options--callback-) method.</span></span> <span data-ttu-id="9e195-132">Если пользователь не вошел в Office, откроется диалоговое окно и будет выполнен переход к странице входа в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9e195-132">If the user is not signed into Office, Office will open a dialog and navigate it to the Azure Active Directory login page.</span></span> <span data-ttu-id="9e195-133">После входа пользователя метод возвращает маркер доступа,</span><span class="sxs-lookup"><span data-stu-id="9e195-133">After the user is signed in, or if the user is already signed in, the method returns an access token.</span></span> <span data-ttu-id="9e195-134">являющийся маркером начальной загрузки в потоке **От имени**.</span><span class="sxs-lookup"><span data-stu-id="9e195-134">The token is a bootstrap token in the **On Behalf Of** flow.</span></span> <span data-ttu-id="9e195-135">(См. раздел [Доступ к Microsoft Graph с помощью единого входа](#access-to-microsoft-graph-with-sso).) Однако его также можно использовать в качестве маркера идентификации, так как он содержит несколько утверждений, уникальных для текущего пользователя, включая `preferred_username`, `name`, `sub` и `oid`.</span><span class="sxs-lookup"><span data-stu-id="9e195-135">(See [Access to Microsoft Graph with SSO](#access-to-microsoft-graph-with-sso).) However, it can be used as an ID token as well, because it contains several claims that are unique to the current user, including `preferred_username`, `name`, `sub`, and `oid`.</span></span> <span data-ttu-id="9e195-136">Инструкции о том, какое свойство использовать в качестве конечного идентификатора пользователя, см. в статье [Маркеры доступа платформы удостоверений Майкрософт](https://docs.microsoft.com/ru-RU/azure/active-directory/develop/access-tokens#payload-claims).</span><span class="sxs-lookup"><span data-stu-id="9e195-136">For guidance on which property to use as the ultimate user ID, see [Microsoft identity platform access tokens](https://docs.microsoft.com/en-us/azure/active-directory/develop/access-tokens#payload-claims).</span></span> <span data-ttu-id="9e195-137">Пример одного из этих маркеров см. в статье с [примером маркера доступа](sso-in-office-add-ins.md#example-access-token).</span><span class="sxs-lookup"><span data-stu-id="9e195-137">For an example of a one of these tokens, see the [Example access token](sso-in-office-add-ins.md#example-access-token).</span></span>

<span data-ttu-id="9e195-138">После извлечения кодом нужного утверждения из маркера он использует это значение для поиска пользователя в таблице пользователей или вашей базе данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9e195-138">After your code has extracted the desired claim from the token, it uses that value to look up the user in a user table or user database that you maintain.</span></span> <span data-ttu-id="9e195-139">Используйте базу данных для хранения сведений, относящихся к пользователям, например параметров пользователя или состояния учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e195-139">Use the database to store user-relative information such as the user's preferences or the state of the user's account.</span></span> <span data-ttu-id="9e195-140">Так как вы используете единый вход, пользователи не входят отдельно в вашу надстройку, поэтому вам не нужно хранить пароли для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9e195-140">Since you are using SSO, your users don't sign-in separately to your add-in, so you do not need to store a password for the user.</span></span>

<span data-ttu-id="9e195-141">Перед началом внедрения проверки подлинности пользователей с помощью единого входа внимательно ознакомьтесь со статьей [Включение единого входа для надстроек Office](sso-in-office-add-ins.md). Также обратите внимание на следующие примеры:</span><span class="sxs-lookup"><span data-stu-id="9e195-141">Before you begin implementing user authentication with SSO, be sure that you are thoroughly familiar with the article [Enable single sign-on for Office Add-ins](sso-in-office-add-ins.md). Note also these samples:</span></span>

- <span data-ttu-id="9e195-142">[Единый вход с использованием NodeJS для надстройки Office](https://github.com/OfficeDev/Office-Add-in-NodeJS-SSO), особенно на файл [auth.ts](https://github.com/OfficeDev/Office-Add-in-NodeJS-SSO/blob/master/Completed/src/auth.ts), использующий библиотеку [jswebtoken](https://github.com/auth0/node-jsonwebtoken) для декодирования и анализа маркера.</span><span class="sxs-lookup"><span data-stu-id="9e195-142">[Office Add-in NodeJS SSO](https://github.com/OfficeDev/Office-Add-in-NodeJS-SSO), especially the file [auth.ts](https://github.com/OfficeDev/Office-Add-in-NodeJS-SSO/blob/master/Completed/src/auth.ts) which uses the library [jswebtoken](https://github.com/auth0/node-jsonwebtoken) to decode and parse the token.</span></span> <span data-ttu-id="9e195-143">(Однако в этом примере маркер не используется в качестве маркера идентификации.</span><span class="sxs-lookup"><span data-stu-id="9e195-143">(This sample, however, does not use the token as an ID token.</span></span> <span data-ttu-id="9e195-144">Он используется для получения доступа к Microsoft Graph с потоком **От имени**.)</span><span class="sxs-lookup"><span data-stu-id="9e195-144">It uses it to get access to Microsoft Graph with the **On Behalf Of** flow.)</span></span>
- <span data-ttu-id="9e195-145">[Единый вход с использованием ASP.NET для надстройки Office](https://github.com/OfficeDev/Office-Add-in-ASPNET-SSO), особенно на файл [ValuesController.ts](https://github.com/OfficeDev/Office-Add-in-ASPNET-SSO/blob/master/Complete/Office-Add-in-ASPNET-SSO-WebAPI/Controllers/ValuesController.cs), использующий класс [System.Security.Claims.ClaimsPrincipal](https://docs.microsoft.com/dotnet/api/system.security.claims.claimsprincipal) библиотеки для извлечения утверждений из маркера.</span><span class="sxs-lookup"><span data-stu-id="9e195-145">[Office Add-in ASP.NET SSO](https://github.com/OfficeDev/Office-Add-in-ASPNET-SSO), especially the file [ValuesController.ts](https://github.com/OfficeDev/Office-Add-in-ASPNET-SSO/blob/master/Complete/Office-Add-in-ASPNET-SSO-WebAPI/Controllers/ValuesController.cs) which uses the library [System.Security.Claims.ClaimsPrincipal](https://docs.microsoft.com/dotnet/api/system.security.claims.claimsprincipal) class to extract claims from the token.</span></span> <span data-ttu-id="9e195-146">(Однако в этом примере маркер не используется в качестве маркера идентификации.</span><span class="sxs-lookup"><span data-stu-id="9e195-146">(This sample, however, does not use the token as an ID token.</span></span> <span data-ttu-id="9e195-147">Он извлекает утверждение `scope` из маркера и использует его для получения доступа к Microsoft Graph с потоком **От имени**.)</span><span class="sxs-lookup"><span data-stu-id="9e195-147">It extracts a `scope` claim from the token and uses it to get access to Microsoft Graph with the **On Behalf Of** flow.)</span></span>

## <a name="access-to-microsoft-graph-with-sso"></a><span data-ttu-id="9e195-148">Доступ к Microsoft Graph с помощью единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-148">Access to Microsoft Graph with SSO</span></span>

<span data-ttu-id="9e195-149">Чтобы использовать единый вход для получения доступа к Microsoft Graph, ваша надстройка в области задач или файл функции вызывает метод [getAccessTokenAsync](/javascript/api/office/office.auth#getaccesstokenasync-options--callback-).</span><span class="sxs-lookup"><span data-stu-id="9e195-149">To use SSO to get access to Microsoft Graph, your add-in in a task pane or function file calls the [getAccessTokenAsync](/javascript/api/office/office.auth#getaccesstokenasync-options--callback-) method.</span></span> <span data-ttu-id="9e195-150">Если пользователь не вошел в Office, откроется диалоговое окно и будет выполнен переход к странице входа в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9e195-150">If the user is not signed into Office, Office will open a dialog and navigate it to the Azure Active Directory login page.</span></span> <span data-ttu-id="9e195-151">После входа пользователя метод возвращает маркер доступа,</span><span class="sxs-lookup"><span data-stu-id="9e195-151">After the user is signed in, or if the user is already signed in, the method returns an access token.</span></span> <span data-ttu-id="9e195-152">являющийся маркером начальной загрузки в потоке **От имени**.</span><span class="sxs-lookup"><span data-stu-id="9e195-152">The token is a bootstrap token in the **On Behalf Of** flow.</span></span> <span data-ttu-id="9e195-153">В частности он содержит утверждение `scope` со значением `access_as_user`.</span><span class="sxs-lookup"><span data-stu-id="9e195-153">Specifically, it has a `scope` claim with the value `access_as_user`.</span></span> <span data-ttu-id="9e195-154">Руководство по утверждениям в маркере см. в статье [Маркеры доступа платформы удостоверений Майкрософт](https://docs.microsoft.com/ru-RU/azure/active-directory/develop/access-tokens#payload-claims).</span><span class="sxs-lookup"><span data-stu-id="9e195-154">For guidance about the claims in the token, see [Microsoft identity platform access tokens](https://docs.microsoft.com/en-us/azure/active-directory/develop/access-tokens#payload-claims).</span></span> <span data-ttu-id="9e195-155">Пример одного из этих маркеров см. в статье с [примером маркера доступа](sso-in-office-add-ins.md#example-access-token).</span><span class="sxs-lookup"><span data-stu-id="9e195-155">For an example of a one of these tokens, see the [Example access token](sso-in-office-add-ins.md#example-access-token).</span></span>

<span data-ttu-id="9e195-156">После получения маркера кодом он используется в потоке **От имени**, чтобы получить второй маркер: маркер доступа к Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="9e195-156">After your code obtains the token, it uses it in the **On Behalf Of** flow to obtain a second token: an access token to Microsoft Graph.</span></span>

<span data-ttu-id="9e195-157">Перед началом внедрения единого входа Office внимательно ознакомьтесь со следующими двумя статьями:</span><span class="sxs-lookup"><span data-stu-id="9e195-157">Before you begin implementing Office SSO, be sure that you are thoroughly familiar with these two articles:</span></span>

- [<span data-ttu-id="9e195-158">Включение единого входа для надстроек Office</span><span class="sxs-lookup"><span data-stu-id="9e195-158">Enable single sign-on for Office Add-ins</span></span>](sso-in-office-add-ins.md)
- [<span data-ttu-id="9e195-159">Авторизация в Microsoft Graph с помощью единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-159">Authorize to Microsoft Graph with SSO</span></span>](authorize-to-microsoft-graph.md)

<span data-ttu-id="9e195-160">Вам также следует ознакомиться хотя бы с одним руководством, указанным здесь.</span><span class="sxs-lookup"><span data-stu-id="9e195-160">You should also read at least one of the walkthrough articles listed here.</span></span> <span data-ttu-id="9e195-161">Даже если вы не выполняете описанные действия, они содержат важную информацию о реализации единого входа Office и потока **От имени**.</span><span class="sxs-lookup"><span data-stu-id="9e195-161">Even if you don't carry out the steps, these contain valuable information about how you implement Office SSO and the **On Behalf Of** flow.</span></span> 

- [<span data-ttu-id="9e195-162">Создание надстройки Office на платформе ASP.NET с использованием единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-162">Create an ASP.NET Office Add-in that uses single sign-on</span></span>](create-sso-office-add-ins-aspnet.md)
- [<span data-ttu-id="9e195-163">Создание надстройки Office на платформе Node.js с использованием единого входа</span><span class="sxs-lookup"><span data-stu-id="9e195-163">Create a Node.js Office Add-in that uses single sign-on</span></span>](create-sso-office-add-ins-nodejs.md)

<span data-ttu-id="9e195-164">Также обратите внимание на следующие примеры:</span><span class="sxs-lookup"><span data-stu-id="9e195-164">Note also these samples:</span></span>

- [<span data-ttu-id="9e195-165">Единый вход с использованием NodeJS для надстройки Office</span><span class="sxs-lookup"><span data-stu-id="9e195-165">Office Add-in NodeJS SSO</span></span>](https://github.com/OfficeDev/Office-Add-in-NodeJS-SSO)
- [<span data-ttu-id="9e195-166">Единый вход с использованием ASP.NET для надстройки Office</span><span class="sxs-lookup"><span data-stu-id="9e195-166">Office Add-in ASP.NET SSO</span></span>](https://github.com/OfficeDev/Office-Add-in-ASPNET-SSO)

## <a name="access-to-non-microsoft-data-sources"></a><span data-ttu-id="9e195-167">Доступ к сторонним источникам данных (отличным от Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="9e195-167">Access to non-Microsoft data sources</span></span>

<span data-ttu-id="9e195-168">С помощью популярных веб-служб, в том числе Google, Facebook, LinkedIn, SalesForce и GitHub, разработчики могут предоставлять пользователям доступ к их учетным записям в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="9e195-168">Popular online services, including Office 365, Google, Facebook, LinkedIn, SalesForce, and GitHub, let developers give users access to their accounts in other applications.</span></span> <span data-ttu-id="9e195-169">Благодаря этому вы можете включать эти службы в свои надстройки Office.</span><span class="sxs-lookup"><span data-stu-id="9e195-169">This gives you the ability to include these services in your Office Add-in.</span></span> <span data-ttu-id="9e195-170">Обзор способов, доступных вашей надстройке для выполнения этих действий, см. в статье [Авторизация внешних служб в надстройке Office](auth-external-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="9e195-170">For an overview of the ways that your add-in can do this, see [Authorize external services in your Office Add-in](auth-external-add-ins.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e195-171">Перед началом создания кода выясните, позволяет ли источник данных открывать экран входа в элементе iFrame.</span><span class="sxs-lookup"><span data-stu-id="9e195-171">Before you begin coding, find out if the data source allows its login in screen to be opened in an iFrame.</span></span> <span data-ttu-id="9e195-172">При работе с надстройкой Office в *Office в Интернете* область задач является элементом iFrame.</span><span class="sxs-lookup"><span data-stu-id="9e195-172">When an Office Add-in is running on *Office on the web*, the task pane is an iFrame.</span></span> <span data-ttu-id="9e195-173">Если источник данных не позволяет открывать экран входа в элементе iFrame, вам потребуется открыть экран входа в диалоговом окне, вызываемом с помощью Dialog API для Office.</span><span class="sxs-lookup"><span data-stu-id="9e195-173">If the data source does not allow its login screen to be opened in an iFrame, then you will need to open the login screen in a dialog opened with the Office Dialog API.</span></span> <span data-ttu-id="9e195-174">Дополнительные сведения см. в статье [Проверка подлинности с помощью Dialog API для Office](auth-with-office-dialog-api.md).</span><span class="sxs-lookup"><span data-stu-id="9e195-174">For more information, see [Authentication with the Office Dialog API](auth-with-office-dialog-api.md).</span></span>
