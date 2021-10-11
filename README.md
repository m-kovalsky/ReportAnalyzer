# [Report Analyzer](https://github.com/m-kovalsky/ReportAnalyzer/releases/latest)

### Purpose

This tool is designed to help Power BI developers/admins match Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview) to specific visuals in their Power BI report. Additionally, Report Analyzer provides a visual interface for prioritizing performance troubleshooting.

### Running the tool

Report Analyzer is an [External Tool](https://docs.microsoft.com/power-bi/transform-model/desktop-external-tools) for [Power BI Desktop](https://powerbi.microsoft.com/desktop). 

1. Download Report Analyzer.
2. Open Power BI Desktop.
3. Navigate to 'External Tools' in the ribbon.
4. Open Report Analyzer.
5. Select the folder which contains your Power BI Desktop (or Power BI Template) file as well as the Performance Analyzer export (.json) file.

This tool is best used after running [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) across all tabs in your Power BI report and [exporting the performance data](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-performance-analyzer#saving-performance-information).

### Features

* Visually see [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data on a simulated Power BI Desktop canvas.
* Find a specific visual by searching by Visual ID (especially useful for matching Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview)).
* Easily see all visuals of a specific visual type (i.e. card).
* Use the slider to select a DAX Query Time which highlights visuals (red border) with DAX Query times slower than the selected time (in seconds).
* Hover over a visual to see additional tooltip information.
   *  Visual ID, Visual Name, Page Name, Report Name, DAX Query Time, Render Time, Row Count, DAX Query, Columns Used, Measures Used, Hierarchies Used, Custom Visual Flag, Visual Contains a [Report-Level Measure](https://www.elegantbi.com/post/reportlevelmeasures).
* Click on a visual to copy additional information to the clipboard.

### Disclaimer

* In order to obtain the report metadata, Report Analyzer 'hacks' into the Power BI Desktop file. This type of operation is not supported by Microsoft.
