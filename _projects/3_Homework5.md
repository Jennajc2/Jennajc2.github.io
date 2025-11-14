---
name: Homework 5
tools: [Python, Altair, vega-lite]
image: assets/pngs/bigfoot.png
description: Click to see during which phase of the moon you are most likely to spot bigfoot!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

### Bigfoot Sightings By State, Season, and Phase of the Moon
<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_bigfoot.json" style="width: 100%"></vegachart>

### Heat Map Write-Up
This heat map visualizes the number of bigfoot sightings reported in each US state, excluding Hawaii, grouped by the season of the year. I encoded the four seasons on the x-axis, reordering them chronologically. I encoded states on the y-axis. The heat map is colored by the number of sightings in each state during each season from 1869-2018. Given that white was the default for no reported sightings, I decided to reverse the inferno color scheme to maintain consistency of lighter colors being associated with fewer sightings. I decided to exclude NaN data and data for which the season was "Unknown".

### Bar Plot Write-Up
This bar plot visualizes the number of bigfoot sightings reported during different phases of the moon. I encoded moon phases on the x-axis, with 0.00 representing a new moon and 1.00 representing a full moon. The moon phases are grouped in bins for practicality since it is difficult for the naked eye to discern small changes in moon phase. I encoded the number of reported sightings on the y-axis. I decided to color the bars with a color that wasn't already included in the heat map in order to avoid confusion over what colors represent. There were no relevant data transformations beyond excluding NaNs from the moon phase data.

### Interactivity
I decided to link the heat map to the bar plot by allowing the user to select a US state and season of interest by clicking any rectangle on the heat map. Based on the user's selection, the bar plot groups the number of sightings within that state and during that season according to the phases of the moon. In this way, the user can select the state and season they are in and consequently determine the phase of the moon during which they could have the highest probability of sighting bigfoot. (The user should note that even the highest probability is still quite small.) The selected box is outlined in the same green as the bar plot as a way to visually link the two charts. Unfortunately, not all rectangles have moon phase data.


<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Jennajc2/Jennajc2.github.io/blob/main/python_notebooks/Homework5.ipynb" text="The Analysis" %}
</div>