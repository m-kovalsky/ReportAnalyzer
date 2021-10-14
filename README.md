# [Report Analyzer](https://github.com/m-kovalsky/ReportAnalyzer/releases/latest)


![image](https://user-images.githubusercontent.com/29556918/136777584-e0b753f2-e871-4fbe-a888-8e4fe7094c03.png)


### Purpose

This tool is designed to help Power BI developers/admins match Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview) to specific visuals in their Power BI report. Additionally, Report Analyzer provides a visual interface for prioritizing performance troubleshooting.

### Running the tool

Report Analyzer is an [External Tool](https://docs.microsoft.com/power-bi/transform-model/desktop-external-tools) for [Power BI Desktop](https://powerbi.microsoft.com/desktop). 

1. [Install Report Analyzer](https://github.com/m-kovalsky/ReportAnalyzer/releases/latest).
2. Open Power BI Desktop.
3. Navigate to 'External Tools' in the ribbon.
4. Open Report Analyzer.
5. Select the folder which contains your [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (or Power BI Template) file as well as the Performance Analyzer export (.json) file.

In order to take full advantage of the tool, make sure you run the [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) across all tabs in your Power BI report and [export](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-performance-analyzer#saving-performance-information) it to a .json file. Make sure to save the performance data file to the same folder as your Power BI Desktop/Template file(s). There is no specific naming requirement performance data .json file.

### Compatiblity

This tool is compatible with [Power BI Desktop](https://powerbi.microsoft.com/desktop), Power BI Template and [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data (.json) files. All files must be in the same folder for the tool to integrate all of these files.

### Features

* Visually see [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data on a simulated Power BI Desktop canvas.
* Find a specific visual by searching by Visual ID (especially useful for matching Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview)).
* Easily see all visuals of a specific visual type (i.e. card).
* Use the slider to select a DAX Query Time which highlights visuals (red border) with DAX Query times slower than the selected time (in seconds).
* Hover over a visual to see additional tooltip information.
   *  Visual ID, Visual Name, Page Name, Report Name, DAX Query Time, Render Time, Row Count, Columns Used, Measures Used, Hierarchies Used, Custom Visual Flag, Visual Contains a [Report-Level Measure](https://www.elegantbi.com/post/reportlevelmeasures).
* Click on a visual to copy additional information to the clipboard (including the DAX Query).
* Dark mode out of the box.

### Disclaimer

* In order to obtain the report metadata, Report Analyzer 'hacks' into the Power BI Desktop file. This type of operation is not supported by Microsoft.
