# Timeline Table Mode

Timeline vision table mode is option vision of the timeline.

- [Methods](#Methods)
- [Timeline Table Mode Detail](#Timeline-Table-Mode-Detail)
- [Timeline Table Mode Comment](#Timeline-Table-Mode-Comment)
- [Design spec](http://design.emr.philips.com.br/library/wip/components/informational/dynamic-flowchart/)


## Methods
- [renderValues](#renderValues)
- [createTableItem](#createTableItem)
- [onTableItemClick](#onTableItemClick)
- [saveTableItemValue](#saveTableItemValue)
- [fireEventTableModeItemChange](#fireEventTableModeItemChange)
- [onTableItemDetail](#onTableItemDetail)
- [onLoadTimelineTableItemDetail](#onLoadTimelineTableItemDetail)
- [onChangeTableModeDatePicker](#onChangeTableModeDatePicker)
- [closePopoverTimelineItemDetail](#closePopoverTimelineItemDetail)
- [getPopoverTimelineTableItemDetail](#getPopoverTimelineTableItemDetail)
- [saveTableItemDetail](#saveTableItemDetail)
- [showPopover](#showPopover)
- [onChangeTableModeItem](#onChangeTableModeItem)
- [attachEventListener](#attachEventListener)
- [destroy](#destroy)
- [editDetailTimelineItemTableMode ](#editDetailTimelineItemTableMode )
- [addCommentTimelineItemTableMode ](#addCommentTimelineItemTableMode )
- [getPopoverTimelineTableItemComment ](#getPopoverTimelineTableItemComment )
- [removeTimelineItemTableMode ](#removeTimelineItemTableMode )


### renderValues
----
#### :page_with_curl: Description
Creates the visual representation of the table mode with the click function and with its values when it has

#### :bookmark_tabs: Parameters
**element** _(DOM element)_ Element being created in the DOM with click function attached
**visItem** _(Object)_ Vis item containing all the properties to be used
**item** _(Object)_ Item that has come from timeline component datasource

#### :leftwards_arrow_with_hook: Return
Not available


### createTableItem
----
#### :page_with_curl: Description
It creates an item to be used when timeline is in table mode

#### :bookmark_tabs: Parameters
**visItem** _(Object)_ Vis item containing all the properties to be used
**item** _(Object)_ Item that has come from timeline component datasource

#### :leftwards_arrow_with_hook: Return
_(DOM element)_ - Returns an element created to be attached in the DOM. Used to display a cell in table mode.


### onTableItemClick
----
#### :page_with_curl: Description
Action of click event to handle a table mode item

#### :bookmark_tabs: Parameters
**visItem** _(Object)_ Vis item containing all the properties to be used

#### :leftwards_arrow_with_hook: Return
Not available


### saveTableItemValue
----
#### :page_with_curl: Description
Function that makes the necessary changes when changing values in an item in table mode

#### :bookmark_tabs: Parameters
**nmAtributo** _(String)_ Cell attribute name
**value** _(String)_ Value entered in the selected cell field
**save** _(boolean)_ Validation to perform the visual change when saving is performed. Default value true

#### :leftwards_arrow_with_hook: Return
Not available


### fireEventTableModeItemChange
----
#### :page_with_curl: Description
Function that fire event 'onTableModeItemChange' of the timeline

#### :bookmark_tabs: Parameters
**data** _(Object)_ - Data to fire envet onTableModeItemChange

#### :leftwards_arrow_with_hook: Return
Not available


### onTableItemDetail
----
#### :page_with_curl: Description
Function that calls the creation of the detail popover component for grouped editing

#### :bookmark_tabs: Parameters
**event** _(Object)_ - Event fired to call the function
**visItem** _(Object)_ Vis item containing all the properties to be used
**item** _(Object)_ Item that has come from timeline component datasource

#### :leftwards_arrow_with_hook: Return
Not available


### onLoadTimelineTableItemDetail
----
#### :page_with_curl: Description
Function called when the 'onLoad' event of the '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' component is fired
Event [onLoad](#onLoad) of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'.

#### :bookmark_tabs: Parameters
**handler** _(Object)_ - Handler of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'

#### :leftwards_arrow_with_hook: Return
Not available


### onChangeTableModeDatePicker
----
#### :page_with_curl: Description
Function called when the 'onTableModeDatePickerChange' event of the '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' component is fired
Event [onTableModeDatePickerChange](#onTableModeDatePickerChange) of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'.

#### :bookmark_tabs: Parameters
**event** _(Object)_  - Event data as an object

#### :leftwards_arrow_with_hook: Return
Not available


### closePopoverTimelineItemDetail 
----
#### :page_with_curl: Description
Function called when the 'onDestroy' event of the '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' component is fired
Event [onDestroy](#onDestroy) of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'.

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
Not available


### getPopoverTimelineTableItemDetail
----
#### :page_with_curl: Description
Create the template of the popover of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' with us directives 

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
Not available


### saveTableItemDetail
----
#### :page_with_curl: Description
Function called when the 'onSaveTableItemDetail' event of the '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' component is fired
Event [onSaveTableItemDetail](#onSaveTableItemDetail) of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'.

#### :bookmark_tabs: Parameters
**event** _(Object)_  - Event data as an object

#### :leftwards_arrow_with_hook: Return
Not available


### showPopover
----
#### :page_with_curl: Description
Function that show popover

#### :bookmark_tabs: Parameters
**event** _(Object)_  - Event data as an object
**element** _(HTML)_  - Template with component structure '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' created
**config** _(Object)_  - Configuration of the display the popover

#### :leftwards_arrow_with_hook: Return
Not available


### onChangeTableModeItem
----
#### :page_with_curl: Description
Function called when the 'onTableModeItemChange' event of the '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)' component is fired
Event [onTableModeItemChange](#onTableModeItemChange) of the component '[onLoadTimelineTableItemDetail](#Timeline-Table-Mode-Detail)'.

#### :bookmark_tabs: Parameters
**event** _(Object)_  - Event data as an object

#### :leftwards_arrow_with_hook: Return
Not available


### editDetailTimelineItemTableMode
----
#### :page_with_curl: Description
This method is used to open the editing popover by the right mouse button event of the timeline vision table mode 

#### :bookmark_tabs: Parameters
**data** _(Object)_ Vis item containing all the properties to be used

#### :leftwards_arrow_with_hook: Return
Not available


### addCommentTimelineItemTableMode
----
#### :page_with_curl: Description
This method is used to open the comment popover by the right mouse button event of the timeline vision table mode 

#### :bookmark_tabs: Parameters
**data** _(Object)_ Vis item containing all the properties to be used

#### :leftwards_arrow_with_hook: Return
Not available


### getPopoverTimelineTableItemComment
----
#### :page_with_curl: Description
Create the template of the comment popover

#### :bookmark_tabs: Parameters
**template** _(HTML)_ Template of display of the comment popover 

#### :leftwards_arrow_with_hook: Return
Not available


### removeTimelineItemTableMode
----
#### :page_with_curl: Description
This method is used to remove the values of the cell by the right mouse button event of the timeline vision table mode 

#### :bookmark_tabs: Parameters
**data** _(Object)_ Vis item containing all the properties to be used

#### :leftwards_arrow_with_hook: Return
Not available


### attachEventListener
----
#### :page_with_curl: Description
This method is used to attach events in components

#### :bookmark_tabs: Parameters
**element** _(DOM element)_ Dom element
**event** _(String)_ Type event to attach in element
**callback** _(Function)_ Function that will be executed in the event

#### :leftwards_arrow_with_hook: Return
Not available


### destroy
----
#### :page_with_curl: Description
This method is used to destroy and remove the component from the DOM tree

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
Not available


# Timeline Table Mode Detail

Table mode detail is the editing of values grouped ​​in a popover, with individual action.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)


## Event Listeners
- [onLoad](#onLoad)
- [onDestroy](#onDestroy)
- [onSaveTableItemDetail](#onSaveTableItemDetail)
- [onTableModeItemChange](#onTableModeItemChange)
- [onTableModeDatePickerChange](#onTableModeDatePickerChange)


### onLoad
----
#### :clock230: When?
This event fires when the user requests the grouped edition of the items.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematic, timelineHandler) { 
    onLoad.addEventListener(() => {
        // do something here
    });
  }
}
```

### onDestroy
----
#### :clock230: When?
This event fires when the grouped edition is destroyed and removed from DOM tree.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematic, timelineHandler) {
    onDestroy.addEventListener(() => { 
        // do something here
    });
  }
}
```

### onTableModeDatePickerChange
----
#### :clock230: When?
This event fires when the date on the datepicker is changed.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>
**event:** _(Object)_ [datetimepicker event](./../../w-datetime-picker/README.md) <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematic, timelineHandler) {
    onTableModeDatePickerChange.addEventListener((event) => {
        const { newValue: current } = event;
    });
  }
}
```

### onTableModeItemChange
----
#### :clock230: When?
This event fires when the value the field is changed.
Least by the date picker that has a specific event.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>
**event:** _(Object)_ change event <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematic, timelineHandler) {
    onTableModeItemChange.addEventListener((event) => {
        const { newValue: current } = event;
    });
  }
}
```

## Handler Methods
- [setData](#setData)

### setData
----
#### :page_with_curl: Description
It sets values ​​to assemble the detail popover for grouped editing.

#### :bookmark_tabs: Parameters
**data:** _(Object)_ Object with values ​​to assemble the detail popover. Object must contain the following properties:</br>
```
visItem: object - Vis item containing all the properties to be used
item: object - Item that has come from timeline component datasource
  attribute: object - (Mandatory) - Meta attribute for creating of the editing component line
  start: moment - (Mandatory) - The moment representing when the cell start
  end: moment - (Mandatory) - The moment representing when the cell stop
  type: String - (Mandatory) - Tipo que será mostrado. Se simples ou multiplos. Values 'tablemode' and 'tablemode_multiple_values'
  values: object - Object with the cell values ​​and that is used to assemble each editing line. When type is tablemode_multiple_values
  value: String - Value of the cell and that is used to assemble editing line. When type is tablemode
  comment: String - Value do comment of the cell
```


# Timeline Table Mode Comment

Table mode comment is used to remove and add a comment in the cell.

- [Methods Comment](#Methods-Comment)


## Methods Comment
- [createCommentTimelineTableItem](#createCommentTimelineTableItem)
- [createTemplateComment](#createTemplateComment)
- [registerCommentButtonAction](#registerCommentButtonAction)
- [createTextArea](#createTextArea)
- [saveTableItemValue](#saveTableItemValue)
- [renderComment](#renderComment)
- [loadTableItemCommentMessages](#loadTableItemCommentMessages)
- [setTextsElements](#setTextsElements)


### createCommentTimelineTableItem
----
#### :page_with_curl: Description
Function that set value data item and call function 'createTemplateComment'.

#### :bookmark_tabs: Parameters
**data** _(Object)_ Values item selected

#### :leftwards_arrow_with_hook: Return
Not available


### createTemplateComment 
----
#### :page_with_curl: Description
Creates the visual representation of the comment popover

#### :bookmark_tabs: Parameters
**data** _(Object)_ Values item selected

#### :leftwards_arrow_with_hook: Return
Not available


### registerCommentButtonAction
----
#### :page_with_curl: Description
Register the actions of the comment popover buttons

#### :bookmark_tabs: Parameters
**data** _(Object)_ Value returned from popover after creation 

#### :leftwards_arrow_with_hook: Return
Not available


### createTextArea
----
#### :page_with_curl: Description
Method that create the component items textarea

#### :bookmark_tabs: Parameters
**data.visItem** _(Object)_ Vis item containing all the properties to be used
**data.item** _(Object)_ Item that has come from timeline component datasource

#### :leftwards_arrow_with_hook: Return
 _(component)_ - Component textarea


### saveTableItemValue
----
#### :page_with_curl: Description
Function that makes the necessary changes when changing values of a comment

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
Not available


### renderComment
----
#### :page_with_curl: Description
Creates the comment in table mode when the cell has the same, using tooltip

#### :bookmark_tabs: Parameters
**element** _(DOM element)_ Element being created in the DOM with its respective comment using tooltip
**comment** _(String)_ String to be rendered inside tooltip

#### :leftwards_arrow_with_hook: Return
Not available


### loadTableItemCommentMessages
----
#### :page_with_curl: Description
Method that requests to backend all the texts used in a context table mode comment

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
Not available


### setTextsElements
----
#### :page_with_curl: Description
Method to set texts of the elements

#### :bookmark_tabs: Parameters
**selector** _(String)_ Selector javascript of the element
**text** _(String)_ Text set of the element

#### :leftwards_arrow_with_hook: Return
Not available
