---
layout: post
title: Named Set
description: named set
platform: emberjs
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Named sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members that can be created by combining cube data, arithmetic operators, numbers, and functions.

You can bind the named sets in the pivot tree map by setting it's unique name in the `field-name` property in the row or column axis and `is-named-sets` Boolean property to true.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivottreemap id="PivotTreeMap" e-dataSource=model.dataSource e-renderSuccess=model.renderSuccess}}
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
            },
            renderSuccess: function(args){
                     var treemapTarget = $('#PivotTreeMapTreeMapContainer').data('ejTreeMap');
                     treemapTarget.model.tooltipTemplate = null;
                     treemapTarget.model.showTooltip = false;
                     treemapTarget.refresh();
                }
           }
        }
    });
{% endhighlight %}

{% endtabs %}

![](NamedSets_images/namedset.png)