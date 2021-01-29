---
title: Save and Load Report
description: save and load report
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Save and load report

Allows you to save the current report of pivot grid and render the control with saved report later.

## Save report to local storage

To save the current report of pivot grid to the local storage, you should call the `saveReport` method in the pivot grid.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-saveReport=model.saveToLocal}}
    {{ej-button id="Export" e-text="Export" e-click=model.onSave }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                onSave: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    url = "",
                    name = "report",
                    storage = "local",
                    pGridObj.saveReport(name, storage, url);
                },
                saveToLocal: function(args) {
                    localStorage.setItem("report", JSON.stringify(args.report));
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}

## Load report from local storage

To load the stored report of pivot grid from the local storage, you should call the `loadReport` method in the pivot grid.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-loadReport=model.loadFromLocal}}
    {{ej-button id="Export" e-text="Export" e-click=model.onLoad }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                onLoad: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    url = "",
                    name = "report",
                    storage = "local",
                    pGridObj.loadReport(name, storage, url);
                },
                loadFromLocal: function(args) {
                    args.targetControl.model.dataSource = JSON.parse(localStorage.getItem("report"));
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}
