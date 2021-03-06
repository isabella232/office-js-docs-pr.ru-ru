---
title: Загрузка неопубликованных надстроек Office на iPad и Mac для тестирования
description: Протестируйте надстройку Office на iPad и Mac, не прополнив загрузку неопубликованных приложений.
ms.date: 09/02/2020
localization_priority: Normal
ms.openlocfilehash: 7c5e9542c6e6f9abc96defde389b9543421b8529
ms.sourcegitcommit: 604361e55dee45c7a5d34c2fa6937693c154fc24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47364060"
---
# <a name="sideload-office-add-ins-on-ipad-and-mac-for-testing"></a>Загрузка неопубликованных надстроек Office на iPad и Mac для тестирования

Чтобы проверить работу надстройки в Office для iOS, вы можете загрузить манифест неопубликованной надстройки на iPad с помощью iTunes или непосредственно в Office для Mac. Вы не сможете устанавливать точки останова и отлаживать код надстройки во время выполнения, но сможете проверить ее работу и убедиться, что интерфейс отображается правильно и его можно использовать.

## <a name="prerequisites-for-office-on-ios"></a>Предварительные требования (Office для iOS)

- Компьютер Windows или Mac, на котором установлено приложение [iTunes](https://www.apple.com/itunes/download/).
  > [!IMPORTANT]
  > Если вы используете macOS Каталина, [iTunes больше не будет доступен](https://support.apple.com/HT210200) , поэтому вам следует выполнить инструкции из раздела [Загрузка неопубликованных надстройки в Excel или Word на iPad с помощью macOS Каталина](#sideload-an-add-in-on-excel-or-word-on-ipad-using-macos-catalina) далее в этой статье.

- IPad под управлением iOS 8,2 или более поздней версии с установленными [приложением Excel](https://apps.apple.com/app/microsoft-excel/id586683407) или [Word](https://apps.apple.com/app/microsoft-word/id586447913) и кабелем синхронизации.

- XML-файл манифеста для надстройки, которую вы хотите протестировать.

## <a name="prerequisites-for-office-on-mac"></a>Предварительные требования (Office для Mac)

- Компьютер Mac под управлением OS X 10.10 Yosemite или более поздней версии с установленным набором [Office для Mac](https://products.office.com/buy/compare-microsoft-office-products?tab=omac).

- Word для Mac версии 15.18 (160109).

- Excel для Mac версии 15.19 (160206).

- PowerPoint для Mac версии 15.24 (160614)

- XML-файл манифеста для надстройки, которую вы хотите протестировать.

## <a name="sideload-an-add-in-on-excel-or-word-on-ipad-using-itunes"></a>Загрузка неопубликованных надстройку в Excel или Word на iPad с помощью iTunes

1. Подключите iPad к компьютеру с помощью кабеля для синхронизации. Если вы подключаете iPad к компьютеру в первый раз, вам будет предложено **доверять этому компьютеру?**. Выберите **Доверять**.

2. В iTunes под строкой меню выберите значок **iPad**.

3. В левой части iTunes в разделе **Параметры** выберите **Приложения**.

4. В правой части iTunes прокрутите окно вниз до раздела **Общий доступ к файлам**, а затем в столбце **Надстройки** выберите **Excel** или **Word**.

5. В нижней части столбца документы **Excel** или **Word** нажмите кнопку **Добавить файл**, а затем выберите файл manifest. XML надстройки, которую необходимо Загрузка неопубликованных.

6. Откройте приложение Excel или Word на iPad. Если приложение Excel или Word уже запущено, нажмите кнопку **домой** , а затем закройте и перезапустите приложение.

7. Откройте документ.

8. Выберите **пункт надстройки** на вкладке **Вставка** . (на вкладке **Вставка** может потребоваться прокрутить страницу по горизонтали, пока не появится **кнопка** надстройка.) Надстройка неопубликованные доступна для вставки под заголовком **разработчик** **в пользовательском интерфейсе надстроек.**

    ![Вставка надстроек в приложение Excel](../images/excel-insert-add-in.png)

## <a name="sideload-an-add-in-on-excel-or-word-on-ipad-using-macos-catalina"></a>Загрузка неопубликованных надстройку в Excel или Word на iPad с помощью macOS Каталина

> [!IMPORTANT]
> С появлением macOS Каталина, [iTunes по протоколу Apple в Mac](https://support.apple.com/HT210200) и интегрированных функциональных возможностей, необходимых для Загрузка неопубликованных приложений в **Finder**.

1. Подключите iPad к компьютеру с помощью кабеля для синхронизации. Если вы подключаете iPad к компьютеру в первый раз, вам будет предложено **доверять этому компьютеру?**. Выберите **Доверять**. Кроме того, вам может быть предложено сделать это новым iPad или восстановить его.

2. В области Finder в разделе **расположения**выберите значок **iPad** под строкой меню.

3. В верхней части окна Finder выберите **файлы**, а затем найдите **Excel** или **Word**.

4. В другом окне Finder перетащите manifest.xml файл надстройки, который требуется загрузить, в файл **Excel** или **Word** в первом окне Finder.

5. Откройте приложение Excel или Word на iPad. Если приложение Excel или Word уже запущено, нажмите кнопку **домой** , а затем закройте и перезапустите приложение.

6. Откройте документ.

7. Выберите **пункт надстройки** на вкладке **Вставка** . (на вкладке **Вставка** может потребоваться прокрутить страницу по горизонтали, пока не появится **кнопка** надстройка.) Надстройка неопубликованные доступна для вставки под заголовком **разработчик** **в пользовательском интерфейсе надстроек.**

    ![Вставка надстроек в приложение Excel](../images/excel-insert-add-in.png)

## <a name="sideload-an-add-in-in-office-on-mac"></a>Загрузка неопубликованной надстройки в Office для Mac

> [!NOTE]
> Сведения о загрузке неопубликованной надстройки Outlook для Mac см. в статье [Загрузка неопубликованных надстроек Outlook для тестирования](../outlook/sideload-outlook-add-ins-for-testing.md#sideload-an-add-in-in-outlook-on-the-desktop).

1. Откройте **терминал** и перейдите в одну из следующих папок, где будет сохранен файл манифеста надстройки. Если папки `wef` нет на компьютере, создайте ее.

    - Для Word: `/Users/<username>/Library/Containers/com.microsoft.Word/Data/Documents/wef`
    - Для Excel: `/Users/<username>/Library/Containers/com.microsoft.Excel/Data/Documents/wef`
    - Для PowerPoint: `/Users/<username>/Library/Containers/com.microsoft.Powerpoint/Data/Documents/wef`

2. Откройте папку в **Finder** с помощью команды `open .` (включая точку или точку). Скопируйте файл манифеста надстройки в эту папку.

    ![Папка Wef в Office для Mac](../images/all-my-files.png)

3. Запустите Word и откройте документ. Если приложение Word уже запущено, перезапустите его.

4. В Word выберите **Вставить**надстройки в  >  **Add-ins**  >  **папку Мои** надстройки (раскрывающееся меню), а затем выберите свою надстройку.

    ![Мои надстройки в Office для Mac](../images/my-add-ins-wikipedia.png)

    > [!IMPORTANT]
    > Неопубликованные надстройки не отображаются в диалоговом окне "Мои надстройки". Они видны только в раскрывающемся меню (небольшая стрелка вниз справа от кнопки "Мои надстройки" на вкладке **Вставка**). Неопубликованные надстройки перечислены под заголовком **Надстройки для разработчиков** в этом меню.

5. Проверьте, отображается ли ваша надстройка в Word.

    ![Надстройка в Office для Mac](../images/lorem-ipsum-wikipedia.png)

## <a name="remove-a-sideloaded-add-in"></a>Удаление надстройки неопубликованные

Вы можете удалить ранее созданную надстройку неопубликованные, очистив кэш Office на вашем компьютере. Сведения о том, как очистить кэш для каждой платформы и приложений можно найти в статье [Очистка кэша Office](clear-cache.md).

## <a name="see-also"></a>См. также

- [Отладка надстроек Office на iPad и Mac](debug-office-add-ins-on-ipad-and-mac.md)
