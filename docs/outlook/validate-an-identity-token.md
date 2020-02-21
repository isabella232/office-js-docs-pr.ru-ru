---
title: Проверка маркера удостоверения надстройки Outlook
description: Надстройка Outlook может отправить вам маркер удостоверения пользователя Exchange, но прежде чем обращаться с запросом как с доверенным, нужно проверить, поступил ли маркер с ожидаемого сервера Exchange Server.
ms.date: 11/07/2019
localization_priority: Normal
ms.openlocfilehash: b412756a980d54a20a1c8deab43cd7634c0188cb
ms.sourcegitcommit: a3ddfdb8a95477850148c4177e20e56a8673517c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42166742"
---
# <a name="validate-an-exchange-identity-token"></a><span data-ttu-id="a5b09-103">Проверка маркера удостоверения Exchange</span><span class="sxs-lookup"><span data-stu-id="a5b09-103">Validate an Exchange identity token</span></span>

<span data-ttu-id="a5b09-104">Надстройка Outlook может отправить вам маркер удостоверения пользователя Exchange, но прежде чем обращаться с запросом как с доверенным, нужно проверить, поступил ли маркер с ожидаемого сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="a5b09-104">Your Outlook add-in can send you an Exchange user identity token, but before you trust the request you must validate the token to ensure that it came from the Exchange server that you expect.</span></span> <span data-ttu-id="a5b09-105">Маркеры удостоверений пользователей Exchange представляют собой маркеры JSON Web Token (JWT).</span><span class="sxs-lookup"><span data-stu-id="a5b09-105">Exchange user identity tokens are JSON Web Tokens (JWT).</span></span> <span data-ttu-id="a5b09-106">Инструкции по проверке JWT представлены в документе [RFC 7519 JSON Web Token (JWT)](https://www.rfc-editor.org/rfc/rfc7519.txt).</span><span class="sxs-lookup"><span data-stu-id="a5b09-106">The steps required to validate a JWT are described in [RFC 7519 JSON Web Token (JWT)](https://www.rfc-editor.org/rfc/rfc7519.txt).</span></span>

<span data-ttu-id="a5b09-107">Рекомендуем использовать процесс, состоящий из четырех этапов, для проверки маркера удостоверения и получения уникального идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5b09-107">We suggest that you use a four-step process to validate the identity token and obtain the user's unique identifier.</span></span> <span data-ttu-id="a5b09-108">Первый этап: извлечение веб-маркера JSON (JWT) из строки, закодированной в формате URL-адреса Base64.</span><span class="sxs-lookup"><span data-stu-id="a5b09-108">First, extract the JSON Web Token (JWT) from a base64 URL-encoded string.</span></span> <span data-ttu-id="a5b09-109">Второй этап: проверка правильности маркера, то есть его предназначения для вашей надстройки Outlook, его актуальности и возможности извлечения допустимого URL-адреса для документа метаданных проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a5b09-109">Second, make sure that the token is well-formed, that it is for your Outlook add-in, that it has not expired, and that you can extract a valid URL for the authentication metadata document.</span></span> <span data-ttu-id="a5b09-110">Затем необходимо получить документ метаданных проверки подлинности с сервера Exchange и проверить подпись, приложенную к маркеру удостоверения.</span><span class="sxs-lookup"><span data-stu-id="a5b09-110">Next, retrieve the authentication metadata document from the Exchange server and validate the signature attached to the identity token.</span></span> <span data-ttu-id="a5b09-111">Наконец, вычислите уникальный идентификатор для пользователя, объединяя идентификатор Exchange пользователя с URL-адресом документа с метаданными проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a5b09-111">Finally, compute a unique identifier for the user by concatenating the user's Exchange ID with the URL of the authentication metadata document.</span></span>

## <a name="extract-the-json-web-token"></a><span data-ttu-id="a5b09-112">Извлечение маркера JSON Web Token</span><span class="sxs-lookup"><span data-stu-id="a5b09-112">Extract the JSON Web Token</span></span>

<span data-ttu-id="a5b09-113">Маркер, возвращаемый методом [getUserIdentityTokenAsync](../reference/objectmodel/preview-requirement-set/office.context.mailbox.md#methods), — это закодированная строка, представляющая его.</span><span class="sxs-lookup"><span data-stu-id="a5b09-113">The token returned from [getUserIdentityTokenAsync](../reference/objectmodel/preview-requirement-set/office.context.mailbox.md#methods) is an encoded string representation of the token.</span></span> <span data-ttu-id="a5b09-114">В этом формате (согласно стандарту RFC 7519) все маркеры JWT состоят из трех частей, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="a5b09-114">In this form, per RFC 7519, all JWTs have three parts, separated by a period.</span></span> <span data-ttu-id="a5b09-115">Используется приведенный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="a5b09-115">The format is as follows.</span></span>

```json
{header}.{payload}.{signature}
```

<span data-ttu-id="a5b09-116">Чтобы получить представление каждой части в формате JSON, необходимо раскодировать заголовок и полезные данные согласно кодировке Base64.</span><span class="sxs-lookup"><span data-stu-id="a5b09-116">The header and payload should be base64-decoded to obtain a JSON representation of each part.</span></span> <span data-ttu-id="a5b09-117">Подпись необходимо расшифровать согласно кодировке Base64, чтобы получить массив байтов, содержащий двоичную подпись.</span><span class="sxs-lookup"><span data-stu-id="a5b09-117">The signature should be base64-decoded to obtain a byte array containing the binary signature.</span></span>

<span data-ttu-id="a5b09-118">Дополнительные сведения о содержимом маркера см. в статье [Подробные сведения о маркере удостоверения Exchange](inside-the-identity-token.md).</span><span class="sxs-lookup"><span data-stu-id="a5b09-118">For more information about the contents of the token, see [Inside the Exchange identity token](inside-the-identity-token.md).</span></span>

<span data-ttu-id="a5b09-119">После получения трех раскодированных компонентов можно продолжать проверку содержимого маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-119">After you have the three decoded components, you can proceed with validating the content of the token.</span></span>

## <a name="validate-token-contents"></a><span data-ttu-id="a5b09-120">Проверка содержимого маркера</span><span class="sxs-lookup"><span data-stu-id="a5b09-120">Validate token contents</span></span>

<span data-ttu-id="a5b09-121">Для проверки содержимого маркера необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a5b09-121">To validate the token contents, you should check the following.</span></span>

- <span data-ttu-id="a5b09-122">Проверьте заголовок и убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="a5b09-122">Check the header and verify that the:</span></span>
    - <span data-ttu-id="a5b09-123">`typ`для `JWT`утверждения задано значение.</span><span class="sxs-lookup"><span data-stu-id="a5b09-123">`typ` claim is set to `JWT`.</span></span>
    - <span data-ttu-id="a5b09-124">`alg`для `RS256`утверждения задано значение.</span><span class="sxs-lookup"><span data-stu-id="a5b09-124">`alg` claim is set to `RS256`.</span></span>
    - <span data-ttu-id="a5b09-125">`x5t`присутствует утверждение.</span><span class="sxs-lookup"><span data-stu-id="a5b09-125">`x5t` claim is present.</span></span>

- <span data-ttu-id="a5b09-126">Проверьте полезную нагрузку и убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="a5b09-126">Check the payload and verify that the:</span></span>
    - <span data-ttu-id="a5b09-127">`amurl`в параметре `appctx` Claims in the указывается расположение подписанного файла манифеста подписанного маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-127">`amurl` claim inside the `appctx` is set to the location of an authorized token signing key manifest file.</span></span> <span data-ttu-id="a5b09-128">Например, ожидаемое `amurl` значение для Office 365: https://outlook.office365.com:443/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="a5b09-128">For example, the expected `amurl` value for Office 365 is https://outlook.office365.com:443/autodiscover/metadata/json/1.</span></span> <span data-ttu-id="a5b09-129">В следующем разделе [проверяйте домен](#verify-the-domain) на наличие дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="a5b09-129">See the next section [Verify the domain](#verify-the-domain) for additional information.</span></span>
    - <span data-ttu-id="a5b09-130">Текущее время находится в промежутке между значениями, `nbf` указанными в утверждениях и `exp` .</span><span class="sxs-lookup"><span data-stu-id="a5b09-130">Current time is between the times specified in the `nbf` and `exp` claims.</span></span> <span data-ttu-id="a5b09-131">В утверждении `nbf` указано время, с которого начинается срок действия маркера, а в утверждении `exp` — время его окончания.</span><span class="sxs-lookup"><span data-stu-id="a5b09-131">The `nbf` claim specifies the earliest time that the token is considered valid, and the `exp` claim specifies the expiration time for the token.</span></span> <span data-ttu-id="a5b09-132">Рекомендуем допускать небольшие различия в заданном времени на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="a5b09-132">It is recommended to allow for some variation in clock settings between servers.</span></span>
    - <span data-ttu-id="a5b09-133">`aud`Claim — это ожидаемый URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="a5b09-133">`aud` claim is the expected URL for your add-in.</span></span>
    - <span data-ttu-id="a5b09-134">`version`для `ExIdTok.V1`утверждения в `appctx` утверждении задано значение.</span><span class="sxs-lookup"><span data-stu-id="a5b09-134">`version` claim inside the `appctx` claim is set to `ExIdTok.V1`.</span></span>

### <a name="verify-the-domain"></a><span data-ttu-id="a5b09-135">Проверка домена</span><span class="sxs-lookup"><span data-stu-id="a5b09-135">Verify the domain</span></span>

<span data-ttu-id="a5b09-136">При реализации логики проверки, описанной ранее в этом разделе, необходимо также указать, чтобы домен `amurl` утверждения соответствовал домену автообнаружения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5b09-136">When implementing the verification logic described previously in this section, you should also require that the domain of the `amurl` claim matches the Autodiscover domain for the user.</span></span> <span data-ttu-id="a5b09-137">Для этого необходимо использовать или реализовать службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a5b09-137">To do so, you'll need to use or implement Autodiscover.</span></span> <span data-ttu-id="a5b09-138">Чтобы узнать больше, можно запустить службу [автообнаружения для Exchange](/exchange/client-developer/exchange-web-services/autodiscover-for-exchange).</span><span class="sxs-lookup"><span data-stu-id="a5b09-138">To learn more, you can start with [Autodiscover for Exchange](/exchange/client-developer/exchange-web-services/autodiscover-for-exchange).</span></span>

## <a name="validate-the-identity-token-signature"></a><span data-ttu-id="a5b09-139">Проверка подписи маркера удостоверения</span><span class="sxs-lookup"><span data-stu-id="a5b09-139">Validate the identity token signature</span></span>

<span data-ttu-id="a5b09-140">Когда вы убедитесь, что JWT содержит необходимые утверждения, можно переходить к проверке подписи маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-140">After you know that the JWT contains the required claims, you can proceed with validating the token signature.</span></span>

### <a name="retrieve-the-public-signing-key"></a><span data-ttu-id="a5b09-141">Получение открытого ключа подписывания</span><span class="sxs-lookup"><span data-stu-id="a5b09-141">Retrieve the public signing key</span></span>

<span data-ttu-id="a5b09-142">Первый этап — получение открытого ключа, соответствующего сертификату, который сервер Exchange Server использовал для подписывания маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-142">The first step is to retrieve the public key that corresponds to the certificate that the Exchange server used to sign the token.</span></span> <span data-ttu-id="a5b09-143">Этот ключ указан в документе с метаданными проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a5b09-143">The key is found in the authentication metadata document.</span></span> <span data-ttu-id="a5b09-144">Этот документ представляет собой JSON-файл, размещенный по URL-адресу, указанному в утверждении `amurl`.</span><span class="sxs-lookup"><span data-stu-id="a5b09-144">This document is a JSON file hosted at the URL specified in the `amurl` claim.</span></span>

<span data-ttu-id="a5b09-145">Документ с метаданными проверки подлинности имеет приведенный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="a5b09-145">The authentication metadata document uses the following format.</span></span>

```json
{
    "id": "_70b34511-d105-4e2b-9675-39f53305bb01",
    "version": "1.0",
    "name": "Exchange",
    "realm": "*",
    "serviceName": "00000002-0000-0ff1-ce00-000000000000",
    "issuer": "00000002-0000-0ff1-ce00-000000000000@*",
    "allowedAudiences": [
        "00000002-0000-0ff1-ce00-000000000000@*"
    ],
    "keys": [
        {
            "usage": "signing",
            "keyinfo": {
                "x5t": "enh9BJrVPU5ijV1qjZjV-fL2bco"
            },
            "keyvalue": {
                "type": "x509Certificate",
                "value": "MIIHNTCC..."
            }
        }
    ],
    "endpoints": [
        {
            "location": "https://by2pr06mb2229.namprd06.prod.outlook.com:444/autodiscover/metadata/json/1",
            "protocol": "OAuth2",
            "usage": "metadata"
        }
    ]
}
```

<span data-ttu-id="a5b09-146">Доступные ключи подписывания находятся в массиве `keys`.</span><span class="sxs-lookup"><span data-stu-id="a5b09-146">The available signing keys are in the `keys` array.</span></span> <span data-ttu-id="a5b09-147">Выберите подходящий ключ, убедившись, что значение `x5t` в свойстве `keyinfo` совпадает со значением `x5t` в заголовке маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-147">Select the correct key by ensuring that the `x5t` value in the `keyinfo` property matches the `x5t` value in the header of the token.</span></span> <span data-ttu-id="a5b09-148">Открытый ключ находится в дочернем свойстве `value` свойства `keyvalue`, хранящемся в массиве байтов с кодировкой Base64.</span><span class="sxs-lookup"><span data-stu-id="a5b09-148">The public key is inside the `value` property in the `keyvalue` property, stored as a base64-encoded byte array.</span></span>

<span data-ttu-id="a5b09-149">После получения правильного открытого ключа проверьте подпись.</span><span class="sxs-lookup"><span data-stu-id="a5b09-149">After you have the correct public key, verify the signature.</span></span> <span data-ttu-id="a5b09-150">Подписанные данные представляют собой первые две части закодированного маркера, разделенные точкой:</span><span class="sxs-lookup"><span data-stu-id="a5b09-150">The signed data is the first two parts of the encoded token, separated by a period:</span></span>

```json
{header}.{payload}
```

## <a name="compute-the-unique-id-for-an-exchange-account"></a><span data-ttu-id="a5b09-151">Вычисление уникального идентификатора для учетной записи Exchange</span><span class="sxs-lookup"><span data-stu-id="a5b09-151">Compute the unique ID for an Exchange account</span></span>

<span data-ttu-id="a5b09-152">Вы можете создать уникальный идентификатор для учетной записи Exchange, объединяя URL-адрес документа метаданных проверки подлинности с идентификатором Exchange для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a5b09-152">You can create a unique identifier for an Exchange account by concatenating the authentication metadata document URL with the Exchange identifier for the account.</span></span> <span data-ttu-id="a5b09-153">Получив этот уникальный идентификатор, вы можете создать систему единого входа для веб-службы надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="a5b09-153">When you have this unique identifier, you can use it to create a single sign-on (SSO) system for your Outlook add-in web service.</span></span> <span data-ttu-id="a5b09-154">Дополнительные сведения об использовании уникального идентификатора для единого входа см. в статье [Проверка подлинности пользователя с помощью маркера удостоверения для Exchange](authenticate-a-user-with-an-identity-token.md).</span><span class="sxs-lookup"><span data-stu-id="a5b09-154">For details about using the unique identifier for SSO, see [Authenticate a user with an identity token for Exchange](authenticate-a-user-with-an-identity-token.md).</span></span>

## <a name="use-a-library-to-validate-the-token"></a><span data-ttu-id="a5b09-155">Проверка маркера с помощью библиотеки</span><span class="sxs-lookup"><span data-stu-id="a5b09-155">Use a library to validate the token</span></span>

<span data-ttu-id="a5b09-156">Существует ряд библиотек, способных выполнять общие задачи анализа и проверки JWT.</span><span class="sxs-lookup"><span data-stu-id="a5b09-156">There are a number of libraries that can do general JWT parsing and validation.</span></span> <span data-ttu-id="a5b09-157">Корпорация Майкрософт предоставляет две библиотеки, с помощью которых можно проверять маркеры удостоверений пользователей Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5b09-157">Microsoft provides two libraries that can be used to validate Exchange user identity tokens.</span></span>

### <a name="systemidentitymodeltokensjwt"></a><span data-ttu-id="a5b09-158">System.IdentityModel.Tokens.Jwt</span><span class="sxs-lookup"><span data-stu-id="a5b09-158">System.IdentityModel.Tokens.Jwt</span></span>

<span data-ttu-id="a5b09-159">Библиотека [System.IdentityModels.Tokens.Jwt](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt) может анализировать маркер, а также выполнять проверку, но вам потребуется самостоятельно проанализировать утверждение `appctx` и получить открытый ключ подписывания.</span><span class="sxs-lookup"><span data-stu-id="a5b09-159">The [System.IdentityModels.Tokens.Jwt](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt) library can parse the token and also perform the validation, though you will need to parse the `appctx` claim yourself and retrieve the public signing key.</span></span>

```cs
// Load the encoded token
string encodedToken = "...";
JwtSecurityToken jwt = new JwtSecurityToken(encodedToken);

// Parse the appctx claim to get the auth metadata url
string authMetadataUrl = string.Empty;
var appctx = jwt.Claims.FirstOrDefault(claim => claim.Type == "appctx");
if (appctx != null)
{
    var AppContext = JsonConvert.DeserializeObject<ExchangeAppContext>(appctx.Value);

    // Token version check
    if (string.Compare(AppContext.Version, "ExIdTok.V1", StringComparison.InvariantCulture) != 0) {
        // Fail validation
    }

    authMetadataUrl = AppContext.MetadataUrl;
}

// Use System.IdentityModel.Tokens.Jwt library to validate standard parts
JwtSecurityTokenHandler tokenHandler = new JwtSecurityTokenHandler();
TokenValidationParameters tvp = new TokenValidationParameters();

tvp.ValidateIssuer = false;
tvp.ValidateAudience = true;
tvp.ValidAudience = "{URL to add-in}";
tvp.ValidateIssuerSigningKey = true;
// GetSigningKeys downloads the auth metadata doc and
// returns a List<SecurityKey>
tvp.IssuerSigningKeys = GetSigningKeys(authMetadataUrl);
tvp.ValidateLifetime = true;

try
{
    var claimsPrincipal = tokenHandler.ValidateToken(encodedToken, tvp, out SecurityToken validatedToken);

    // If no exception, all standard checks passed
}
catch (SecurityTokenValidationException ex)
{
    // Validation failed
}
```

<br/>

<span data-ttu-id="a5b09-160">Класс `ExchangeAppContext` определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a5b09-160">The `ExchangeAppContext` class is defined as follows:</span></span>

```cs
using Newtonsoft.Json;

/// <summary>
/// Representation of the appctx claim in an Exchange user identity token.
/// </summary>
public class ExchangeAppContext
{
    /// <summary>
    /// The Exchange identifier for the user
    /// </summary>
    [JsonProperty("msexchuid")]
    public string ExchangeUid { get; set; }

    /// <summary>
    /// The token version
    /// </summary>
    public string Version { get; set; }

    /// <summary>
    /// The URL to download authentication metadata
    /// </summary>
    [JsonProperty("amurl")]
    public string MetadataUrl { get; set; }
}
```

<span data-ttu-id="a5b09-161">Пример проверки маркеров Exchange с помощью этой библиотеки, в котором также реализован метод `GetSigningKeys`: [Outlook-Add-In-Token-Viewer](https://github.com/OfficeDev/Outlook-Add-In-Token-Viewer).</span><span class="sxs-lookup"><span data-stu-id="a5b09-161">For an example that uses this library to validate Exchange tokens and has an implementation of `GetSigningKeys`, see [Outlook-Add-In-Token-Viewer](https://github.com/OfficeDev/Outlook-Add-In-Token-Viewer).</span></span>

### <a name="microsoftexchangewebservices"></a><span data-ttu-id="a5b09-162">Microsoft.Exchange.WebServices</span><span class="sxs-lookup"><span data-stu-id="a5b09-162">Microsoft.Exchange.WebServices</span></span>

<span data-ttu-id="a5b09-163">[Управляемый API веб-служб Exchange](https://www.nuget.org/packages/Microsoft.Exchange.WebServices/) также может проверять маркеры удостоверений пользователей Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5b09-163">The [Exchange Web Services Managed API](https://www.nuget.org/packages/Microsoft.Exchange.WebServices/) can also validate Exchange user identity tokens.</span></span> <span data-ttu-id="a5b09-164">Так как он предназначен только для Exchange, в нем реализована вся необходимая логика для анализа утверждения `appctx` и проверки версии маркера.</span><span class="sxs-lookup"><span data-stu-id="a5b09-164">Because it is Exchange-specific, it implements all of the necessary logic to parse the `appctx` claim and verify the token version.</span></span>

```cs
using Microsoft.Exchange.WebServices.Auth.Validation;

AppIdentityToken ValidateIdentityToken(string rawToken, string expectedAudience)
{
    try
    {
        AppIdentityToken appIdToken = AuthToken.Parse(rawToken) as AppIdentityToken;
        appIdToken.Validate(new Uri(expectedAudience));

        // No exception, validation succeeded
        return appIdToken;
    }
    catch (TokenValidationException ex)
    {
        throw new Exception(string.Format("Token validation failed: {0}", ex.Message));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a5b09-165">См. также</span><span class="sxs-lookup"><span data-stu-id="a5b09-165">See also</span></span>

- [<span data-ttu-id="a5b09-166">Outlook-Add-In-Token-Viewer</span><span class="sxs-lookup"><span data-stu-id="a5b09-166">Outlook-Add-In-Token-Viewer</span></span>](https://github.com/OfficeDev/Outlook-Add-In-Token-Viewer)
- [<span data-ttu-id="a5b09-167">Outlook-Add-in-JavaScript-ValidateIdentityToken</span><span class="sxs-lookup"><span data-stu-id="a5b09-167">Outlook-Add-in-JavaScript-ValidateIdentityToken</span></span>](https://github.com/OfficeDev/Outlook-Add-in-JavaScript-ValidateIdentityToken)