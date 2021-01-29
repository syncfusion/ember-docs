---
layout: post
title: Paging
description: paging
platform: emberjs
control: PivotClient
documentation: ug
---

# Paging

I> This feature is applicable only for the OLAP data source.

Paging helps improve the rendering performance of the pivot client control by dividing a large amount of data into several sections and displaying one section at a time.

## Using pager 

You can enable the pager in the pivot client by setting the `e-enablePaging` property to true. You can provide the page size and current page details for each axis through the `pagerOptions` property.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enablePaging=model.enablePaging e-dataSource=model.dataSource }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: "//bi.syncfusion.com/olap/msmdpump.dll", //data
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
                                ],
                                pagerOptions: {
                                    categoricalPageSize: 3,
                                    seriesPageSize: 3,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                }
                            },
                            enablePaging: true
        }
    }
});

{% endhighlight %}

The following are the navigation options available in the pager:

* Move first: Navigates to the first page.
* Move last: Navigates to the last page. 
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Numeric box: Navigates to the desired page when an appropriate page number is entered in numeric value.

![](Paging_images/paging.png)


## Using virtual scrolling

Virtual scrolling is a technique that allows you to view the pivot client information in page by page with the use of the vertical and horizontal scrollbars. You can enable the virtual scrolling option in the pivot client by setting the `e-enableVirtualScrolling` property to true. You can provide the page size and current page details for each axis through the `pagerOptions` property.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enableVirtualScrolling=model.enableVirtualScrolling e-dataSource=model.dataSource }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: "//bi.syncfusion.com/olap/msmdpump.dll", //data
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
                                ],
                                pagerOptions: {
                                    categoricalPageSize: 3,
                                    seriesPageSize: 3,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                }
                            },
                            enableVirtualScrolling: true
        }
    }
});

{% endhighlight %}

![](Paging_images/virtual-scrolling.png)

## Page settings

The page setting for categorical and series axes is needed for setting in the data source property by using the following properties:

`categoricalPageSize`: Allows to set the number of categorical columns to be displayed in each page by applying the paging.

`seriesPageSize`: Allows to set the number of series rows to be displayed in each page by applying the paging.

`categoricalCurrentPage`: Allows to set the page number to be loaded in the categorical axis by default.

`seriesCurrentPage`: Allows to set the page number to be loaded in the series axis by default.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enablePaging=model.enablePaging e-dataSource=model.dataSource }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: "//bi.syncfusion.com/olap/msmdpump.dll", //data
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
                                ],
                                pagerOptions: {
                                    categoricalPageSize: 3,
                                    seriesPageSize: 3,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                }
                            },
                            enablePaging: true
        }
    }
});

{% endhighlight %}