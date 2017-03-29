# Interactive Charts Exercise

Make an interactive chart.

If you get stuck, or would like a step-by-step tutorial, see the accompanying [screencast](https://youtu.be/OxLxBGyEVuA).

## Objectives

  1. Gain exposure to making interactive charts and graphs.
  2. Practice data-driven document development.
  3. Practice updating page contents without refreshing the page.

## Prerequisites

  + [Changing Datasets](/exercises/data-driven-documents/changing-datasets.md)

## Instructions

Create a new `index.html` page and populate it with the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Highcharts Exercise</title>
    <script src="http://code.highcharts.com/highcharts.js"></script>
  </head>
  <body>
    <h1>Highcharts Exercise</h1>

    <!-- OPTIONALLY PUT A SELECT OR BUTTON ELEMENT HERE - FURTHER EXPLORATION ONLY -->

    <div id="my-chart-container">
    </div>

    <script type="text/javascript">

      // INITIALIZE YOUR CHART HERE

    </script>
  </body>
</html>
````

> NOTE: Do not at any time manually edit the HTML elements on this page (except as instructed in the "Further Exploration" section). Only edit the contents of the `script` at the bottom of the page.

Preview the page in a browser.

Browse the [types of charts available](http://www.highcharts.com/demo), and choose one that looks interesting to you. Then click on it to reveal an example. For example, you might choose a [basic pie chart](http://www.highcharts.com/demo/pie-basic).

Scroll down and click the "View Options" button to reveal the source code producing the example chart.

Copy and paste that code into your `script`, then refresh the page and see if you can get it to display on the page.

Once you see the chart, save your work, then start to make minor edits to the configuration options. Configure the graph's title, series colors, series labels, axis labels, number formatting, etc.

Optionally change the data series to display different data values.

Nice job!

> ## Further Exploration
>
> Abstract-away the data series from within the chart configuration options to a variable outside of the chart initialization function.
>
> Create another dataset that mimics the structure of this dataset, but differs in values. Store that in a different variable.
>
> Add a `button` or `select` element, and configure it such that when clicked or selected, it changes the contents of the chart by switching the underlying dataset.
