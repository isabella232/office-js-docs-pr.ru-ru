---
title: Авторизация в Microsoft Graph с помощью единого входа
description: Узнайте, как пользователи надстройки Office могут использовать единый вход (SSO) для получения данных из Microsoft Graph.
ms.date: 07/30/2020
localization_priority: Normal
ms.openlocfilehash: 68440a347e11d909f0ebd4d4d29892711646da5e
ms.sourcegitcommit: 9609bd5b4982cdaa2ea7637709a78a45835ffb19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "47292906"
---
# <a name="authorize-to-microsoft-graph-with-sso"></a>Авторизация в Microsoft Graph с помощью единого входа

Пользователи входят в Office (в Интернете, на мобильных устройствах и настольных компьютерах), используя личную учетную запись Майкрософт, учетную запись Microsoft 365 для образования или рабочую учетную запись. Чтобы надстройка Office могла получить авторизованный доступ к [Microsoft Graph](https://developer.microsoft.com/graph/docs), лучше всего использовать учетные данные для входа пользователя в Office. Это позволяет пользователям получить доступ к своим данным Microsoft Graph без необходимости повторного входа.

> [!NOTE]
> API единого входа в настоящее время поддерживается для Word, Excel, Outlook и PowerPoint. Дополнительные сведения о текущей поддержке API единого входа см. в статье [Наборы обязательных элементов API идентификации](/office/dev/add-ins/reference/requirement-sets/identity-api-requirement-sets).
> Если вы работаете с надстройкой Outlook, обязательно включите современную проверку подлинности для клиента Office 365. Сведения о том, как это сделать, см. в статье [Exchange Online: как включить в клиенте современную проверку подлинности](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx).


## <a name="add-in-architecture-for-sso-and-microsoft-graph"></a>Архитектура надстройки для единого входа и Microsoft Graph

Помимо страниц и кода JavaScript веб-приложения, в надстройке также должны размещаться (с тем же [полным доменном именем](/windows/desktop/DNS/f-gly#_dns_fully_qualified_domain_name_fqdn__gly)) один или несколько веб-API, которые будут получать маркер доступа и отправлять запросы к Microsoft Graph.

Манифест надстройки содержит разметку, которая указывает, как надстройка регистрируется в конечной точке Azure Active Directory (Azure AD) версии 2.0, а также задает необходимые надстройке разрешения для Microsoft Graph.

### <a name="how-it-works-at-runtime"></a>Принцип работы во время выполнения

На приведенной ниже схеме показан процесс входа в систему и получения доступа к Microsoft Graph.

![Схема единого входа](../images/sso-access-to-microsoft-graph.png)

1. Код JavaScript надстройки вызывает новый API Office.js — [getAccessToken](/javascript/api/office-runtime/officeruntime.auth#getaccesstoken-options-). Это указывает клиентскому приложению Office, что необходимо получить маркер доступа к надстройке. (Далее он будет называться **маркером доступа к начальной загрузке**, поскольку в этом процессе он позже будет заменен вторым маркером. Пример раскодированного маркера доступа к начальной загрузке см. в разделе [Пример маркера доступа](sso-in-office-add-ins.md#example-access-token)).
2. Если пользователь не выполнил вход, клиентское приложение Office открывает всплывающее окно, в котором пользователь может войти в систему.
3. Если пользователь запускает надстройку в первый раз, ему предлагается дать согласие.
4. Клиентское приложение Office запрашивает **маркер доступа к начальной** загрузке из конечной точки Azure AD версии 2.0 для текущего пользователя.
5. Azure AD отправляет маркер начальной загрузки клиентскому приложению Office.
6. Клиентское приложение Office отправляет **маркер доступа к начальной** загрузке надстройке в составе объекта результата, возвращенного `getAccessToken` вызовом.
7. Код JavaScript надстройки отправляет HTTP-запрос к веб-API с тем же полным доменным именем, что и у надстройки. Этот запрос включает **маркер доступа к начальной загрузке** в качестве подтверждения авторизации.
8. Серверный код проверяет входящий **маркер доступа к начальной загрузке**.
9. Серверный код использует для получения маркера доступа к начальной загрузке маркер "от имени" (определенный на сервере [OAuth2 Token](https://tools.ietf.org/html/draft-ietf-oauth-token-exchange-02) ), а также [сценарий демона или серверное приложение для веб-API Azure](/azure/active-directory/develop/active-directory-authentication-scenarios)) для получения маркера доступа для Microsoft Graph в Exchange.
10. Azure AD возвращает надстройке маркер доступа в Microsoft Graph (и маркер обновления, если надстройка запрашивает разрешение *offline_access*).
11. Серверный код кэширует маркер доступа в Microsoft Graph.
12. Серверный код отправляет запросы к Microsoft Graph и включает маркер доступа в Microsoft Graph.
13. Microsoft Graph возвращает данные в надстройку, которая может передать ее в пользовательский интерфейс надстройки.
14. Когда маркер доступа в Microsoft Graph истекает, серверный код может использовать свой маркер обновления, чтобы получить новый маркер доступа в Microsoft Graph.

## <a name="develop-an-sso-add-in-that-accesses-microsoft-graph"></a>Разработка надстройки с единым входом для Microsoft Graph

Надстройка с доступом в Microsoft Graph разрабатывается так же, как и любая другая надстройка с единым входом. Подробное описание см. в статье [Включение единого входа для надстроек Office](../develop/sso-in-office-add-ins.md). Разница заключается в том, что у надстройки обязательно должен быть серверный веб-API, а также в использовании термина "маркер доступа к начальной загрузке" вместо термина "маркер доступа" из указанной статьи.

В зависимости от языка и платформы могут быть доступны библиотеки, которые упростят создание серверного кода. Ваш код должен выполнять следующее:

* Инициируйте потоки "от имени" с вызовом конечной точки Azure AD версии 2.0, которая включает маркер доступа к начальной загрузке, некоторые метаданные пользователя и учетные данные надстройки (ее идентификатор и секрет).
* создать один или несколько методов веб-API, которые получают данные Microsoft Graph, передавая (возможно кэшированный) маркер доступа в Microsoft Graph.
* при необходимости перед запуском потока проверять маркер доступа к начальной загрузке надстройки, полученный от созданного ранее обработчика маркеров. Дополнительные сведения см. в разделе [Проверка маркера доступа](sso-in-office-add-ins.md#validate-the-access-token); 
* при необходимости после завершения потока поместить в кэш возвращенный маркер доступа к Microsoft Graph. Это рекомендуется делать, если надстройка выполняет несколько вызовов в Microsoft Graph. Дополнительные сведения об этом потоке см. в статье [Azure Active Directory версии 2.0 и поток "от имени" OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-on-behalf-of);

> [!NOTE]
> Примеры раскодированных маркеров доступа в Microsoft Graph, которые были получены потоком "от имени", см. в статье [Azure Active Directory версии 2.0 и поток "от имени" OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-on-behalf-of).

Подробные пошаговые инструкции и сценарии см. в следующих статьях:

* [Создание надстройки Office на платформе Node.js с использованием единого входа](create-sso-office-add-ins-nodejs.md)
* [Создание надстройки Office на платформе ASP.NET с использованием единого входа](create-sso-office-add-ins-aspnet.md)
* [Сценарий: реализация единого входа для службы в надстройке Outlook](../outlook/implement-sso-in-outlook-add-in.md)

## <a name="distributing-sso-enabled-add-ins-in-microsoft-appsource"></a>Распространение надстроек с включенной поддержкой единого входа в Microsoft AppSource

Когда администратор Microsoft 365 получает надстройку от [AppSource](https://appsource.microsoft.com), администратор может перераспределить его с помощью [централизованного развертывания](../publish/centralized-deployment.md) и предоставить надстройке разрешение администратора для доступа к областям Microsoft Graph. Тем не менее, для конечного пользователя также можно получить надстройку непосредственно из AppSource, в этом случае пользователь должен предоставить согласие на надстройку. Это может создать потенциальную проблему с производительностью, для которой мы предоставили решение.

Если ваш код передает `allowConsentPrompt` параметр в вызове `getAccessToken` , например `OfficeRuntime.auth.getAccessToken( { allowConsentPrompt: true } );` , Office может запросить разрешение у пользователя, если вы получаете отчеты Azure AD в Office, что согласие еще не было предоставлено надстройке. Однако из соображений безопасности Office может запрашивать у пользователя согласие только на область Azure AD `profile` . *Office не может запрашивать согласие на любые области Microsoft Graph*, а не даже `User.Read` . Это означает, что если пользователь предоставит согласие на запрос, Office возвратит маркер начальной загрузки. Но попытка Exchange маркера начальной загрузки для маркера доступа к Microsoft Graph завершится с ошибкой AADSTS65001, что означает, что разрешение (в областях Microsoft Graph) не было предоставлено.

Ваш код может, а также обрабатывать эту ошибку, возвращающую альтернативную систему проверки подлинности, которая предложит пользователю предоставить разрешения для областей Microsoft Graph. (Примеры кода: создание надстройки [office Node.js, использующей единый вход](create-sso-office-add-ins-nodejs.md) , и [Создание надстройки Office ASP.NET, которая использует единый вход](create-sso-office-add-ins-aspnet.md) , и образцы, на которые они ссылаются.) Но весь процесс требует нескольких циклов обработки в Azure AD. Можно избежать этого снижения производительности, включив `forMSGraphAccess` параметр в вызове `getAccessToken` , например `OfficeRuntime.auth.getAccessToken( { forMSGraphAccess: true } )` .  Это означает, что вашей надстройке требуются области Microsoft Graph. Office запросит Azure AD, чтобы убедиться в том, что эта надстройка уже предоставила разрешения для областей Microsoft Graph. Если это так, будет возвращен маркер начальной загрузки. В противном случае вызов возвратит `getAccessToken` ошибку 13012. Код может обработать эту ошибку, вернувшись обратно в альтернативную систему проверки подлинности немедленно, не предоставляя думед для обмена токенами с Azure AD.

Рекомендуется всегда передаваться в то `forMSGraphAccess` `getAccessToken` время, когда ваша надстройка будет распространяться в AppSource и нуждается в областях Microsoft Graph.

> [!TIP]
> Если вы разрабатываете надстройку Outlook, использующую единый вход, и Загрузка неопубликованных ее для тестирования, Office *всегда* возвращает сообщение об ошибке 13012, если оно будет `forMSGraphAccess` передано, `getAccessToken` даже если предоставлено согласие администратора. По этой причине следует закомментировать `forMSGraphAccess` параметр **при разработке** надстройки Outlook. При развертывании в рабочей среде обязательно раскомментируйте параметр. Поддельный 13012 возникает только при наличии неопубликованных приложений в Outlook.
