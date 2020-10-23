# Timeline Table Mode

Timeline vision table mode is option vision of the timeline.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)
- [Design spec](http://design.emr.philips.com.br/library/wip/components/informational/dynamic-flowchart/)
- [Timeline Table Mode Detail](#Timeline-Table-Mode-Detail)


#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const config = {
      start: moment(),
      end: moment().add(1, 'd'),
      groupId: 'NR_SEQUENCIA',
      gap: 2,
    };
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.setConfig(moment().add(5, 'days'));
  }
}
```

### getCurrent
----
#### :page_with_curl: Description
Get the current date of the component

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - Current date time

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getCurrent());
  }
}
```

### setCurrent
----
#### :page_with_curl: Description
Set the current date of the component

#### :bookmark_tabs: Parameters
**current** _(Object)_ Moment to represent the current date

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.setCurrent(moment().add(5, 'days'));
  }
}
```

### getCustomClass
----
#### :page_with_curl: Description
It retrieves the custom class previously set

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(String)_ - custom class name

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getCustomClass());
  }
}
```

### setCustomClass
----
#### :page_with_curl: Description
It adds a class in the main container of timeline header

#### :bookmark_tabs: Parameters
**customClass** _(String)_ - custom class name

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.setCustomClass('my-custom-class');
  }
}
```

### setDataSourceItems
----
#### :page_with_curl: Description
It sets a new datasource into timeline model to be used in the next time draw() method be called.

#### :bookmark_tabs: Parameters
**items** _(Object)_ - VIS items

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();
    const items = // list of items;

    settingBarHandler.setDataSourceItems(items);
  }
}
```

### getDataSourceItems
----
#### :page_with_curl: Description
It retrieves the custom data source previously set

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - VIS items

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.table(settingBarHandler.getDataSourceItems());
  }
}
```

### addTimelineButtons
----
#### :page_with_curl: Description
It adds custom buttons in timeline edges.

#### :bookmark_tabs: Parameters
**jump** _(int)_  - The amount of time in minutes that when the button is clicked should change in timeline range
**callback** _(Function)_ - A callback to be executed at the end of the process

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.addTimelineButtons(250, () => {
      // do shomething here
    });
  }
}
```

### setFlagDescriptionFormatter
----
#### :page_with_curl: Description
It sets a custom formatter to render in a new way the label inside datetimepicker area.

#### :bookmark_tabs: Parameters
**fn** _(Function)_  - The new formatter that must return a String.

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.setFlagDescriptionFormatter(() => moment(this.myCurrentDate).format('LT'));
  }
}
```

### setLayoutTimeline
----
#### :page_with_curl: Description
Define the columns layout of the Timeline<br>
The schematics layout recommended is 12 columns to provide better visualization of<br>
data list and Timeline.<br>
Within 12 columns the full layout uses 6x6, 4x8, 8x4 (Data list x Timeline).<br>
To define Timeline you can choose 4, 8 or 6 columns and pass as a parameter.<br>
Setting a different value, the Timeline will assume the default option of 6 columns.<br>

#### :bookmark_tabs: Parameters
**columns** _(number)_  - The number of columns to be used in timeline layout

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();
    const columnsCount = 8; 

    settingBarHandler.setLayoutTimeline(columnsCount);
  }
}
```

### getAutocompleteHandler
----
#### :page_with_curl: Description
Return autocomplete component handler 

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - Autocomplete handler

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getAutocompleteHandler());
  }
}
```

### getDatePickerHandler
----
#### :page_with_curl: Description
Return datepicker component handler 

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - datepicker handler

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getDatePickerHandler());
  }
}
```

### getIntervalListBoxHandler
----
#### :page_with_curl: Description
Return interval listbox component handler 

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - interval listbox handler

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getIntervalListBoxHandler());
  }
}
```

### getGapListBoxHandler
----
#### :page_with_curl: Description
Return gap listbox component handler 

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
_(Object)_ - gap listbox handler

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    console.log(settingBarHandler.getGapListBoxHandler());
  }
}
```

### setDatePickerMode
----
#### :page_with_curl: Description
It sets the new mode that datetimepicker should be.

#### :bookmark_tabs: Parameters
**mode** _(Object)_ - The new [mode](./../../w-datetime-picker/w-datetime-picker.constant.js) that datetimepicker should obey.

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
@Controller({ domain: 'atePac/atePac', code: 123456 })
export default class Timeline extends Timeline {

  onLoad(schematics, timeline) {
    const settingBarHandler = timelineHandler.getTimelineSettingBarHandler();

    settingBarHandler.setDatePickerMode(DateTimePickerOptions.MODE.DATE_TIME_SHORT);
  }
}
```

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

### setConfig
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
