---
title: Advanced Filtering and Sorting
description: advance filtering and sorting
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Advanced filtering and sorting

It allows you to filter and sort the field members in the pivot grid. You can enable the Advanced Filtering and Sorting option in the pivot grid by setting the `e-enableAdvancedFilter` property to true.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-enableAdvancedFilter=model.enableAdvancedFilter }}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
            	enableAdvancedFilter: true
           }
        }
    });
{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field in the ascending or descending order.


![](AdvanceFiltering_images/sorting.png)

## Label filtering

Label filtering provides an option to filter the members of a field purely based on their caption.

![](AdvanceFiltering_images/filtering.png)

![](AdvanceFiltering_images/filtering_dialog.png)


## Value filtering

The value filtering provides an option to filter members based on total values of the appropriate measure between members of the level.

![](AdvanceFiltering_images/valuefilter.png)

![](AdvanceFiltering_images/valuefilter_dialog.png)
