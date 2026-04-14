---
layout: default
title: Chicago Business License Analysis
---

# Homework 5: Chicago Business Licenses
[Link to Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv) | [Link to My Analysis Notebook](./HW5_The_Analysis.ipynb)

## Visualization 1: License Status Frequency
This chart shows the distribution of business license statuses. I chose a horizontal bar chart to ensure labels remain readable and sorted them to show the most common statuses at a glance.

<div id="viz1"></div>

## Visualization 2: Yearly Trends by State
This interactive trend line allows you to filter the data by State using the dropdown menu.

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
