# Sign_In_Location
This workbook allows the administraitor to obtain real time information related to the location and details of anyone that accesses resources in a determined sub.
It displays a map showing exactly where this requests came from and a table with the specifics of the users such as name, ip or id.
```
{
  "type": 3,
  "content": {
    "version": "KqlItem/1.0",
    "query": "SigninLogs\n| summarize count() by UserDisplayName, Location, AuthenticationMethodsUsed, IPAddress, Id\n| order by count_ desc",
    "size": 0,
    "timeContext": {
      "durationMs": 2592000000
    },
    "queryType": 0,
    "resourceType": "microsoft.operationalinsights/workspaces",
    "visualization": "map",
    "mapSettings": {
      "locInfo": "CountryRegion",
      "locInfoColumn": "Location",
      "sizeSettings": "Location",
      "sizeAggregation": "Count",
      "labelSettings": "Location",
      "legendMetric": "count_",
      "legendAggregation": "Sum",
      "itemColorSettings": {
        "nodeColorField": "count_",
        "colorAggregation": "Sum",
        "type": "heatmap",
        "heatmapPalette": "greenRed"
      }
    }
  },
  "name": "query - 2"
}
```
