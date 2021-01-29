---
layout: post
title:  Column Resizing
description: column resizing
platform: emberjs
control: PivotGrid
documentation: ug
---

# Resizing column

Allows you to change the column width by holding and dragging the column border using the mouse pointer.

## Column width based on size

The `e-enableColumnResizing` property adjusts the width of each column based on the size of the widget.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-enableColumnResizing=model.enableColumnResizing }}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
            	enableColumnResizing: true
           }
        }
    });
{% endhighlight %} 

## Column width based on text

The `e-resizeColumnsToFit` property automatically adjusts the width of each column based on the maximum content length available in the respective column.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-resizeColumnsToFit=model.resizeColumnsToFit }}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
            	resizeColumnsToFit: true
           }
        }
    });
{% endhighlight %} )

![](Column-Resizing_images/columnresizing.png)