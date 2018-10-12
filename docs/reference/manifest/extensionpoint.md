# <a name="extensionpoint-element"></a>Элемент ExtensionPoint

 Определяет, где доступны функции надстройки в пользовательском интерфейсе Office. Элемент **ExtensionPoint** является дочерним для элемента [AllFormFactors](allformfactors.md), [DesktopFormFactor](desktopformfactor.md) или [MobileFormFactor](mobileformfactor.md). 

## <a name="attributes"></a>Атрибуты

|  Атрибут  |  Обязательный  |  Описание  |
|:-----|:-----|:-----|
|  **xsi:type**  |  Да  | Тип определяемой точки расширения.|

## <a name="extension-points-for-excel-only"></a>Точки расширения только для Excel

- **CustomFunctions** — настраиваемая функция, написанная на JavaScript для Excel.

[Пример кода в этой XML](https://github.com/OfficeDev/Excel-Custom-Functions/blob/master/customfunctions.xml) показывает, как использовать элемент **ExtensionPoint** со значением атрибута **CustomFunctions** и как использовать дочерние элементы.

## <a name="extension-points-for-word-excel-powerpoint-and-onenote-add-in-commands"></a>Точки расширения для команд надстроек Word, Excel, PowerPoint и OneNote

- **PrimaryCommandSurface** — лента в Office.
- **ContextMenu** — контекстное меню, которое появляется при нажатии правой кнопкой мыши в интерфейсе Office.

В следующих примерах показано, как использовать элемент **ExtensionPoint** со значениями атрибута **PrimaryCommandSurface** и **ContextMenu**, и какие дочерние элементы использовать с каждым из них.

> [!IMPORTANT] 
> Убедитесь, что для элементов, содержащих атрибут ID, указан уникальный идентификатор. Рекомендуем указать название компании и ваш идентификатор. Например, используйте следующий формат. <CustomTab id="mycompanyname.mygroupname">

```XML
<ExtensionPoint xsi:type="PrimaryCommandSurface">
          <CustomTab id="Contoso Tab">
          <!-- If you want to use a default tab that comes with Office, remove the above CustomTab element, and then uncomment the following OfficeTab element -->
            <!-- <OfficeTab id="TabData"> -->
            <Label resid="residLabel4" />
            <Group id="Group1Id12">
              <Label resid="residLabel4" />
              <Icon>
                <bt:Image size="16" resid="icon1_32x32" />
                <bt:Image size="32" resid="icon1_32x32" />
                <bt:Image size="80" resid="icon1_32x32" />
              </Icon>
              <Tooltip resid="residToolTip" />
              <Control xsi:type="Button" id="Button1Id1">

                  <!-- information about the control -->
              </Control>
              <!-- other controls, as needed -->
            </Group>
          </CustomTab>
        </ExtensionPoint>

      <ExtensionPoint xsi:type="ContextMenu">
        <OfficeMenu id="ContextMenuCell">
          <Control xsi:type="Menu" id="ContextMenu2">
                  <!-- information about the control -->
          </Control>
          <!-- other controls, as needed -->
        </OfficeMenu>
        </ExtensionPoint>
```

#### <a name="child-elements"></a>Дочерние элементы
 
|**Элемент**|**Описание**|
|:-----|:-----|
|**CustomTab**|Обязательный, если требуется добавить на ленту настраиваемую вкладку (с помощью элемента **PrimaryCommandSurface**). Если используется элемент **CustomTab**, использовать элемент **OfficeTab** невозможно. Атрибут **id** является обязательным.|
|**OfficeTab**|Обязательный, если требуется расширить стандартную вкладку ленты Office (с помощью элемента **PrimaryCommandSurface**). Невозможно использовать элементы **OfficeTab** и **CustomTab** одновременно. Дополнительные сведения см. в статье [OfficeTab](officetab.md).|
|**OfficeMenu**|Обязательный при добавлении команд надстройки в контекстное меню по умолчанию (с помощью элемента **ContextMenu**). Для атрибута **id** необходимо задать следующее значение: <br/> - **ContextMenuText** для Excel или Word. Отображает элемент в контекстном меню, когда пользователь щелкает выделенный текст правой кнопкой мыши. <br/> - **ContextMenuCell** для Excel. Отображает элемент в контекстном меню, когда пользователь нажимает ячейку электронной таблицы правой кнопкой мыши.|
|**Group**|Группа точек расширения пользовательского интерфейса на вкладке. Группа может включать до шести элементов управления. Атрибут **id** является обязательным. Это строка длиной до 125 символов.|
|**Label**|Обязательный. Метка группы. Для атрибута **resid** необходимо задать значение атрибута **id** элемента **String**. Элемент **String** — это дочерний элемент элемента **ShortStrings**, который является дочерним для элемента **Resources**.|
|**Icon**|Обязательный. Задает значок группы, который будет использоваться на устройствах с малым форм-фактором либо при отображении слишком большого количества кнопок. Для атрибута **resid** необходимо задать значение атрибута **id** элемента **Image**. Элемент **Image** — это дочерний элемент элемента **Images**, который является дочерним для элемента **Resources**. Атрибут **size** указывает размер изображения в пикселях. Необходимо три размера изображения: 16, 32 и 80. Кроме того, поддерживается пять необязательных размеров: 20, 24, 40, 48 и 64.|
|**Tooltip**|Необязательный. Подсказка группы. Для атрибута **resid** необходимо задать значение атрибута **id** элемента **String**. Элемент **String** — это дочерний элемент элемента **LongStrings**, который является дочерним для элемента **Resources**.|
|**Control**|В каждой группе должен быть по крайней мере один элемент управления. Элемент **Control** может относиться к типу **Button** или **Menu**. С помощью элемента **Menu** можно указать раскрывающийся список элементов управления "Кнопка". В настоящее время поддерживаются только кнопки и меню. Дополнительные сведения см. в разделах [Элементы управления "Кнопка"](control.md#button-control) и [Элементы управления меню](control.md#menu-dropdown-button-controls).<br/>**Примечание.** Чтобы упростить устранение неполадок, рекомендуем добавлять элемент **Control** и соответствующий дочерний элемент **Resources** по одному за раз.|
|**Script**|Ссылка на файл JavaScript с определением настраиваемой функции и кодом регистрации. Этот элемент не используется в предварительной версии для разработчиков. Вместо этого, загрузку всех файлов JavaScript выполняет страница HTML.|
|**Page**|Ссылка на HTML-страницу для настраиваемых функций.|

## <a name="extension-points-for-outlook"></a>Точки расширения для Outlook

- [MessageReadCommandSurface](#messagereadcommandsurface) 
- [MessageComposeCommandSurface](#messagecomposecommandsurface) 
- [AppointmentOrganizerCommandSurface](#appointmentorganizercommandsurface) 
- [AppointmentAttendeeCommandSurface](#appointmentattendeecommandsurface)
- [Module](#module) (можно использовать только в [DesktopFormFactor](desktopformfactor.md)).
- [MobileMessageReadCommandSurface](#mobilemessagereadcommandsurface)
- [События](#events)
- [DetectedEntity](#detectedentity)

### <a name="messagereadcommandsurface"></a>MessageReadCommandSurface
Эта точка расширения помещает кнопки на панель команд для представления чтения почты. В классической версии Outlook эта панель отображается на ленте.

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [OfficeTab](officetab.md) |  Добавляет команду(ы) на вкладку ленты по умолчанию.  |
|  [CustomTab](customtab.md) |  Добавляет команду(ы)  на специальную вкладку ленты.  |

#### <a name="officetab-example"></a>Пример элемента OfficeTab
```xml
<ExtensionPoint xsi:type="MessageReadCommandSurface">
  <OfficeTab id="TabDefault">
        <-- OfficeTab Definition -->
  </OfficeTab>
</ExtensionPoint>
```

#### <a name="customtab-example"></a>Пример элемента CustomTab
```xml
<ExtensionPoint xsi:type="MessageReadCommandSurface">
  <CustomTab id="TabCustom1">
        <-- CustomTab Definition -->
  </CustomTab>
</ExtensionPoint>
```

### <a name="messagecomposecommandsurface"></a>MessageComposeCommandSurface
Эта точка расширения добавляет кнопки на ленту для надстроек, использующих форму создания сообщения. 

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [OfficeTab](officetab.md) |  Добавляет команду(ы) на вкладку ленты по умолчанию.  |
|  [CustomTab](customtab.md) |  Добавляет команду(ы)  на специальную вкладку ленты.  |

#### <a name="officetab-example"></a>Пример элемента OfficeTab
```xml
<ExtensionPoint xsi:type="MessageComposeCommandSurface">
  <OfficeTab id="TabDefault">
        <-- OfficeTab Definition -->
  </OfficeTab>
</ExtensionPoint>
```

#### <a name="customtab-example"></a>Пример элемента CustomTab

```xml
<ExtensionPoint xsi:type="MessageComposeCommandSurface">
  <CustomTab id="TabCustom1">
        <-- CustomTab Definition -->
  </CustomTab>
</ExtensionPoint>
```

### <a name="appointmentorganizercommandsurface"></a>AppointmentOrganizerCommandSurface

Эта точка расширения добавляет кнопки на ленту для формы, предназначенной для организатора собрания. 

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [OfficeTab](officetab.md) |  Добавляет команду(ы) на вкладку ленты по умолчанию.  |
|  [CustomTab](customtab.md) |  Добавляет команду(ы)  на специальную вкладку ленты.  |

#### <a name="officetab-example"></a>Пример элемента OfficeTab
```xml
<ExtensionPoint xsi:type="AppointmentOrganizerCommandSurface">
  <OfficeTab id="TabDefault">
        <-- OfficeTab Definition -->
  </OfficeTab>
</ExtensionPoint>
```

#### <a name="customtab-example"></a>Пример элемента CustomTab
```xml
<ExtensionPoint xsi:type="AppointmentOrganizerCommandSurface">
  <CustomTab id="TabCustom1">
        <-- CustomTab Definition -->
  </CustomTab>
</ExtensionPoint>
```

### <a name="appointmentattendeecommandsurface"></a>AppointmentAttendeeCommandSurface

Эта точка расширения добавляет кнопки на ленту для формы, предназначенной для участника собрания. 

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [OfficeTab](officetab.md) |  Добавляет команду(ы) на вкладку ленты по умолчанию.  |
|  [CustomTab](customtab.md) |  Добавляет команду(ы)  на специальную вкладку ленты.  |

#### <a name="officetab-example"></a>Пример элемента OfficeTab
```xml
<ExtensionPoint xsi:type="AppointmentAttendeeCommandSurface">
  <OfficeTab id="TabDefault">
        <-- OfficeTab Definition -->
  </OfficeTab>
</ExtensionPoint>
```

#### <a name="customtab-example"></a>Пример элемента CustomTab
```xml
<ExtensionPoint xsi:type="AppointmentAttendeeCommandSurface">
  <CustomTab id="TabCustom1">
        <-- CustomTab Definition -->
  </CustomTab>
</ExtensionPoint>
```

### <a name="module"></a>Модуль

Эта точка расширения добавляет кнопки на ленту для расширения модуля. 

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [OfficeTab](officetab.md) |  Добавляет команду(ы) на вкладку ленты по умолчанию.  |
|  [CustomTab](customtab.md) |  Добавляет команду(ы)  на специальную вкладку ленты.  |

### <a name="mobilemessagereadcommandsurface"></a>MobileMessageReadCommandSurface
Эта точка расширения помещает кнопки на панель команд для чтения почты в форм-факторе мобильного устройства.

#### <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Описание  |
|:-----|:-----|
|  [Group](group.md) |  Добавляет группу кнопок на панель команд.  |

У элементов **ExtensionPoint** этого типа может быть только один дочерний элемент —  **Group**.

Для атрибута **xsi:type** элементов **Control**, содержащихся в этой точке расширения, должно быть назначено значение `MobileButton`.

#### <a name="example"></a>Пример
```xml
<ExtensionPoint xsi:type="MobileMessageReadCommandSurface">
  <Group id="mobileGroupID">
    <Label resid="residAppName"/>
      <Control id="mobileButton1" xsi:type="MobileButton">
        <!-- Control definition -->
      </Control>
  </Group>
</ExtensionPoint>
```

### <a name="events"></a>События

Эта точка расширения добавляет обработчик для указанного события.

> [!NOTE]
> Данный тип элементов поддерживается только с Outlook в Интернете в Office 365.

| Элемент | Описание  |
|:-----|:-----|
|  [Событие](event.md) |  Задает событие и функцию его обработчика.  |

#### <a name="itemsend-event-example"></a>Пример события ItemSend

```xml
<ExtensionPoint xsi:type="Events"> 
  <Event Type="ItemSend" FunctionExecution="synchronous" FunctionName="itemSendHandler" /> 
</ExtensionPoint> 
```

### <a name="detectedentity"></a>DetectedEntity

Эта точка расширения добавляет активацию контекстной надстройки для указанного типа сущности.

В соответствующем элементе [VersionOverrides](versionoverrides.md) для атрибута `xsi:type` должно быть задано значение `VersionOverridesV1_1`.

> [!NOTE]
> Данный тип элементов поддерживается только с Outlook в Интернете в Office 365.

|  Элемент |  Описание  |
|:-----|:-----|
|  [Label](#label) |  Задает метку для надстройки в контекстном окне.  |
|  [SourceLocation](sourcelocation.md) |  Задает URL-адрес контекстного окна.  |
|  [Rule](rule.md) |  Задает одно или несколько правил, определяющих, когда активируется надстройка.  |

#### <a name="label"></a>Label

Обязательный элемент. Метка группы. Атрибуту **resid** нужно присвоить значение атрибута **id** элемента **String** в элементе **ShortStrings**, вложенном в элемент [Resources](resources.md).

#### <a name="highlight-requirements"></a>Требования к выделению

Единственный способ, которым пользователь может активировать контекстную надстройку, — взаимодействие с выделенной сущностью. Разработчики могут указывать, какие сущности выделяются, с помощью атрибута `Highlight` элемента `Rule` для типов правил `ItemHasKnownEntity` и `ItemHasRegularExpressionMatch`.

Однако следует учитывать некоторые ограничения. Они гарантируют, что в соответствующих сообщениях и встречах всегда есть выделенная сущность, с помощью которой пользователь может активировать надстройку.

- Сущности `EmailAddress` и `Url` не поддерживают выделение, поэтому их нельзя использовать для активации надстройки.
- Если используется одно правило, то для атрибута `Highlight` ДОЛЖНО быть задано значение `all`.
- Если используется правило `RuleCollection`, совмещенное с другими правилами с помощью оператора `Mode="AND"`, то как минимум в одном из правил для атрибута `Highlight` ДОЛЖНО быть задано значение `all`.
- Если используется правило `RuleCollection`, в котором правила совмещаются с помощью оператора `Mode="OR"`, то в каждом из них для атрибута `Highlight` ДОЛЖНО быть задано значение `all`.

#### <a name="detectedentity-event-example"></a>Пример события DetectedEntity

```xml
<ExtensionPoint xsi:type="DetectedEntity">
  <Label resid="residLabelName"/>
  <SourceLocation resid="residDetectedEntityURL" />
  <Rule xsi:type="RuleCollection" Mode="And">
    <Rule xsi:type="ItemIs" ItemType="Message" />
    <Rule xsi:type="ItemHasKnownEntity" EntityType="MeetingSuggestion" Highlight="all" />
    <Rule xsi:type="ItemHasKnownEntity" EntityType="Address" Highlight="none" />
  </Rule>
</ExtensionPoint> 
```