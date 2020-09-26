---
title: Открытие набора обязательных элементов окна браузера
description: Указывает, какие платформы и сборки Office поддерживают API Опенбровсервиндов.
ms.date: 09/16/2020
ms.prod: non-product-specific
localization_priority: Normal
ms.openlocfilehash: 8bc26525bf64ed87d46d85cd1248f79696d67f2b
ms.sourcegitcommit: 4a03d8b3f676ee2d91114813cb81bce5da3c8d6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48175509"
---
# <a name="open-browser-window-api-requirement-sets"></a><span data-ttu-id="60883-103">Наборы обязательных элементов API окна браузера</span><span class="sxs-lookup"><span data-stu-id="60883-103">Open Browser Window API requirement sets</span></span>

<span data-ttu-id="60883-p101">Наборы обязательных элементов — именованные группы элементов API. Надстройки Office с помощью наборов обязательных элементов, указанных в манифесте, или проверки в среде выполнения определяют, поддерживает ли ведущее приложение Office необходимые API. Дополнительные сведения см. в статье [Версии Office и наборы обязательных элементов](../../develop/office-versions-and-requirement-sets.md).</span><span class="sxs-lookup"><span data-stu-id="60883-p101">Requirement sets are named groups of API members. Office Add-ins use requirement sets specified in the manifest or use a runtime check to determine whether an Office host supports APIs that an add-in needs. For more information, see [Office versions and requirement sets](../../develop/office-versions-and-requirement-sets.md).</span></span>

<span data-ttu-id="60883-107">Набор API Опенбровсервиндов позволяет надстройкам открывать браузер для выполнения задач, которые не всегда можно выполнить в изолированном элементе управления вебвиев внутри надстройки; Например, Загрузка PDF-файла, когда элемент управления вебвиев предоставляется Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="60883-107">The OpenBrowserWindow API set enables add-ins to open a browser to accomplish tasks that cannot always be done in the sandboxed webview control within the add-in itself; for example, downloading a PDF file when the webview control is provided by Microsoft Edge.</span></span>

<span data-ttu-id="60883-108">Надстройки Office работают в нескольких версиях Office.</span><span class="sxs-lookup"><span data-stu-id="60883-108">Office Add-ins run across multiple versions of Office.</span></span> <span data-ttu-id="60883-109">В следующей таблице перечислены наборы требований API Опенбровсервиндов, ведущие приложения Office, которые поддерживают этот набор требований, а также номера сборок или версий для приложения Office.</span><span class="sxs-lookup"><span data-stu-id="60883-109">The following table lists the OpenBrowserWindow API requirement sets, the Office host applications that support that requirement set, and the build or version numbers for the Office application.</span></span>

|  <span data-ttu-id="60883-110">Набор обязательных элементов</span><span class="sxs-lookup"><span data-stu-id="60883-110">Requirement set</span></span>  | <span data-ttu-id="60883-111">Office 2013 в Windows или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="60883-111">Office 2013 on Windows or later</span></span><br><span data-ttu-id="60883-112">(единовременная покупка)</span><span class="sxs-lookup"><span data-stu-id="60883-112">(one-time purchase)</span></span> | <span data-ttu-id="60883-113">Office для Windows</span><span class="sxs-lookup"><span data-stu-id="60883-113">Office on Windows</span></span><br><span data-ttu-id="60883-114">(версия, подключенная к подписке на Office 365)</span><span class="sxs-lookup"><span data-stu-id="60883-114">(connected to Office 365 subscription)</span></span> |  <span data-ttu-id="60883-115">Office для iPad</span><span class="sxs-lookup"><span data-stu-id="60883-115">Office on iPad</span></span><br><span data-ttu-id="60883-116">(версия, подключенная к подписке на Office 365)</span><span class="sxs-lookup"><span data-stu-id="60883-116">(connected to Office 365 subscription)</span></span>  |  <span data-ttu-id="60883-117">Office для Mac</span><span class="sxs-lookup"><span data-stu-id="60883-117">Office on Mac</span></span><br><span data-ttu-id="60883-118">(версия, подключенная к подписке на Office 365)</span><span class="sxs-lookup"><span data-stu-id="60883-118">(connected to Office 365 subscription)</span></span>  | <span data-ttu-id="60883-119">Office в Интернете</span><span class="sxs-lookup"><span data-stu-id="60883-119">Office on the web</span></span>  |  <span data-ttu-id="60883-120">Office Online Server</span><span class="sxs-lookup"><span data-stu-id="60883-120">Office Online Server</span></span>  |
|:-----|-----|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="60883-121">Опенбровсервиндовапи 1,1</span><span class="sxs-lookup"><span data-stu-id="60883-121">OpenBrowserWindowApi 1.1</span></span>  | <span data-ttu-id="60883-122">Недоступно</span><span class="sxs-lookup"><span data-stu-id="60883-122">N/A</span></span> | <span data-ttu-id="60883-123">Версия 1810 (сборка 16.0.11001.20074) или более поздняя</span><span class="sxs-lookup"><span data-stu-id="60883-123">Version 1810 (Build 16.0.11001.20074) or later</span></span> | <span data-ttu-id="60883-124">16.0.0.0 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="60883-124">16.0.0.0 or later</span></span> | <span data-ttu-id="60883-125">16.0.0.0 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="60883-125">16.0.0.0 or later</span></span> | <span data-ttu-id="60883-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="60883-126">N/A</span></span> | <span data-ttu-id="60883-127">Н/Д</span><span class="sxs-lookup"><span data-stu-id="60883-127">N/A</span></span>|

<span data-ttu-id="60883-128">Статьи и разделы с дополнительными сведениями о версиях, номерах сборок и Office Online Server:</span><span class="sxs-lookup"><span data-stu-id="60883-128">To find out more about versions, build numbers, and Office Online Server, see:</span></span>

- <span data-ttu-id="60883-129">[Номера версий и сборок выпусков из канала обновления для клиентов Office 365](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7);</span><span class="sxs-lookup"><span data-stu-id="60883-129">[Version and build numbers of update channel releases for Office 365 clients](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)</span></span>
- <span data-ttu-id="60883-130">[Какая у меня версия Office](https://support.office.com/article/What-version-of-Office-am-I-using-932788b8-a3ce-44bf-bb09-e334518b8b19);</span><span class="sxs-lookup"><span data-stu-id="60883-130">[What version of Office am I using?](https://support.office.com/article/What-version-of-Office-am-I-using-932788b8-a3ce-44bf-bb09-e334518b8b19)</span></span>
- <span data-ttu-id="60883-131">[Где можно найти номера версии и сборки клиентского приложения Office 365](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7);</span><span class="sxs-lookup"><span data-stu-id="60883-131">[Where you can find the version and build number for an Office 365 client application](https://support.office.com/article/version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)</span></span>
- [<span data-ttu-id="60883-132">Обзор Office Online Server</span><span class="sxs-lookup"><span data-stu-id="60883-132">Office Online Server overview</span></span>](/officeonlineserver/office-online-server-overview)

## <a name="office-common-api-requirement-sets"></a><span data-ttu-id="60883-133">Наборы обязательных элементов общего API для Office</span><span class="sxs-lookup"><span data-stu-id="60883-133">Office Common API requirement sets</span></span>

<span data-ttu-id="60883-134">Сведения о наборах обязательных элементов общего API см. в статье [Наборы обязательных элементов общего API для Office](office-add-in-requirement-sets.md).</span><span class="sxs-lookup"><span data-stu-id="60883-134">For information about Common API requirement sets, see [Office Common API requirement sets](office-add-in-requirement-sets.md).</span></span>

## <a name="openbrowserwindowapi-11"></a><span data-ttu-id="60883-135">Опенбровсервиндовапи 1,1</span><span class="sxs-lookup"><span data-stu-id="60883-135">OpenBrowserWindowApi 1.1</span></span>

<span data-ttu-id="60883-136">Опенбровсервиндовапи 1,1 — это первая версия API.</span><span class="sxs-lookup"><span data-stu-id="60883-136">The OpenBrowserWindowApi 1.1 is the first version of the API.</span></span> <span data-ttu-id="60883-137">Более подробную информацию об API можно узнать в разделе [Office. Context. UI](/javascript/api/office/office.context#ui) .</span><span class="sxs-lookup"><span data-stu-id="60883-137">For details about the API, see the [Office.context.ui](/javascript/api/office/office.context#ui) reference topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="60883-138">См. также</span><span class="sxs-lookup"><span data-stu-id="60883-138">See also</span></span>

- [<span data-ttu-id="60883-139">Версии Office и наборы обязательных элементов</span><span class="sxs-lookup"><span data-stu-id="60883-139">Office versions and requirement sets</span></span>](../../develop/office-versions-and-requirement-sets.md)
- [<span data-ttu-id="60883-140">Указание ведущих приложений Office и обязательных элементов API</span><span class="sxs-lookup"><span data-stu-id="60883-140">Specify Office hosts and API requirements</span></span>](../../develop/specify-office-hosts-and-api-requirements.md)
- [<span data-ttu-id="60883-141">XML-манифест надстроек Office</span><span class="sxs-lookup"><span data-stu-id="60883-141">Office Add-ins XML manifest</span></span>](../../develop/add-in-manifests.md)