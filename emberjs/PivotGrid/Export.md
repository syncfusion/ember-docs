---
title: Export
description: export
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Exporting

The pivot grid control can be exported to the following file formats:

* Microsoft Excel
* Microsoft Word
* PDF
* CSV

The pivot grid control can be exported by invoking the **"exportPivotGrid"** method with an appropriate export option as a parameter.

## JSON export

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource}}
    {{ej-button id="Export" e-text="Export" e-click=model.Export }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}

### Excel export

You can export the contents of pivot grid to an Excel document for future archival, references, and analysis purposes.

To achieve Excel export, the service URL and the file name are set as parameters.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

### Word export

You can export the contents of pivot grid to a Word document for future archival, references, and analysis purposes.

To achieve Word export, the service URL and the file name are set as parameters.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

### PDF export

You can export the contents of pivot grid to a PDF document for future archival, references, and analysis purposes.

To achieve PDF export, the service URL and the file name are set as parameters.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/PDFExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

### CSV export

You can export the contents of pivot grid to a CSV document for future archival, references, and analysis purposes.

To achieve CSV export, the service URL and the file name are set as parameters.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/CSVExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

### Customize the export document name

For customizing file name, set the file name as parameter to the **exportPivotGrid**  method along with service URL.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
                }
        }
    }
});

{% endhighlight %}

## Exporting customization

You can add the title and description to the exporting document by using the title and description property obtained in the "beforeExport" event.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-beforeExport=model.beforeExport}}
    {{ej-button id="Export" e-text="Export" e-click=model.Export }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
                    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
                }
                beforeExport: function(args) {
                    args.title = "PivotGrid";
                    args.description = "Displays both OLAP and Relational datasource in tabular format";
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}

The following screenshot shows the pivot grid control exported to an Excel document:

![](Export_images/ExportPivotExcel.png)

The following screenshot shows the pivot grid control exported to a Word document:

![](Export_images/ExportPivotWord.png)

The following screenshot shows the pivot grid control exported to a PDF document:

![](Export_images/ExportPivotPDF.png)

The following screenshot shows the pivot grid control exported to a CSV document:

![](Export_images/ExportPivotCSV.png)
