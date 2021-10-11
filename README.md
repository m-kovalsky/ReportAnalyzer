# Report Analyzer

### Purpose

### Running the tool

Report Analzyer is an [External Tool](https://docs.microsoft.com/power-bi/transform-model/desktop-external-tools) for [Power BI Desktop](https://powerbi.microsoft.com/desktop/). 

1. Download Report Analyzer.
2. Open Power BI Desktop.
3. Navigate to 'External Tools' in the ribbon.
4. Open Report Analyzer.

### Features

* Visually see [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data on a simulated Power BI Desktop canvas.
* Find a specific visual by searching by Visual ID (especially useful for matching Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview)).
* Easily see all visuals of a specific visual type (i.e. card).
* Use the slider to select a DAX Query Time which highlights visuals (red border) with DAX Query times slower than the selected time (in seconds).
* Hover over a visual to see additional tooltip information.
   *  DAX Query, Columns Used, Measures Used, Hierarchies Used, Custom Visual Flag, Visual Contains a Report-Level Measure
* Click on a visual to copy additional information to the clipboard.
