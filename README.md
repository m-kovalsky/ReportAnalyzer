# [Report Analyzer](https://github.com/m-kovalsky/ReportAnalyzer/releases/latest)


![image](https://user-images.githubusercontent.com/29556918/136777584-e0b753f2-e871-4fbe-a888-8e4fe7094c03.png)


## Purpose

This tool is designed to help Power BI developers/admins match Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview) to specific visuals in their Power BI report. Additionally, Report Analyzer provides a visual interface for prioritizing performance troubleshooting.

## Running the tool

Report Analyzer is an [External Tool](https://docs.microsoft.com/power-bi/transform-model/desktop-external-tools) for [Power BI Desktop](https://powerbi.microsoft.com/desktop). 

In order to take full advantage of the tool, make sure you run the [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) across all tabs in your Power BI report and [export](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-performance-analyzer#saving-performance-information) the results to a .json file. Save the performance data file to the same folder as your Power BI Desktop/Template file(s). Report Analyzer is able to handle multiple .pbix/.pbit files as well as multiple Performance Analyzer .json files.

*NOTE: There is no specific naming requirement performance data .json file.*

1. [Install Report Analyzer](https://github.com/m-kovalsky/ReportAnalyzer/releases/latest).
2. Open Power BI Desktop.
3. Navigate to 'External Tools' in the ribbon.
4. Open Report Analyzer.
5. Select the folder which contains your [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (or Power BI Template) file(s) as well as the Performance Analyzer export (.json) file.

## Compatiblity

This tool is compatible with [Power BI Desktop](https://powerbi.microsoft.com/desktop), Power BI Template and [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data (.json) files. All files must be in the same folder for the tool to integrate all of these files.

## Features

* Visually see [Performance Analyzer](https://docs.microsoft.com/power-bi/create-reports/desktop-performance-analyzer) data overlayed on each visual on a simulated Power BI Desktop canvas.
* Find a specific visual by searching by Visual ID (especially useful for matching Visual IDs from [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview)).
* Easily see all visuals of a specific visual type (i.e. card).
* Use the slider to select a DAX Query Time which highlights visuals (red border) with DAX Query times slower than the selected time (in seconds).
* Hover over a visual to see additional tooltip information.
   *  Visual ID, Visual Name, Page Name, Report Name, DAX Query Time, Render Time, Row Count, Columns Used, Measures Used, Hierarchies Used, Custom Visual Flag, Visual Contains a [Report-Level Measure](https://www.elegantbi.com/post/reportlevelmeasures).
* Click on a visual to copy additional information to the clipboard (including the DAX Query).
* Dark mode out of the box.

## Log Analytics Visual Matching

Report Analyzer can be used to match Log Analytics queries to a specific visual in a Power BI report. In order to do this, follow these steps:

1. Navigate to your [Log Analytics](https://docs.microsoft.com/power-bi/transform-model/log-analytics/desktop-log-analytics-overview) Workspace.
2. Click on 'Logs' within the 'General' category on the left pane.
3. Paste the [Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) query (see below).
4. Add any additional filters to the Kusto query (as desired - perhaps based on time etc.).
5. Copy the VisualId from the Kusto query and search for it within the Report Analyzer's Visual ID slicer (must be connected to the same report).

```kusto
PowerBIDatasetsWorkspace
| where OperationName == "QueryEnd"
| project WorkspaceName
,DatasetId = substring(ApplicationContext,indexof(ApplicationContext,"{\"DatasetId\":")+14,36)
,ReportId  = substring(ApplicationContext,indexof(ApplicationContext,"{\"ReportId\":")+13,36)
,VisualId  = substring(ApplicationContext,indexof(ApplicationContext,",\"VisualId\":")+13,20)
,DurationMs
,EventText
,ApplicationContext
| order by DurationMs desc 
```


*NOTE: A simple way to find the Report ID of a Power BI report is by navigating to the report page within [PowerBI.com]("https://www.powerbi.com") and see the GUID within the URL after 'reports' (highlighted in orange in the screenshot below).*

![image](https://user-images.githubusercontent.com/29556918/137474202-34204afc-a1bc-461c-9324-125cbc521b38.png)


## Disclaimer

* In order to obtain the report metadata, Report Analyzer 'hacks' into the Power BI Desktop file. This type of operation is not supported by Microsoft.
