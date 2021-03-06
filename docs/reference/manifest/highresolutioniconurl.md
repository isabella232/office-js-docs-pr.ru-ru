---
title: Элемент HighResolutionIconUrl в файле манифеста
description: Указывает URL-адрес изображения, которое используется для представления надстройки Office в пользовательском интерфейсе вставки и Магазине Office на экранах с высоким DPI.
ms.date: 12/04/2018
localization_priority: Normal
ms.openlocfilehash: 77675e768895a568bdfee97fc4d5006e1e890937
ms.sourcegitcommit: cc6886b47c84ac37a3c957ff85dd0ed526ca5e43
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46641356"
---
# <a name="highresolutioniconurl-element"></a>Элемент HighResolutionIconUrl

Указывает URL-адрес изображения, которое используется для представления надстройки Office в пользовательском интерфейсе вставки и Магазине Office на экранах с высоким DPI.

**Тип надстройки:** контентные и почтовые надстройки, надстройки области задач.

## <a name="syntax"></a>Синтаксис

```XML
<HighResolutionIconUrl DefaultValue="string" />
```

## <a name="can-contain"></a>Может содержать:

[Override](override.md)

## <a name="attributes"></a>Атрибуты

|Атрибут|Тип|Обязательный|Описание|
|:-----|:-----|:-----|:-----|
|DefaultValue|string (URL-адрес)|Обязательный|Задает значение по умолчанию для этого параметра, представленное для языкового стандарта, который указан с помощью элемента [DefaultLocale](defaultlocale.md).|

## <a name="remarks"></a>Замечания

Для почтовой надстройки значок **отображается в**  >  пользовательском интерфейсе**Управление надстройками** . Значок надстройки области задач или контентной надстройки отображается в разделе **Вставка** > **Надстройки**.

Изображение должно быть в формате GIF, JPG, PNG, EXIF, BMP или TIFF. Для приложений области задач и приложений для работы с контентом рекомендуется размер изображения 64 х 64 пикселя. Для почтовых приложений изображение должно иметь размер 128 x 128 пикселей. Дополнительные сведения см. в разделе _Создание согласованного визуального образа приложения_ статьи [Создание эффективных описаний в AppSource и в Office](/office/dev/store/create-effective-office-store-listings#create-a-consistent-visual-identity).
