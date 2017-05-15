## Open-source JavaScript Libraries

### Highcharts Overview

> Highcharts makes it easy for developers to set up interactive charts in their web pages. - [Highcharts website](http://www.highcharts.com/)

Highcharts allows you to make basic charts (Highcharts), stock charts (HighStock), and maps (Highmaps).

We will be focusing on basic charts.

#### Charts

##### Documentation and Reference

Source Code: https://github.com/highcharts/highcharts.

API Documentation: http://api.highcharts.com/highcharts.

Getting-started guide: http://www.highcharts.com/docs/getting-started/installation.

Examples: http://www.highcharts.com/demo.

##### Usage

Reference: http://www.highcharts.com/docs/getting-started/your-first-chart.

Basic initialization of a new chart looks like:

```` js
configurationOptions = {
  chart: {
    type: 'bar'
  },
  title: {
    text: 'Food Consumption'
  },
  xAxis: {
    categories: ['Apples', 'Bananas', 'Cookies']
  },
  yAxis: {
    title: {
      text: 'Type of food eaten'
    }
  },
  series: [
    {name: 'Cookie Monster', data: [0, 0, 11]},
    {name: 'Santa Claus', data: [2, 3, 8]}
  ]
} // some object containing values corresponding to options contained in the documentation
Highcharts.chart('my-chart-container', configurationOptions) // where `my-chart-container` corresponds to the `id` attribute of some empty `div` element
````
