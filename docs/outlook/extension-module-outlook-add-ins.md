---
title: Надстройки Outlook с расширением модуля
description: Создают приложения, которые запускаются внутри Outlook и с помощью которых пользователи могут легко получать доступ к бизнес-информации и средствам повышения производительности, не выходя из Outlook.
ms.date: 05/27/2020
localization_priority: Normal
ms.openlocfilehash: ba25a10e0f6e8c8b3b14df7e98ff200e00717136
ms.sourcegitcommit: be23b68eb661015508797333915b44381dd29bdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "44611647"
---
# <a name="module-extension-outlook-add-ins"></a>Надстройки Outlook с расширением модуля

Надстройки с расширением модуля отображаются на панели навигации Outlook рядом с почтой, задачами и календарями. Расширение модуля может использовать не только сведения о почте и встречах. Вы можете создать приложения, с помощью которых пользователи могут получать доступ к бизнес-информации и средствам повышения производительности, не выходя из Outlook.

> [!NOTE]
> Расширения модуля поддерживаются только в Outlook 2016 или более поздних версиях для Windows.  

## <a name="open-a-module-extension"></a>Открытие расширения модуля

Чтобы открыть расширение модуля, пользователю необходимо щелкнуть имя или значок модуля на панели навигации Outlook. Если пользователь выбрал компактный режим панели навигации, то на ней будет отображаться значок, показывающий, что расширение загружено.

![Показана компактная панель навигации, когда расширение модуля загружено в Outlook.](../images/outlook-module-navigationbar-compact.png)

Если пользователь не используют компактную навигацию, то для панели навигации доступно два представления. Если загружено одно расширение, отображается название надстройки.

![Показана развернутая панель навигации, когда в Outlook загружено одно расширение модуля.](../images/outlook-module-navigationbar-one.png)

Если загружено несколько надстроек, отображается слово **Надстройки**. В обоих вариантах при нажатии откроется пользовательский интерфейс расширения.

![Показана развернутая панель навигации, когда в Outlook загружено несколько расширений модуля.](../images/outlook-module-navigationbar-more.png)

Когда вы щелкаете расширение, Outlook заменяет встроенный модуль на специальный, чтобы пользователи могли взаимодействовать с надстройкой. Вы можете использовать все функции API JavaScript для Outlook в надстройке и создавать кнопки на ленте Outlook, которые будут взаимодействовать с содержимым надстройки. Ниже показана интегрированная в панель навигации Outlook надстройка с кнопками на ленте, которые обновляют ее содержимое.

![Пользовательский интерфейс расширения модуля](../images/outlook-module-extension.png)

## <a name="example"></a>Пример

Ниже показан раздел файла манифеста, который определяет расширение модуля.

```xml
<!-- Add Outlook module extension point -->
<VersionOverrides xmlns="http://schemas.microsoft.com/office/mailappversionoverrides"
                  xsi:type="VersionOverridesV1_0">
  <VersionOverrides xmlns="http://schemas.microsoft.com/office/mailappversionoverrides/1.1"
                    xsi:type="VersionOverridesV1_1">

    <!-- Begin override of existing elements -->
    <Description resid="residVersionOverrideDesc" />

    <Requirements>
      <bt:Sets DefaultMinVersion="1.3">
        <bt:Set Name="Mailbox" />
      </bt:Sets>
    </Requirements>
    <!-- End override of existing elements -->

    <Hosts>
      <Host xsi:type="MailHost">
        <DesktopFormFactor>
          <!-- Set the URL of the file that contains the
                JavaScript function that controls the extension -->
          <FunctionFile resid="residFunctionFileUrl" />

          <!--New Extension Point - Module for a ModuleApp -->
          <ExtensionPoint xsi:type="Module">
            <SourceLocation resid="residExtensionPointUrl" />
            <Label resid="residExtensionPointLabel" />

            <CommandSurface>
              <CustomTab id="idTab">
                <Group id="idGroup">
                  <Label resid="residGroupLabel" />

                  <Control xsi:type="Button" id="group.changeToAssociate">
                    <Label resid="residChangeToAssociateLabel" />
                    <Supertip>
                      <Title resid="residChangeToAssociateLabel" />
                      <Description resid="residChangeToAssociateDesc" />
                    </Supertip>
                    <Icon>
                      <bt:Image size="16" resid="residAssociateIcon16" />
                      <bt:Image size="32" resid="residAssociateIcon32" />
                      <bt:Image size="80" resid="residAssociateIcon80" />
                    </Icon>
                    <Action xsi:type="ExecuteFunction">
                      <FunctionName>changeToAssociateRate</FunctionName>
                    </Action>
                  </Control>
                  
              </Group>
                <Label resid="residCustomTabLabel" />
              </CustomTab>
            </CommandSurface>
          </ExtensionPoint>
        </DesktopFormFactor>
      </Host>
    </Hosts>

    <Resources>
      <bt:Images>
        <bt:Image id="residAddinIcon16" 
                  DefaultValue="https://localhost:8080/Executive-16.png" />
        <bt:Image id="residAddinIcon32" 
                  DefaultValue="https://localhost:8080/Executive-32.png" />
        <bt:Image id="residAddinIcon80" 
                  DefaultValue="https://localhost:8080/Executive-80.png" />
      
        <bt:Image id="residAssociateIcon16" 
                  DefaultValue="https://localhost:8080/Associate-16.png" />
        <bt:Image id="residAssociateIcon32" 
                  DefaultValue="https://localhost:8080/Associate-32.png" />
        <bt:Image id="residAssociateIcon80" 
                  DefaultValue="https://localhost:8080/Associate-80.png" />
      </bt:Images>

      <bt:Urls>
        <bt:Url id="residFunctionFileUrl" 
                DefaultValue="https://localhost:8080/" />
        <bt:Url id="residExtensionPointUrl" 
                DefaultValue="https://localhost:8080/" />
      </bt:Urls>

      <!--Short strings must be less than 30 characters long -->
      <bt:ShortStrings>
        <bt:String id="residExtensionPointLabel" 
                    DefaultValue="Billable Hours" />
        <bt:String id="residGroupLabel" 
                    DefaultValue="Change billing rate" />
        <bt:String id="residCustomTabLabel" 
                    DefaultValue="Billable hours" />

        <bt:String id="residChangeToAssociateLabel" 
                    DefaultValue="Associate" />
      </bt:ShortStrings>

      <bt:LongStrings>
        <bt:String id="residVersionOverrideDesc" 
                    DefaultValue="Version override description" />

        <bt:String id="residChangeToAssociateDesc" 
                    DefaultValue="Change to the associate billing rate: $127/hr" />
      </bt:LongStrings>
    </Resources>
  </VersionOverrides>
</VersionOverrides>
```

## <a name="see-also"></a>См. также

- [Манифесты надстроек Outlook](manifests.md)
- [Команды надстроек Outlook](add-in-commands-for-outlook.md)
- [Пример расширений модуля Outlook для расчета оплачиваемых часов](https://github.com/OfficeDev/Outlook-Add-in-JavaScript-ModuleExtension)
