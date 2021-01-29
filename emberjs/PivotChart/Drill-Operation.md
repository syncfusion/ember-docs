---
layout: post
title: Drill Operation
description: drill operation
platform: emberjs
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Drill operation

This is a basic feature of the pivot chart through which the amount of information can be limited for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the context menu present in the pivot chart.

Drill up, also called roll up, navigates from the inner most level (having detailed member information) to any of the outer levels.

Drill down, also called roll down, is the reverse of drill up. It navigates from any of the outer levels to the inner most level.

![](Drill-Operation_images/Drill-Operation_img1.png)


![](Drill-Operation_images/Drill-Operation_img2.png)


The DrillSuccess event will be triggered when you right-click the pivot chart and select any option available from the context menu to perform drill up or drill down operation.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-drillSuccess=model.drillSuccess }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                drillSuccess: function(args) {
				    alert("Drill Success");
			    }
        }
    }
});

{% endhighlight %}

{% endtabs %}

