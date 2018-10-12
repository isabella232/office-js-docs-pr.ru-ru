# <a name="officemenu-element"></a>Элемент OfficeMenu

Определяет коллекцию элементов управления, которые нужно добавить в контекстное меню Office. Применяется в надстройках Word, Excel, PowerPoint и OneNote.

## <a name="attributes"></a>Атрибуты

| Атрибут            | Обязательный | Описание                          |
|:---------------------|:--------:|:-------------------------------------|
| [xsi:type](#xsitype) | Да      | Тип определяемого элемента OfficeMenu.|

## <a name="child-elements"></a>Дочерние элементы

|  Элемент |  Обязательный  |  Описание  |
|:-----|:-----|:-----|
|  [Control](#control)    | Да |  Коллекция из одного или нескольких объектов Control.  |

## <a name="xsitype"></a>xsi:type

Указывает то встроенное меню клиентского приложения Office, в которое необходимо добавить название надстройки Office.

- `ContextMenuText` — отображает элемент в контекстном меню, когда пользователь открывает это меню, щелкая правой кнопкой мыши по выделенному тексту. Применяется для Word, Excel, PowerPoint и OneNote.
- `ContextMenuCell` — отображает элемент в контекстном меню, когда пользователь открывает это меню, щелкая правой кнопкой мыши ячейку электронной таблицы. Применяется для Excel. 

## <a name="control"></a>Control

Для каждого элемента **OfficeMenu** требуется один или несколько элементов управления [меню](control.md#menu-dropdown-button-controls). 

## <a name="example"></a>Пример

```xml
<OfficeMenu id="ContextMenuCell">
    <Control xsi:type="Menu" id="myMenuID">
      <Label resid="residLabel3" />
      <Supertip>
          <Title resid="residLabel" />
          <Description resid="residToolTip" />
      </Supertip>   
      <Icon>
        <bt:Image size="16" resid="icon1_16x16" />
        <bt:Image size="32" resid="icon1_32x32" />
        <bt:Image size="80" resid="icon1_80x80" />
      </Icon>    
      <Items>
        <Item id="myMenuItemID">
          <Label resid="residLabel3"/>
          <Supertip>
            <Title resid="residLabel" />
            <Description resid="residToolTip" />
          </Supertip>
          <Icon>
            <bt:Image size="16" resid="icon1_16x16" />
            <bt:Image size="32" resid="icon1_32x32" />
            <bt:Image size="80" resid="icon1_80x80" />
          </Icon>    
          <Action xsi:type="ShowTaskpane">
            <SourceLocation resid="residTaskpaneUrl2" />    
          </Action>    
        </Item>
      </Items>
    </Control>   
</OfficeMenu>
```