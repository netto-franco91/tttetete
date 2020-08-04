# WCheckbox

This component is responsible to render a checkbox component and control it's state.


## Summary

- [Attributes](#attributes)
- [Event Listeners](#event-listeners)
- [Handler Methods](#handler-methods)
- [Design spec link](#design-spec-link)


## How to group checkboxes on detail?

Follow a link with explanation [groupping checkboxes](https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/app/components/molecules/w-mdetail/README.md#grouped-checkbox)


## Attributes

- state
- handler
- value
- label
- display
- readOnly
- showsInfo
- openInfo
- data
- noDirty
- alwaysShowTooltip
- tooltipField


### onChange
----
#### :clock230: When?
This event executed when changing value the checkbox.

#### :bookmark_tabs: Parameters
**handler:** _(Object)_ Component handler <br>
**nmAtributo:** _(String)_  Name Atribute<br>
**oldValue:** _(Object)_  Old Value<br>
**newValue:** _(Object)_  New Value<br>
**source:** _(WCheckboxConstants)_  Source checkbox<br>

#### :pencil2: Example 

```javascript      
onChange(handler, nmAtributo, oldValue, newValue, source) {
  //do something
}
```

## Event Listeners

- [onChange](#onchange)
- [onLoad](#onload)
- [onFocus](#onfocus)
- [onBlur](#onblur)
- [onClick](#onclick)
- [onDoubleClick](#ondoubleclick)
- [onChangeVisibility](#onchangevisibility)
- [onInfobuttonClick](#oninfobuttonclick)


## Handler Methods

  - [getValue](#getvalue)
  - [setValue](#setvalue)
  - [getOldValue](#getoldvalue)
  - [setOldValue](#setoldvalue)
  - [clearValue](#clearvalue)
  - [setOnRight](#setonright)
  - [setToolTip](#settooltip)
  - [setImgSrc](#setimgsrc)
  - [setImgHeight](#setimgheight)
  - [setImgWidth](#setimgwidth)
  - [setFocus](#setfocus)
  - [setBlur](#setblur)
  - [setVisible](#setvisible)
  - [isVisible](#isvisible)
  - [setEnabled](#setenabled)
  - [isEnabled](#isenabled)
  - [setReadOnly](#setreadonly)
  - [isReadOnly](#isreadonly)
  - [setIndeterminateMode](#setindeterminatemode)
  - [getLabel](#getlabel)
  - [setLabel](#setlabel)
  - [setInfobutton](#setinfobutton)

### getValue

  This method is used to get the value of checkbox.

Example:

  ```javascript
    var row = handler.getValue();
  ```

### setValue

  This method is used to set the value of the checkbox

|   Params  |           Description                   |   Type   | Default |
| --------- | --------------------------------------- | -------- | ------- |
| value     | The new value                           | Anything | none    |
| fireEvent | set if the change event has to be fired | Boolean  | false   |

Example:

  ```javascript
    var records = handler.setValue(true, false);
  ```

### getOldValue

  This method returns the old value

Example:

  ```javascript
    handler.getOldValue();
  ```

### setOldValue

  This method change the old value.

|   Params  |   Description   |   Type   | Default |
| --------- | --------------- | -------- | ------- |
| value     | The new value   | Anything | none    |

Example:

  ```javascript
    handler.setOldValue(false);
  ```

### clearValue

  This method change de value to the true one.

Example:

```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").clearValue();
}
```

### setOnRight

  This method changes the checkboz style.
  If true, the checkbox is shown at the right side of the label.
  If false, the checkbox is shown at the left side of the label. (Default)

|   Params  |   Description   |   Type   | Default |
| --------- | --------------- | -------- | ------- |
| value     | The new value   | Boolean  | false   |


Example:

```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setOnRight(true);
}
```

### setToolTip

  This method  change the checkbox tooltip.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | The new tooltip   | String   |  none   |

```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setToolTip('tests');
}
```

### setImgSrc

  This method set a image to the checkbox label.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | Path to the image | String   | none    |

```javascript
function onReady(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgSrc('assets/images/checkbox_image.jpeg');
}
```

### setImgHeight

  This method changes the image height.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | New image height  | Number   | none    |

```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgHeight(20);
}
```  

### setImgWidth

  This method changes the image width.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | New image width   | Number   | none    |

```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgWidth(20);
}
```

### setFocus

  This method set the focus to the checkbox

```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setFocus();
}
```  

### setBlur

### setVisible

  This method changes the checkbox visibility.
  If true is visible. (Default)
  If false is not visible.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox visibility   | Boolean   | none    |

```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setVisible(false);
}
```

### isVisible

  This method return if the checkbox is visible or not.


```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isVisible()){
    //Do Something
  }
}
```

### setEnabled

  This method changes if the checkbox is enable or not.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox Enabled      | Boolean   | none    |

```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setEnabled(false);
}
```

### isEnabled

  This method returns if the checkbox is enable or not.

```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isEnabled()){
    //Do Something
  }
}
```

### setReadOnly

  This method changes the read only property.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox readOnly     | Boolean   | none    |

```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setReadOnly(true);
}
```

### isReadOnly

  This method return if the checkbox is read only or not.

```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isReadOnly()){
    //Do Something
  }
}
```

### setIndeterminateMode

  This method set the checkbox to the indeterminate mode, now the checkbox has a third state.
  Now it can be true value, undefined or null, false value.
  Default is disable.

|   Params  |   Description                 |   Type    | Default |
| --------- | ----------------------------- | --------- | ------- |
| value     | Enable indeterminate mode     | Boolean   | none    |

```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setIndeterminateMode(true);
}
```

### getLabel

This method returns the label of the checkbox

#### Example

```javascript
function myMethod() {
  let checkbox = detailHandler.getAttribute('CHECKBOX');
  let label = checkbox.getLabel();
}
```

### setLabel

This method change the label of the checkbox

#### Example

```javascript
function myMethod() {
  let checkbox = detailHandler.getAttribute('CHECKBOX');
  checkbox.setLabel("NEW_LABEL");
}
```


### setInfobutton

----
#### :page_with_curl: Description
Add an icon on right of the component.

There are some default icons that can be use, these options are described on the file [WInfobuttonTypes](https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/app/components/atoms/w-infobutton/w-infobutton-types.enum.js).

#### :bookmark_tabs: Parameters
**type:** _(Object)_  Object with the definition of the infos. In the object must have the attributes: 
 - _name(String)_ Name to be used to store the type of the icon
 - _image(String)_ Must be an Base64 image

**tooltip:** _(String)_ The tooltip information that it will display when hover

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
import { Controller, Inject } from '@philips/odin-ext';

@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class DBPanel extends DBPanel {

  @Inject('WInfobuttonTypes')
  WInfobuttonTypes;

  onOpenDetail() {
    const detail = this.handler.getDetailHandler();
    const active = detail.getAttribute('IE_ATIVO');

    active.setInfobutton(this.WInfobuttonTypes.NOTICE, 'It will control if the record is active');
  }

}
```

It is possible to implement custom info buttons creating the an object with a `name` field and a `image` field. The `image` field must contain an url to the image fo the icon.

It is also possible to use `SVG` files in the assets of the [tasy repo](https://github.com/philips-emr/tasy/tree/dev/assets), or implement a SVG dynamicly into the javascript as made into [this](https://github.com/philips-emr/tasy/pull/98103) pull request.

## Design spec link
http://design.emr.philips.com.br/library/wip/components/basic-elements/checkbox/
