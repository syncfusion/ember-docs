---
title: Getting Started for Ember JS PivotTreeMap
description: How to create a PivotTreeMap with data source.
platform: emberjs
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Getting started

Before you start with the pivot tree map, refer to [`this page`](https://help.syncfusion.com/emberjs/getting-started) for general information regarding integrating Syncfusion widgets.

This section explains how to populate the pivot tree map with data source. This section covers only the minimal features that are needed to get started with the pivot tree map.

## Adding script reference

To render the pivot tree map control, the following list of external dependencies are needed:

The pivot tree map uses one or more sub-controls, therefore refer to the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the pivot tree map, the dependent CSS file `ej.web.all.min.css` (which includes styles of all widgets) should also be referred.

Refer to this [`link`](https://help.syncfusion.com/emberjs/getting-started "link") to add the above dependencies in to your ember application.

### Initialize pivot tree map

The pivot tree map component can be created with prefix of `ej-`. The code example for defining controls in EmberJS is as follows:

{% highlight html %}

	{% raw%}
	{{ej-pivottreemap id="PivotTreeMap"}}
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

### Populate pivot tree map with OLAP data source

This section explains how to populate the pivot tree map control using OLAP data source as follows:

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivottreemap id="PivotTreeMap" e-dataSource=model.dataSource }}
	{% endraw %}
	</div>
    
    <script type="text/x-jsrender" id="tooltipTemplate">
        <div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
            <div>Measure(s) : \{{:~Measures(#data)}}</div><div>Row : \{{:~Row(#data)}}</div><div>Column : \{{:~Column(#data)}}</div><div>Value : \{{:~Value(#data)}}</div>
        </div>
    </script>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
                dataSource: {
                data: "http://bi.syncfusion.com/olap/msmdpump.dll", //data
                catalog: "Adventure Works DW 2008 SE",
                cube: "Adventure Works",
                rows: [
                    {
                        fieldName: "[Date].[Fiscal]"
                    }
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
                                fieldName: "[Measures].[Internet Sales Amount]",
                            }
                        ],
                        axis: "columns"
                    }
                ]
            }
           }
        }
    });
{% endhighlight %}

The above code will generate a simple pivot tree map with internet sales amount over a period of fiscal years across different customer geographic locations.

![](getting-started_images/Olap.png)