---
layout: post
title: Advanced Filtering and Sorting
description: advanced filtering and sorting
platform: emberjs
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Advanced filtering and sorting

It allows you to filter and sort the field members in the pivot client.

You can enable the Advanced Filtering and Sorting option in the pivot client by setting the `e-enableAdvancedFilter` property to true.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{ej-pivotclient id="PivotClient" e-enableAdvancedFilter=model.enableAdvancedFilter }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                enableAdvancedFilter: true
        }
    }
});

{% endhighlight %}

## Sorting

The sorting provides an option to sort the members of a field either in the ascending or descending order.

I> This feature is not applicable for the OLAP data source bound from the server-side.

![](AdvanceFiltering_images/sorting.png)

## Label filtering

Label filtering provides an option to filter the members of a field purely based on their caption. 

![](AdvanceFiltering_images/filtering.png)

![](AdvanceFiltering_images/filtering_dialog.png)


## Value filtering

Value filtering provides an option to filter members based on total values of the appropriate measure between members of the level. 

![](AdvanceFiltering_images/valuefilter.png)

![](AdvanceFiltering_images/valuefilter_dialog.png)
