# Timeline Table Mode

Timeline vision table mode is option vision of the timeline.

- [Example Use](#Example-Use)
- [Event](#Event)
- [Methods](#Methods)


## Example Use
- [Set BackEnd](#Set-BackEnd)


### Set BackEnd
----
#### :clock230: When?
Example of how to set the values ​​to load the vision table mode of the timeline.
Below we will see the classes that should be used to set the values.

#### :bookmark_tabs: Parameters
**FlowsheetMetadataRow:** _(Object)_ - Class with the following parameters: <br>
  - **description:** _(String)_ - Description of line of the Metadata 
  - **id:** _(String)_ - Identification id
  - **timelineTableItems:** - _(List<TimelineTableDefaultItem>)_ - Use of the framework
  - **timelineTableRow:** - _(FlowsheetTimelineTableRow)_ - Set the values ​​for the table mode row

**FlowsheetTimelineTableRow:** _(Object)_ - Class with the following parameters: <br>
  - **metaAtribute:** _(MetaAtributo)_ - Default class to set MetaAtributo
  - **timelineTableValues:** _(List<TimelineValue>)_ - List value for timeline vision table mode. Class com attribute: value _(Object)_ and start _(LocalDateTime)_
  - **timelineTableComments:** - _(List<TimelineTableComment>)_ - List comment. Class com attribute: value _(Object)_ and start _(LocalDateTime)_


#### :pencil2: Example
![Class FlowsheetMetadataRow](./../../../../assets/framework/w-timeline/class-flowsheet-metadata.png)<br />

![Class FlowsheetTimelineTableRow](./../../../../assets/framework/w-timeline/class-flowsheet-timeline.png)<br />

![Exemple of how to set a MetaAttribute](./../../../../assets/framework/w-timeline/ex-add-metaattribute.png)<br />

![Exemple of how to set a Values](./../../../../assets/framework/w-timeline/ex-add-values.png)<br />

![Exemple of how to set a Comment](./../../../../assets/framework/w-timeline/ex-add-comment.png)<br />



## Event
- [onTableModeDatePickerChange](#onTableModeDatePickerChange)
- [onTableModeItemChange](#onTableModeItemChange)
- [onSaveTableItemDetail](#onSaveTableItemDetail)


### onTableModeDatePickerChange
----
#### :clock230: When?
This event is fired when change event is triggered by the field date picker at the editing popover of the table mode.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onTableModeDatePickerChange(schematic, component) {
    // your business logic
  }
}
```

### onTableModeItemChange
----
#### :clock230: When?
This event is fired when change event is triggered by the field at the editing simple or na editing popover of the table mode. <br />
Least by the date picker that has a specific event.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onTableModeItemChange(schematic, component) {
    // your business logic
  }
}
```

### onSaveTableItemDetail
----
#### :clock230: When?
This event is fired when change event is triggered by button 'Save' at the editing popover of the table mode.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onSaveTableItemDetail(schematic, component) {
    // your business logic
  }
}
```


## Event
- [getTableModeValues](#getTableModeValues)
- [setTableMode](#setTableMode)
- [isTableMode](#isTableMode)

### getTableModeValues
----
#### :page_with_curl: Description
It returns the values of the timeline vision table mode

#### :bookmark_tabs: Parameters
Not available.

#### :leftwards_arrow_with_hook: Return
_(object)_ - Object with the value item selected e value of the cell 

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onSave(schematics, timelineHandler) {
    const values = timelineHandler.getTableModeValues();
  }
}
```

### setTableMode
----
#### :page_with_curl: Description
It is going to activate the table mode in the timeline.

#### :bookmark_tabs: Parameters
**value:** _(boolean)_ It is going to define if the table mode will be activated or not.</br>

#### :leftwards_arrow_with_hook: Return
Not available.

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timelineHandler) {
    timelineHandler.setTableMode(true);
  }
}
```

### isTableMode
----
#### :page_with_curl: Description
It is going to return if the table mode is activated or not.

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(boolean)_ - Return true if the table mode is activated.

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timelineHandler) {
    if (timelineHandler.isTableMode()) {
      console.log('The table mode is activated.');
    }
  }
}
```
