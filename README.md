# WCheckbox

This component is responsible to render a checkbox component and control it's state.


## Summary

- [Attributes](#attributes)
- [Event Listeners](#event-listeners)
- [Handler Methods](#handler-methods)
- <a href="https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework-demo/src/main/components/w-checkbox/" target="_blank">Demo link</a>
- [Design spec link](#design-spec-link)


## How to group checkboxes on detail?

Follow a link with explanation [groupping checkboxes](https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/app/components/molecules/w-mdetail/README.md#grouped-checkbox)


## Attributes
|      Name         |           Description                               |     Mandatory?     |      Type      |
|  :------------    |    :--------------------------                      |    :----------:    |  :----------:  |
|   state           |     Default label stylename                         |         No         |     String     |
|   handler         |     Show or Hide the label                          |         No         |     Boolean    |
|   value           |     Enable or Disable the label                     |         No         |     Boolean    |
|   label           |     A text/message code to be shown                 |         No         |     Number     |
|   display         |     If true, setValue method has no verification    |         No         |     Boolean    |
|   readOnly        |     If true, setValue method has no verification    |         No         |     Boolean    |
|   showsInfo       |     If true, setValue method has no verification    |         No         |     Boolean    |
|   openInfo        |     If true, setValue method has no verification    |         No         |     Boolean    |
|   data            |     If true, setValue method has no verification    |         No         |     Boolean    |
|   noDirty         |     If true, setValue method has no verification    |         No         |     Boolean    |
|   alwaysShowTooltip |   If true, setValue method has no verification    |         No         |     Boolean    |
|   tooltipField    |     If true, setValue method has no verification    |         No         |     Boolean    |


## Event Listeners

- [onChange](#onchange)
- [onLoad](#onload)
- [onFocus](#onfocus)
- [onBlur](#onblur)
- [onClick](#onclick)
- [onDoubleClick](#ondoubleclick)
- [onChangeVisibility](#onchangevisibility)
- [onInfobuttonClick](#oninfobuttonclick)


### onChange
----
#### :clock230: When?
This event executed when changing value the checkbox.

#### :bookmark_tabs: Parameters
**handler:** _(Object)_ Component handler <br>
**nmAtributo:** _(String)_  Name Atribute<br>
**oldValue:** _(Object)_  Old Value<br>
**newValue:** _(Object)_  New Value<br>
**source:** _(WCheckboxConstants)_  Source checkbox

#### :pencil2: Example 
```javascript      
onChange(handler, nmAtributo, oldValue, newValue, source) {
  //do something
}
```

### onLoad
----
#### :clock230: When?
This event is triggered when the w-checkbox component is loaded.

#### :pencil2: Example 
```javascript      
onLoad() {
  //do something
}
```

### onFocus
----
#### :clock230: When?
This event is fired when the component has the focus on it.

#### :bookmark_tabs: Parameters
**event** _(Object)_ Event data as an object.

#### :pencil2: Example 
```javascript      
onFocus(event) {
  //do something
}
```

### onBlur
----
#### :clock230: When?
This event fired when focus out.

#### :pencil2: Example 
```javascript      
onBlur() {
  //do something
}
```

### onClick
----
#### :clock230: When?
This event is triggered when the internal daily directive is clicked.

#### :bookmark_tabs: Parameters
**event** _(Object)_ Event data as an object.

#### :pencil2: Example 

```javascript
onClick(event){ 
  //do something
}
```

### onDoubleClick
----
#### :clock230: When?
This event is triggered when the internal daily directive is clicked.

#### :bookmark_tabs: Parameters
**handler:** _(Object)_ Component handler <br>
**nmAtributo:** _(String)_  Name Atribute<br>
**value** _(Object)_ Value descripion of the checkbox.

#### :pencil2: Example 

```javascript
onDoubleClick(handler, nmAtributo, value){ 
  //do something
}
```

### onChangeVisibility
----
#### :clock230: When?
This event fired when component change the visibility.

#### :bookmark_tabs: Parameters
**handler:** _(Object)_ Component handler

#### :pencil2: Example 

```javascript
onChangeVisibility(handler){ 
  //do something
}
```

### onInfobuttonClick
----
#### :clock230: When?
This event is fire after the click on the info button.

#### :bookmark_tabs: Parameters
**code:** _(Object)_ Code of the component<br>
**value** _(Object)_ Value descripion of the checkbox.<br>
**nmAtributo:** _(String)_  Name Atribute<br>
**data:** _(Object)_  Data of the scope <br>

#### :pencil2: Example 

```javascript
onInfobuttonClick(code, value, nmAtributo, data){ 
  //do something
}
```

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
----
#### :clock230: When?
This method is used to get the value of checkbox.

#### :pencil2: Example 
```javascript
  var row = handler.getValue();
```


### setValue
----
#### :clock230: When?
This method is used to set the value of the checkbox

|   Params  |           Description                   |   Type   | Default |
| --------- | --------------------------------------- | -------- | ------- |
| value     | The new value                           | Anything | none    |
| fireEvent | set if the change event has to be fired | Boolean  | false   |

#### :pencil2: Example 
```javascript
  var records = handler.setValue(true, false);
```


### getOldValue
----
#### :clock230: When?
This method returns the old value

#### :pencil2: Example
```javascript
  handler.getOldValue();
```


### setOldValue
----
#### :clock230: When?
This method change the old value.

|   Params  |   Description   |   Type   | Default |
| --------- | --------------- | -------- | ------- |
| value     | The new value   | Anything | none    |

#### :pencil2: Example
```javascript
  handler.setOldValue(false);
```


### clearValue
----
#### :clock230: When?
This method change de value to the true one.

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").clearValue();
}
```


### setOnRight
----
#### :clock230: When?
This method changes the checkboz style.
If true, the checkbox is shown at the right side of the label.
If false, the checkbox is shown at the left side of the label. (Default)

|   Params  |   Description   |   Type   | Default |
| --------- | --------------- | -------- | ------- |
| value     | The new value   | Boolean  | false   |

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setOnRight(true);
}
```


### setToolTip
----
#### :clock230: When?
This method  change the checkbox tooltip.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | The new tooltip   | String   |  none   |

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setToolTip('tests');
}
```


### setImgSrc
----
#### :clock230: When?
This method set a image to the checkbox label.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | Path to the image | String   | none    |

#### :pencil2: Example
```javascript
function onReady(schematics, dbPanel) {
    dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgSrc('assets/images/checkbox_image.jpeg');
}
```

### setImgHeight
----
#### :clock230: When?
This method changes the image height.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | New image height  | Number   | none    |

#### :pencil2: Example
```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgHeight(20);
}
```  


### setImgWidth
----
#### :clock230: When?
This method changes the image width.

|   Params  |   Description     |   Type   | Default |
| --------- | ----------------- | -------- | ------- |
| value     | New image width   | Number   | none    |

#### :pencil2: Example
```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setImgWidth(20);
}
```


### setFocus
----
#### :clock230: When?
This method set the focus to the checkbox

#### :pencil2: Example
```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setFocus();
}
```  


### setVisible
----
#### :clock230: When?
This method changes the checkbox visibility.
If true is visible. (Default)
If false is not visible.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox visibility   | Boolean   | none    |

#### :pencil2: Example
```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setVisible(false);
}
```


### isVisible
----
#### :clock230: When?
This method return if the checkbox is visible or not.

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isVisible()){
    //Do Something
  }
}
```


### setEnabled
----
#### :clock230: When?
This method changes if the checkbox is enable or not.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox Enabled      | Boolean   | none    |

#### :pencil2: Example
```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setEnabled(false);
}
```


### isEnabled
----
#### :clock230: When?
This method returns if the checkbox is enable or not.

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isEnabled()){
    //Do Something
  }
}
```


### setReadOnly
----
#### :clock230: When?
This method changes the read only property.

|   Params  |   Description         |   Type    | Default |
| --------- | --------------------- | --------- | ------- |
| value     | Checkbox readOnly     | Boolean   | none    |

#### :pencil2: Example
```javascript
function onDetailOpen(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setReadOnly(true);
}
```


### isReadOnly
----
#### :clock230: When?
This method return if the checkbox is read only or not.

#### :pencil2: Example
```javascript
function onSelectionChange(schematics, dbPanel) {
  if(dbPanel.getGridHandler().getAttribute("CHECKBOX").isReadOnly()){
    //Do Something
  }
}
```


### setIndeterminateMode
----
#### :clock230: When?
This method set the checkbox to the indeterminate mode, now the checkbox has a third state.
Now it can be true value, undefined or null, false value.
Default is disable.

|   Params  |   Description                 |   Type    | Default |
| --------- | ----------------------------- | --------- | ------- |
| value     | Enable indeterminate mode     | Boolean   | none    |

#### :pencil2: Example
```javascript
function onReady(schematics, dbPanel) {
  dbPanel.getGridHandler().getAttribute("CHECKBOX").setIndeterminateMode(true);
}
```


### getLabel
----
#### :clock230: When?
This method returns the label of the checkbox

#### :pencil2: Example
```javascript
function myMethod() {
  let checkbox = detailHandler.getAttribute('CHECKBOX');
  let label = checkbox.getLabel();
}
```


### setLabel
----
#### :clock230: When?
This method change the label of the checkbox

#### :pencil2: Example
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
