---
title: Getting Started for Ember JS PivotGauge
description: How to create a PivotGauge with data source.
platform: emberjs
control: PivotGauge
documentation: ug
keywords: ejpivotgauge, pivotgauge, js pivotgauge
---

# Getting started

Before you start with the pivot gauge, refer to [`this page`](https://help.syncfusion.com/emberjs/getting-started) for general information regarding integrating Syncfusion widgets.

This section explains how to populate the pivot gauge with data source. This section covers only the minimal features that are needed to get started with the pivot gauge.

## Adding script reference

To render the pivot gauge control, the following list of external dependencies are needed:

The pivot gauge uses one or more sub-controls, therefore refer to the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the pivot gauge, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also be referred.

Refer to this [`link`](https://help.syncfusion.com/emberjs/getting-started "link") to add the above dependencies in to your ember application.

## Relational

This section explains how to populate a simple pivot gauge with relational data source.

### Initialize pivot gauge

The pivot gauge component can be created with prefix of `ej-`. The code example for defining controls in EmberJS is as follows:

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge"}}
{% endraw%}	
{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
        }
    },
});
    
{% endhighlight %}

### Populate pivot gauge with relational data source

This section explains how to populate the pivot gauge control using a sample JSON data as shown below:

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgauge id="PivotGauge" e-dataSource=model.dataSource e-isResponsive=model.isResponsive e-enableTooltip=model.enableTooltip e-backgroundColor=model.backgroundColor e-labelFormatSettings=model.labelFormatSettings e-scales=model.scales }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';
export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: [
									{ Amount: 100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Alberta" },
									{ Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 3, State: "British Columbia" },
									{ Amount: 300, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Brunswick" },
									{ Amount: 150, Country: "Canada", Date: "FY 2008", Product: "Bike", Quantity: 3, State: "Manitoba" },
									{ Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Car", Quantity: 4, State: "Ontario" },
									{ Amount: 100, Country: "Canada", Date: "FY 2007", Product: "Van", Quantity: 1, State: "Quebec" },
									{ Amount: 200, Country: "France", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Charente-Maritime" },
									{ Amount: 250, Country: "France", Date: "FY 2006", Product: "Van", Quantity: 4, State: "Essonne" },
									{ Amount: 300, Country: "France", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Garonne (Haute)" },
									{ Amount: 150, Country: "France", Date: "FY 2008", Product: "Van", Quantity: 2, State: "Gers" },
									{ Amount: 200, Country: "Germany", Date: "FY 2006", Product: "Van", Quantity: 3, State: "Bayern" },
									{ Amount: 250, Country: "Germany", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Brandenburg" },
									{ Amount: 150, Country: "Germany", Date: "FY 2008", Product: "Car", Quantity: 4, State: "Hamburg" },
									{ Amount: 200, Country: "Germany", Date: "FY 2008", Product: "Bike", Quantity: 4, State: "Hessen" },
									{ Amount: 150, Country: "Germany", Date: "FY 2007", Product: "Van", Quantity: 3, State: "Nordrhein-Westfalen" },
									{ Amount: 100, Country: "Germany", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Saarland" },
									{ Amount: 150, Country: "United Kingdom", Date: "FY 2008", Product: "Bike", Quantity: 5, State: "England" },
									{ Amount: 250, Country: "United States", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Alabama" },
									{ Amount: 200, Country: "United States", Date: "FY 2005", Product: "Van", Quantity: 4, State: "California" },
									{ Amount: 100, Country: "United States", Date: "FY 2006", Product: "Bike", Quantity: 2, State: "Colorado" },
									{ Amount: 150, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "New Mexico" },
									{ Amount: 200, Country: "United States", Date: "FY 2005", Product: "Bike", Quantity: 4, State: "New York" },
									{ Amount: 250, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "North Carolina" },
									{ Amount: 300, Country: "United States", Date: "FY 2007", Product: "Van", Quantity: 4, State: "South Carolina" }
								],
                                rows: [
                                    {
                                        fieldName: "Country",
                                        fieldCaption: "Country"
                                    },
                                    {
                                        fieldName: "State",
                                        fieldCaption: "State"
                                    }
                                ],
                                columns: [

                                    {
                                        fieldName: "Product",
                                        fieldCaption: "Product"
                                    }
                                ],
                                values: [
                                    {
                                        fieldName: "Amount",
                                        fieldCaption: "Amount"
                                    },
                                    {
                                        fieldName: "Quantity",
                                        fieldCaption: "Quantity"
                                    }
                                ]
                            },
                            enableTooltip: true, isResponsive: true,
                            backgroundColor: "transparent",
                            labelFormatSettings: { decimalPlaces: 2 },
                            scales: [{
                                showRanges: true,
                                radius: 150, showScaleBar: true, size: 1,
                                border: {
                                    width: 0.5
                                },
                                showIndicators: true, showLabels: true,
                                pointers: [{
                                    showBackNeedle: true,
                                    backNeedleLength: 20,
                                    length: 120,
                                    width: 7
                                },
								{
									type: "marker",
									markerType: ej.datavisualization.CircularGauge.MarkerType.Diamond,
									distanceFromScale: 5,
									placement: "center",
									backgroundColor: "#29A4D9",
									length: 25,
									width: 15
								}],
                                ticks: [{
                                    type: "major",
                                    distanceFromScale: 2,
                                    height: 16,
                                    width: 1, color: "#8c8c8c"
                                },
                                {
                                    type: "minor",
                                    height: 6,
                                    width: 1,
                                    distanceFromScale: 2,
                                    color: "#8c8c8c"
                                }],
                                labels: [{
                                    color: "#8c8c8c"
                                }],
                                ranges: [{
                                    distanceFromScale: -5,
                                    backgroundColor: "#fc0606",
                                    border: { color: "#fc0606" }
                                }, {
                                    distanceFromScale: -5
                                }],
                                customLabels: [{
                                    position: { x: 180, y: 290 },
                                    font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }, {
                                    position: { x: 180, y: 320 },
                                    font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }, {
                                    position: { x: 180, y: 150 },
                                    font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }]
                            }]
        }
    }
});

{% endhighlight %}

The above code will generate a simple pivot gauge as follows:

![](getting-started_images/purejs.png)

## OLAP

This section explains how to populate a simple pivot gauge with OLAP data source.

### Initialize pivot gauge

The pivot gauge component can be created with prefix of `ej-`. The code example for defining controls in EmberJS is as follows:

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge"}}
{% endraw%}	
{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
        }
    },
});
    
{% endhighlight %}

### Populate pivot grid with OLAP data source

This section describes how to populate the pivot grid control using OLAP data source as shown below:

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgauge id="PivotGauge" e-dataSource=model.dataSource e-isResponsive=model.isResponsive e-enableTooltip=model.enableTooltip e-backgroundColor=model.backgroundColor e-labelFormatSettings=model.labelFormatSettings e-scales=model.scales }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
import Ember from 'ember';
export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: "http://bi.syncfusion.com/olap/msmdpump.dll",
                                catalog: "Adventure Works DW 2008 SE",
                                cube: "Adventure Works",
                                rows: [
                                    {
                                        fieldName: "[Date].[Fiscal]",
                                        filterItems: { filterType: "include", values: ["[Date].[Fiscal].[Fiscal Year].&amp;[2004]"] }
                                    },
                                ],
                                columns: [
                                    {
                                        fieldName: "[Customer].[Customer Geography]"
                                    }
                                ],
                                values: [
                                    {
                                        measures: [
                                            {
                                                fieldName: "[Measures].[Internet Sales Amount]"
                                            },
                                            {
                                                fieldName: "[Measures].[Internet Revenue Status]"
                                            },
                                              {
                                                  fieldName: "[Measures].[Internet Revenue Trend]"
                                              },
                                          {
                                              fieldName: "[Measures].[Internet Revenue Goal]"
                                          },
                                        ],
                                        axis: ej.PivotGauge.AxisName.Columns
                                    }
                                ]
                            },
                            labelFormatSettings: { decimalPlaces: 2 },
                            enableTooltip: true, isResponsive: true,
                            backgroundColor: "transparent",
                            scales: [{
                                showRanges: true,
                                radius: 150, showScaleBar: true, size: 1,
                                border: {
                                    width: 0.5
                                },
                                showIndicators: true, showLabels: true,
                                pointers: [{
                                    showBackNeedle: true,
                                    backNeedleLength: 20,
                                    length: 120,
                                    width: 7
                                },
                        {
                            type: "marker",
                            markerType: ej.datavisualization.CircularGauge.MarkerType.Diamond,
                            distanceFromScale: 5,
                            placement: "center",
                            backgroundColor: "#29A4D9",
                            length: 25,
                            width: 15
                        }],
                                ticks: [{
                                    type: "major",
                                    distanceFromScale: 2,
                                    height: 16,
                                    width: 1, color: "#8c8c8c"
                                },
                                {
                                    type: "minor",
                                    height: 6,
                                    width: 1,
                                    distanceFromScale: 2,
                                    color: "#8c8c8c"
                                }],
                                labels: [{
                                    color: "#8c8c8c"
                                }],
                                ranges: [{
                                    distanceFromScale: -5,
                                    backgroundColor: "#fc0606",
                                    border: { color: "#fc0606" }
                                }, {
                                    distanceFromScale: -5
                                }],
                                customLabels: [{
                                    position: { x: 180, y: 290 },
                                    font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }, {
                                    position: { x: 180, y: 320 },
                                    font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }, {
                                    position: { x: 180, y: 150 },
                                    font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
                                }]
                            }]
        }
    }
});
{% endhighlight %}

The above code will generate a simple pivot gauge as follows:

![](getting-started_images/Olap.png)