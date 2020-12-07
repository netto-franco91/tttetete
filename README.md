# Flowsheet

Class with the implementations of the methods used by the Flowsheet component. <br />
The framework is responsible for the automatic execution of the methods, but they should be created and customized by DEV. <br />

- [Methods](#Methods)

## Methods
- [Save](#Save)
- [Submit](#Submit)
- [getMetadata](#getMetadata)
- [getDatasource](#getDatasource)
- [getFormMetadata](#getFormMetadata)
- [getSectionMetadata](#getSectionMetadata)
- [getSectionDatasource](#getSectionDatasource)


### Save
----
#### :page_with_curl: Description
Endpoint to be used in order to save linkedData values.

#### :bookmark_tabs: Parameters
**request:** _(Object)_  Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
_(object)_ - true if saved performed sucessfully, false otherwise. <br />
:warning: _(throws)_ - Exception - If some error occurs during save action. <br />

#### :pencil2: Example
**Request Payload:**
```json
[
  {
    "@class":"br.com.wheb.vo.componentes.flowsheet.FlowsheetRequestVO",
    "actionName": "tectesf1FlowsheetAction",
    "dtoCode": "1157339",
    "parameters": {
        "encounter": 25246
    }
  }
]
```

### Submit
----
#### :page_with_curl: Description
Endpoint to be used in order to release linkedData values.

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
_(object)_ - true if saved performed sucessfully, false otherwise. <br />
:warning: _(throws)_ - Exception - If some error occurs during save action. <br />

#### :pencil2: Example
**Request Payload:**
```json
[
  {
    "@class":"br.com.wheb.vo.componentes.flowsheet.FlowsheetRequestVO",
    "actionName": "tectesf1FlowsheetAction",
    "dtoCode": "1157339",
    "parameters": {
        "encounter": 25246
    }
  }
]
```


### getMetadata
----
#### :page_with_curl: Description
Endpoint to be used to get a flowsheet metadata.

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
**FlowsheetMetadata:** _(object)_ - Object containing flowsheet sections and timeline properties. <br />
  - **timelineProperties** _(FlowsheetTimelineProperties)_ - Properties to start the flowsheet timeline. <br />
  - **sections** _(List<FlowsheetSectionMetadata>)_ - List of sessions to be loaded into the flowsheet. <br />
:warning: _(throws)_ - Exception - If some error occurs during fetching its metadata. <br />

#### :pencil2: Example
**Request Payload:**
```json
[
  {
    "@class": "br.com.wheb.vo.componentes.flowsheet.FlowsheetRequestVO",
    "actionName": "tectesf1FlowsheetAction",
    "dtoCode": "1157339",
    "parameters": {
        "encounter": 25246
    }
  }
]
```
**Response Payload:**
```json
{
    "@class": "br.com.wheb.vo.componentes.flowsheet.metadata.FlowsheetMetadata",
    "sections": [{
        "0": {
            "linkedDataId": 178,
            "title": "Vital signs",
            "rowValues": [{
                "0": {
                    "description": "Abdominal,
                    "id": "2196981",
                    "timelineTableItems: [{"@class": "br.com.wheb.vo.componentes.flowsheet.metadata.TimelineTableItem",…},…],
                    "listValueCustomColumn: [{"@class": "br.com.wheb.vo.componentes.flowsheet.metadata.TimelineCustomColumn",…},…],
                    "timelineTableRow: {"metaAtribute": {"@class": "br.com.wheb.vo.componentes.metaData.MetaAtributo", "componente": "TEXTBOX",…}}
                }
            }]
        }
    }],
    "timelineProperties": {
        ""@class": "br.com.wheb.vo.componentes.flowsheet.metadata.FlowsheetTimelineProperties",
        "groupId": "ID",
        "timelineGap": 2,
        "timelineLength": 24,
        "timelineOffset": -20
    }
}
```

### getDatasource
----
#### :page_with_curl: Description
Endpoint to be used to get a flowsheet datasource.

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
**FlowsheetDatasource:** _(object)_ - Object containing flowsheet datasource (values to be shown in its datagrid rows) and its timelines items. <br />
  - **sections** _(List<FlowsheetSectionDatasource>)_ - List of values ​​to be loaded from the flowsheet. <br />
:warning: _(throws)_ - Exception - If some error occurs during fetching its datasource. <br />

#### :pencil2: Example
**Request Payload:**
```json
[
  {
    "@class": "br.com.wheb.vo.componentes.flowsheet.FlowsheetRequestVO",
    "actionName": "tectesf1FlowsheetAction",
    "dtoCode": "1157339",
    "parameters": {
        "encounter": 25246
    }
  }
]
```
**Response Payload:**
```json
{
    "@class": "br.com.wheb.vo.componentes.flowsheet.datasource.FlowsheetDatasource",
    "sections": [{
        "0": {
            "linkedDataId": 178,
            "rowValues": [{
                "0": {
                    "avgValue": 50.75,
                    "chartItems": [{
                        0": {
                            "color": "#3262DB",
                            "data": {"element": "ArrowAverage1", "info": ["Nurse - Flávia Miranda", "<div>Heart Rate: 78bpm</div>"]},
                            "id": "37120687432105502",
                            "maxValue": 83,
                            "minValue": 36,
                            "start": {"tipo": "INSTANT", "@class": "java.time.Instant", "value": "2020-12-07T07:00:00Z"},
                            "type": "arrow-avg"
                        }
                    }],
                    "id": "7904724",
                    "maxValue": 85,
                    "metadataRowId": "2196983",
                    "minValue": 29,
                    "timelineItems": [{
                        "0":  {
                            "data": {"element": "Point3"},
                            "extendable": true,
                            "id": "37120687432053845",
                            "start": {"tipo": "INSTANT", "@class": "java.time.Instant", "value": "2020-12-07T07:00:00Z"},
                            "status": "APPLIED",
                            "type": "point",
                        }
                    }],
                    "value": "174",
                }
            }]
        }
    }],
}
```

### getFormMetadata
----
#### :page_with_curl: Description
Endpoint to be used to get a formulary metadata (wmdetail).

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
**Metadata:** _(object)_ - Object containing the metadata of formulary that will be shown. <br />
:warning: _(throws)_ - Exception - If some error occurs during fetching its form metadata. <br />


### getSectionMetadata
----
#### :page_with_curl: Description
Endpoint to be used in order to return a specific section metadata.

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
**FlowsheetSectionMetadata:** _(object)_ - Section metadata values. <br />
  - **rowValues** _(List<FlowsheetMetadataRow>)_ - Grid line with table mode data, description of the line, meta attribute, id line and values of the column custom list. <br />
    - **id** _(String)_ - Identification id. <br />
    - **description** _(String)_ - Description of line of the Metadata. <br />
    - **timelineTableRow** _(FlowsheetTimelineTableRow)_ - A class containing all the information needed to build timeline table items. <br />
    - **metaAtribute** _(MetaAtributo)_ - Attribute in order to be used to build the visual component that will be used to edit values (listbox, textboxes, segmented-control, datetime picker...). <br />
      - **timelineTableValues** _(List)_ - List to be used to send the values saved in a specific time (multiples values in the same date range, will build the popover in the timeline cell (+2, +3...). TimelineValue contains the following attributes: value (Object) and start (LocalDateTime). <br />
      - **timelineTableComments** _(List)_ - A list to send all the comments applied in a specific time. TimelineTableComment contains the following attributes: value (Object) and start (LocalDateTime). <br />
      - **timelineTableItems** _(List<TimelineTableDefaultItem>)_ - **Exclusive use of the framework**. <br />
      - **listValueCustomColumn** _(List<TimelineCustomColumn>)_ - List of custom columns. Class values: value and id. <br />
  - **linkedDataId** _(Integer)_ - Id Linked Data. <br />
  - **title** _(String)_ - Section description. <br />
  - **listCustomColumn** _(List<FlowsheetCustomColumn>)_ - List of custom columns. <br />
:warning: _(throws)_ - Exception - If some error occurs during fetching its form metadata. <br />

#### :pencil2: Example
[Example](https://github.com/philips-emr/tasy-framework-backend/blob/dev/tasy-legacy-samples/src/main/java/com/philips/tasy/app/tectes/tectesf1/flowsheet/TecTesF1FlowsheetAction.java#L86)<br />


### getSectionDatasource
----
#### :page_with_curl: Description
Endpoint to be used in order to return a specific section datasource.

#### :bookmark_tabs: Parameters
**request:** _(Object)_ - Object containing the parameters to be used by this method. <br />

#### :leftwards_arrow_with_hook: Return
**FlowsheetSectionDatasource:** _(object)_ - Section datasource values. <br />
  - **rowValues** _(List<FlowsheetDatasourceRow>)_ - List with the values ​​of the chart and timeline mode (default view), which are used to assemble the views. <br />
    - **timelineItems** _(List<WTimelineItem>)_ - Items to load data from the timeline view (default). <br />
    - **chartItems** _(List<WTimelineItem>)_ - Items to load the chart view. <br />
    - **metadataRowId** _(String)_ - Id row. <br />
    - **minValue** _(int)_ - Minimum value for displaying the chart. <br />
    - **maxValue** _(int)_ - Maximum value for displaying the chart. <br />
    - **avgValue** _(double)_ - Average value for displaying the chart. <br />
    - **value** _(String)_ - Row value. <br />
    - **id** _(String)_ - Identification id. <br />
  - **linkedDataId** _(Integer)_ - Id Linked Data. <br />
:warning: _(throws)_ - Exception - If some error occurs during fetching its form metadata. <br />

#### :pencil2: Example
[Example](https://github.com/philips-emr/tasy-framework-backend/blob/dev/tasy-legacy-samples/src/main/java/com/philips/tasy/app/tectes/tectesf1/flowsheet/TecTesF1FlowsheetAction.java#L77)<br />
