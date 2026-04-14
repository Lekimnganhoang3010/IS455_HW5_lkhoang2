---
layout: default
title: Chicago Business License Analysis
---

# Homework 5: Chicago Business Licenses
[Link to Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv) | [Link to My Analysis Notebook](./HW5_The_Analysis.ipynb)

## Visualization 1: License Status Frequency
- Description: This chart visualizes the distribution of business licenses across different status categories (e.g., Active, Expired, Revoked) to show the current standing of businesses in the dataset.

- Design & Encodings: I used a horizontal bar chart with Nominal (N) encoding for the "License Status" on the Y-axis and Quantitative (Q) encoding for the "count()" on the X-axis. I applied the tableau10 color scheme to the "License Status" variable to provide high contrast between categories. The horizontal layout ensures that long category labels remain readable without overlapping.

- Data Transformations: On the analysis side, I used fillna("Unknown") to handle missing values in the status column and used Altair’s internal count() transformation to aggregate the raw records into totals.

- Interactivity: (Not applicable for this static plot).

<div id="viz1"></div>

## Visualization 2: Yearly Trends by State
- Description: This plot visualizes the historical timeline of when business licenses were originally issued, allowing for a comparison of business growth trends over time.

- Design & Encodings: I used a Temporal (T) encoding for the "Original Issue Date" (binned by year) on the X-axis and a Quantitative (Q) encoding for the count of licenses on the Y-axis. The chart uses both mark_line and mark_point to show the overall trend while highlighting specific annual data points.

- Data Transformations: I converted the "Original Issue Date" column to a datetime format in Python and used the year() transformation within Altair to aggregate the data from daily entries into annual trends.

- Interactivity: I implemented a Dropdown Filter bound to the "State" field. This allows the user to isolate the trends for a specific state (defaulting to Illinois). This interactivity makes the visualization clearer by preventing "spaghetti chart" clutter and allowing users to focus on a single geographic area's historical business pulse

<div id="viz2"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script type="text/javascript">
  var spec1 = "plot1.json";
  vegaEmbed('#viz1', spec1).then(function(result) {
  }).catch(console.error);

  var spec2 = "plot2.json";
  vegaEmbed('#viz2', spec2).then(function(result) {
  }).catch(console.error);
</script>
