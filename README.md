# Line Chart JS - (Vital signs) <br>
The "LINE_CHART_JS" type chart basically has the same structure as the "LINE" type, but it was created so that we can customize the 'point styles'.</br>

To use the 'LINE_CHART_JS' type chart, we need to make the change via 'BACKEND', as this type of chart is a motivation of the 'LINE' type, so to use it we have to make some configurations and change the default 'Line' type.</br>


#### :warning: Note: 
_The functionality of the chart types 'LINE' and 'LINE_CHART_JS' have practically the same behaviors.</br>
However, in order to customize the 'point styles', we had to use another graphics library and, for this reason, there may be a small visual or behavioral difference between them._


#### :pencil2: Examples: <br>

_Setting to change chart type to 'LINE_CHART_JS'_<br>
```java
WChartProperties chartProperties = new WChartProperties();
chartProperties.setType(SerieType.LINE_CHART_JS);
```

_Configuration to change point style, we have these options: 'CIRCLE', 'CROSS', 'CROSS_ROT', 'DASH', 'LINE', 'RECT', 'RECT_ROUNDED', 'RECT_ROT', 'STAR', 'TRIANGLE'_<br>

```java
WChartProperties chartProperties = new WChartProperties();
chartProperties.addPointsStyles(PointStyleEnum.CIRCLE);
```

#### Full Example:
```java
import br.com.philips.tasy.dto.shared.wchart.WChartProperties;
import br.com.philips.tasy.dto.shared.wchart.WChartSeriesDTO;
import br.com.philips.tasy.dto.shared.wchart.WChartSeriesValueDTO;
import br.com.wheb.action.wChart.AbstractWChartPostProcessingAction;
import br.com.wheb.annotations.NamedAction;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.Map;

@NamedAction(name = "postProcessSeries", referedInterface = AbstractWChartPostProcessingAction.class)
public class TecTesF1WChartPostProcessingAction extends AbstractWChartPostProcessingAction {

    @Override
    public ArrayList<WChartSeriesDTO> build(ArrayList<WChartSeriesDTO> series, Integer dictionaryCode, Map<String, Object> params,
                                            ArrayList<HashMap> aditionalSeries, Map<String, Object> filterValues, WChartProperties chartProperties) {
        ArrayList<WChartSeriesValueDTO> values1stSerie = new ArrayList();
        ArrayList<WChartSeriesValueDTO> values2ndSerie = new ArrayList();
        ArrayList<WChartSeriesValueDTO> values3rdSerie = new ArrayList();
        ArrayList<WChartSeriesValueDTO> values4thSerie = new ArrayList();
        String[] dates = {
            "01/07/2018",
            "02/07/2018",
            "03/07/2018",
            "04/07/2018",
            "05/07/2018",
            "06/07/2018",
            "07/07/2018",
            "08/07/2018",
            "09/07/2018",
            "10/07/2018",
        };

        for (int i = 0; i < 10; i++) {
            values1stSerie.add(createValueDTO(dates[i],400 - 10 * i));
            values2ndSerie.add(createValueDTO(dates[i],50 * i));
            values3rdSerie.add(createValueDTO(dates[i],200 - 2 * i));
            if (i == 1) {
                values4thSerie.add(createValueDTO(dates[i], 0));
            } else {
                values4thSerie.add(createValueDTO(dates[i],100 * i - 75));
            }
        }

        for (WChartSeriesValueDTO value : values1stSerie) {
            series.get(0).getValues().add(value);
        }
        for (WChartSeriesValueDTO value : values2ndSerie) {
            series.get(1).getValues().add(value);
        }
        for (WChartSeriesValueDTO value : values3rdSerie) {
            series.get(2).getValues().add(value);
        }
        for (WChartSeriesValueDTO value : values4thSerie) {
            series.get(3).getValues().add(value);
        }

        // Configuration of chart properties 'LINE_CHART_JS'
        // Sets to type 'LINE_CHART_JS'
        chartProperties.setType(SerieType.LINE_CHART_JS);
        
        // Sets 'point style' of the FIRST series to type 'TRIANGLE'
        chartProperties.addPointsStyles(PointStyleEnum.TRIANGLE);

        // Sets 'point style' of the SECOND series to type 'STAR'
        chartProperties.addPointsStyles(PointStyleEnum.STAR);

        // Sets 'point style' of the THIRD series to type 'CIRCLE'
        chartProperties.addPointsStyles(PointStyleEnum.CIRCLE);

        // Sets 'point style' of the FOURTH series to type 'RECT_ROUNDED'
        chartProperties.addPointsStyles(PointStyleEnum.RECT_ROUNDED);
        
        return series;
    }

    private WChartSeriesValueDTO createValueDTO(Object axisX, Object axisY) {
        WChartSeriesValueDTO value = new WChartSeriesValueDTO();
        value.setPrediction(true);
        value.setValueAxisX(axisX);
        value.setValueAxisY(axisY);
        return value;
    }
}
```



# Region DragDrop Resizer

This component was created with the aim of enabling the 'resizer' of panels and regions of the Tasy system.
With this we can resize each screen, allowing the user to organize the system screens as he wishes.

> :warning: _To activate this configuration, it will be necessary **to migrate the function to use DX schematics** and **configure in Regions what type of 'resizer'** you would like to create for the panel._

To activate resizing it will be necessary to change the Region's 'Layout Resize' field.

The options for the Layout Resize field are: **Horizontal, Vertical and Both.**

**_Example_**: to activate the resizer in a template that has two horizontal areas. 
You must go to the first area and change the 'Layout Resizer' field to the horizontal value and so on.

Exemples:

- Only Region 0 and 1 Vertical
![image](https://github.com/user-attachments/assets/f09da16c-686d-4ce0-bfe7-b52d851a238b)

config:
![image](https://github.com/user-attachments/assets/2296c8c0-ebf8-4063-9668-b2ddc899bd4e)

![image](https://github.com/user-attachments/assets/92a4a60b-f1a1-409c-b3b2-d03b615e8fda)

![image](https://github.com/user-attachments/assets/3360e305-a5e8-4119-9874-e1ecf5402138)

- Region 0 and 1 Vertical with region 2 horizontal
![image](https://github.com/user-attachments/assets/db3bf3d8-71f0-4fb5-81a5-d15e8990889d)

config:

![image](https://github.com/user-attachments/assets/2296c8c0-ebf8-4063-9668-b2ddc899bd4e)

![image](https://github.com/user-attachments/assets/2592353c-6b00-4c96-b9bb-5662770cc292)

![image](https://github.com/user-attachments/assets/3360e305-a5e8-4119-9874-e1ecf5402138)

- Horizontal and Vertical in the 4 regions
![image](https://github.com/user-attachments/assets/c8d562b8-84b5-4926-a08f-21db12c76b94)

config:
![image](https://github.com/user-attachments/assets/f0c5515b-601c-4279-abd1-ed76ee6e26f6)

![image](https://github.com/user-attachments/assets/8d5a0806-f3b1-4c4e-adbb-33ee1ec4aee3)

![image](https://github.com/user-attachments/assets/37efb095-729b-4498-814b-7447a92db3b4)

![image](https://github.com/user-attachments/assets/943a980e-41bd-4438-9df3-798f902938d5)

