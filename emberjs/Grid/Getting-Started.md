---
title: Getting Started for Grid
description: How to create the Grid, data bind, enable paging, grouping, filtering and add summaries
platform: EmberJS
control: Grid
documentation: ug
---
# Getting started

Before we start with the Grid, please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/) for general information regarding integrating Syncfusion widget’s.

## Enable Paging

[Paging] can be enabled by setting the [`e-allowPaging`](https://help.syncfusion.com/api/js/ejgrid#members:allowpaging) to true.  This adds the pager in the bottom of the grid and page size can be customized by using the [`e-pageSettings-pageSize`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagesize) property

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-pageSettings=model.page }}

{% endhighlight %}

{% highlight js %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           data: window.gridData,
           page: { pageSize: 8 },
           cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

N> Pager settings can be customized by using the [`e-pageSettings-pageSize`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagesize) property. When it is not given the default values for `pageSize` and `pageCount` are 12 and 8 respectively.


![](Getting-Started_images/Getting-Started_img3.png)
{:.image }


## Enable Filtering

[`Filtering`] can be enabled by setting the `e-allowFiltering` to `true`. By default, the filter bar row is displayed to perform filtering, you can change the filter type by using the [`e-filterSettings-filterType`](https://help.syncfusion.com/api/js/ejgrid#members:filtersettings) property.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowFiltering=true }}

{% endhighlight %}

{% highlight js %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
            data: window.gridData,
            cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

![](Getting-started_images/Getting-started_img4.png)
{:.image }


## Enable Grouping

[`Grouping`] can be enabled by setting the [`e-allowGrouping`](https://help.syncfusion.com/api/js/ejgrid#members:allowgrouping) to `true`.  Columns can be grouped dynamically by drag and drop the grid column header to the group drop area. The initial grouping can be done by adding required column names in the [`e-groupSettings-groupedColumns`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-groupedcolumns) property.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowGrouping=true}}

{% endhighlight %}

{% highlight js %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
             data: window.gridData,
             cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

![](Getting-started_images/Getting-started_img5.png)
{:.image }


Refer to the following code example for initial grouping.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowGrouping=true e-groupSettings=model.group}}

{% endhighlight %}

{% highlight js %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
            data: window.gridData,
            group: { groupedColumns: ["ShipCountry", "CustomerID"] },
            cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}
![](Getting-started_images/Getting-started_img6.png)
{:.image }


## Add Summaries

[`Summaries`] can be added by setting the [`e-showSummary`](https://help.syncfusion.com/api/js/ejgrid#members:showsummary) to true and adding required summary rows and columns in the [`e-summaryRows`](https://help.syncfusion.com/api/js/ejgrid#members:summaryrows) property. For demonstration, Stock column's sum value is displayed as summary.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-showSummary=true e-summaryRows=model.summaryRows e-allowGrouping=true e-groupSettings=model.group e-pageSettings=model.page}}

{% endhighlight %}

{% highlight js %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           data: window.gridData,
           page : { pageSize: 8 },
           group: { groupedColumns: ["CustomerID"] },
           summaryRows: [
                {
                  	title: "Sum",
                  	summaryColumns: [
                    { summaryType: ej.Grid.SummaryType.Sum, displayColumn: "Freight", dataMember: "Freight" }
              	  ]
              }
           ],
           cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}
![](Getting-started_images/Getting-started_img7.png)
{:.image }
