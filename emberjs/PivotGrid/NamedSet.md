---
title: Named Set
description: named set
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Named sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members, which can be created by combining cube data, arithmetic operators, numbers, and functions.

You can bind the named sets in the pivot grid by setting it's unique name in the `fieldName` property in the row or column axis and `isNamedSets` Boolean property to true.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource}}
	{% endraw %}
	</div>
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
                        fieldName: "[Core Product Group]", 
                        isNamedSets: true 
                    }
                ],
                values: [
                    {
                        measures: [
                            {
                                fieldName: "[Measures].[Internet Sales Amount]"
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

{% endtabs %}

![](KPI_images/namedset.png)
