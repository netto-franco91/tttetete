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
