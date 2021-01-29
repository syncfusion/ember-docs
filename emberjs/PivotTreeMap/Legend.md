---
layout: post
title: Legend
description: legend
platform: emberjs
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Legend

## Legend visibility

The legend shows the value range differences and color occurrence in the respective leaf node while hovering it with the cursor.

N> By default, the legend is visible in the pivot tree map.

![](Legend_images/Legend_img1.png)

You can disable the legend by setting the **showLegend** property to **false**. The following code example shows how to disable the legend:

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivottreemap id="PivotTreeMap" e-renderSuccess=model.renderSuccess}}
	{% endraw %}
	</div>
    
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
            renderSuccess: function(args){
                     var treemapTarget = $('#PivotTreeMapTreeMapContainer').data('ejTreeMap');
                     treemapTarget.model.showLegend = false;
                     treemapTarget.refresh();
                }
           }
        }
    });
{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img2.png)