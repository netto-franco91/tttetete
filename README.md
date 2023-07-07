

# Line Chart JS - (Vital signs) <br>
The "LINE_CHART_JS" type chart basically has the same structure as the "LINE" type, but it was created so that we can customize the 'point styles' so that we can customize the 'points'.</br>

To use the 'LINE_CHART_JS' type chart, we need to make the change via 'BACKEND', as this type of chart is a motivation of the 'LINE' type, so to use it we have to make some configurations and change the default 'Line' type.</br>


#### :warning: Note: 
_The functionality of the chart types 'LINE' and 'LINE_CHART_JS' have practically the same behaviors.</br>
However, in order to customize the 'point styles', we had to use another graphics library and, for this reason, there may be a small visual or behavioral difference between them._


#### :pencil2: Examples: <br>

_Setting to change chart type to 'LINE_CHART_JS'_<br>
```java
wChartSeriesListDTO.getChartProperties().setType(SerieType.LINE_CHART_JS);
```

_Configuration to change point style, we have these options: 'CIRCLE', 'CROSS', 'CROSS_ROT', 'DASH', 'LINE', 'RECT', 'RECT_ROUNDED', 'RECT_ROT', 'STAR', 'TRIANGLE'_<br>

```java
wChartSeriesListDTO.getChartProperties().addPointsStyles(PointStyleEnum.CIRCLE);
```

