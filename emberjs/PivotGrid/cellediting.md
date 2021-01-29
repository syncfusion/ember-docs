---
title: Cell-Editing
description: cell editing
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Cell editing

I> This feature is applicable only for the relational data source.

Cell editing allows you to edit and alter the values in pivot grid. The summary values will be recreated based on edited values. By selecting multiple cells (like in cell selection feature), you can edit multiple cells at the same time.
  
You can enable the cell editing option in the pivot grid by setting the `e-enableCellEditing` property to true.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-enableCellEditing=model.enableCellEditing }}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
            	enableCellEditing: true
           }
        }
    });
{% endhighlight %}

![](Cell-Editing_images/celleditingclient.png)


