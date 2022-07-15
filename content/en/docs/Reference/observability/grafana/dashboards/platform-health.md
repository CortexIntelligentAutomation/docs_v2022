---
title: "Platform Health"
linkTitle: "Platform Health"
description: "Information about the Platform Health Dashboard."
weight: 20
---

# {{< param title >}}

## Description

This dashboard provides the information required to analyse the health of the Cortex Innovation platform.

It is split into 5 main sections:

- Overview
- Availability
- Requests
- Errors
- Duration

There are several filters available to filter the data to a more fine-grained level as necessary.

## Filters

There are 9 filters available on this dashboard:

|Filter  |Description|
|--------|-----------|
| Tenant | List of tenants. Defaulted to All. |
| System | List of systems. Defaulted to All. |
| Node | List of hosts that processed the requests. Defaulted to All. |
| API | List of the API endpoints found in the HTTP requests. Defaulted to All. |
| Status Code | List of [status codes][] found in the HTTP responses. Defaulted to All. |
| Result | List of results found in the HTTP responses. Defaulted to All. |
| Initiator IP Address | List of IP addresses for the initiators of the requests. Defaulted to All. |
| Interval | List of intervals to perform the time series aggregations upon. This only affects the graphs on this dashboard.<br> <br>The available values for this filter are auto, 1m, 10m, 30m, 1h, 6h, 12h, 1d, 7d, 14d, 30d.<br> <br>If *auto* is selected, as is the default, Grafana will aggregate to a level it deems appropriate for the time range specified. |
| Custom Filter | Enables filtering on all available values, including those not exposed by default. |

All filters (excluding Interval and Custom Filter) will display their list of available options dependent on the preceding filters selected.

## Report Sections

### Overview

This section displays key platform health metrics for the specified time range.

Note: The Interval filter does not affect these values.

#### Availability

This tile displays the availability of the platform by calculating the successful requests / total requests during the specified time range. Successful requests are all requests that do not result in a 5xx HTTP response, 4xx responses are considered successful in this scenario. This tile has thresholds set to colour code the tile depending on the value.  These thresholds can be [customised][customise threholds], however the default thresholds are:

| Threshold | Value | Colour |
|------------------|-----------|------------|
| OK  | &gt;= 95% | green |
| WARNING | &gt;= 90% | orange |
| CRITICAL | &lt; 90% | red |

#### Total Requests

This tile displays the total number of requests during the specified time range.

#### Errored Requests

This tile displays the total number of errored requests during the specified time range. Errored requests are all requests that result in an unknown or 5xx HTTP response, 4xx responses are considered successful in this scenario. This tile has thresholds set to colour code the tile depending on the value.  These thresholds can be [customised][customise threholds], however the default thresholds are:

| Threshold | Value | Colour |
|------------------|-----------|------------|
| OK  | 0 | green |
| CRITICAL | &gt;= 1 | red |

#### Mean Request Duration

This tile displays the mean duration for requests during the specified time range.

Note: Certain APIs may take significantly longer than others skewing the result.

### Availability

This section displays the availability of the Cortex Innovation platform and consists of 1 panel.

#### Availability

This graph displays the availability of the Cortex Innovation Platform by calculating successful requests / total requests. Successful requests are all requests that do not result in a 5xx HTTP response, 4xx responses are considered successful in this scenario.

Each data point value is calculated by aggregating requests based on the Interval filter. If we have no data for the previous interval, the line will be [broken](#breaks-in-graph-lines) as we do not know the availability at this time.

This graph has thresholds set to colour code the background to show when availbility drops into warning and critical levels. These thresholds can be [customised][customise threholds], however the default thresholds are:

| Threshold | Value | Colour |
|------------------|-----------|------------|
| OK  | &gt;= 95% | green |
| WARNING | &gt;= 90% | orange |
| CRITICAL | &lt; 90% | red |

This graph is configured to start the availability at 80%, however if the availability drops below this level the scale will modify to show the lowest availability level.

### Requests

This section provides information regarding the history of the requests processed by the Cortex Innovation platform for the specified time range and consists of 2 panels.

#### Requests

This graph displays

- the count of all requests. Each data point value is calculated by aggregating requests based on the Interval filter.
- the count of all requests per second.

#### Top 10 Responses by Total Count

This table displays the Top 10 HTTP responses that occured during the specified time range with their mean, minimum and maximum duration in seconds.

Note: The Interval filter does not affect this list.

### Errors

This section provides information regarding the errored request history for the specified time range and consists of 2 panels.

#### Errored Requests

This graph displays the:

- count of errored requests
- count of all requests

Each data point value is calculated by aggregating requests based on the Interval filter.

Errored requests are all requests that result in an unknown or 5xx HTTP response, 4xx responses are considered successful in this scenario.

#### Top 10 Error Responses by Error Count

This table displays the Top 10 HTTP error responses that occured during the specified time range with their mean, minimum and maximum duration in seconds. Errored requests are all requests that result in an unknown or 5xx HTTP response, 4xx responses are considered successful in this scenario.

Note: The Interval filter does not affect this list.

### Duration

This section provides information regarding the request duration history for the specified time range and consists of 2 panels.

Note: Certain APIs may take significantly longer than others skewing the results.

#### Request Duration

This graph displays the:

- mean duration in seconds for all requests
- minimum duration in seconds for all requests
- maximum duration in seconds for all requests

Each data point value is calculated by aggregating requests based on the Interval filter.

#### Top 10 Responses by Mean Duration

This table displays the top 10 HTTP responses that occured during the specified time range with their mean, minimum and maximum duration in seconds.

Note: The Interval filter does not affect this list.

## Remarks

### Unknown values

It is possible that the dashboards may display flow execution requests that have an unknown status code or result. The chances of this occurring are minimal. However, this will occur if a request has failed without returning the reason.  If we do not know the status code or result, we cannot assign it to the relevant category and therefore, these logs will have their status code and/or result recorded as Unknown.

### Breaks in Graph Lines

When appropriate, there may occur breaks in the line graphs, this is relevant to the Availability graph.  When there is no data, it is not appropriate to say that the availability is the same as the previous data point or that it is zero as if there is no data, we cannot accurately reflect the data at this point and therefore, the line will break.

### Known Limitations

#### Graphs do not reset to zero

There is a limitation in Grafana where the graph does not always return to the zero line when there is no data for a given time point.  This only occurs when there is a data point available at the beginning of the graph, followed by a period with no data, then data occurs again.  When hovering the mouse over this area, it will show that the value is 0, and any other tiles will reflect the zero data at this point accordingly.

## Related Dashboards

None

[status codes]: {{< url "Wikipedia.HttpStatusCodes" >}}
[customise threholds]: {{< url "Cortex.Reference.Dashboards.Grafana.ConfigureThresholds.MainDoc" >}}
