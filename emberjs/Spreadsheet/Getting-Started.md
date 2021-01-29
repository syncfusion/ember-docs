---
title: Getting Started for Spreadsheet
description: How to create a Spreadsheet with data source, apply format and export it as excel file.
platform: EmberJS
control: Spreadsheet
documentation: ug
---
# Getting started

Before we start with the Spreadsheet, please refer [`this page`](https://help.syncfusion.com/emberjs/getting-started) for general information regarding integrating Syncfusion widget's.

This section explains you the steps required to populate the Spreadsheet with data, format, and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

## Adding Script Reference

To render the Spreadsheet control, the following list of external dependencies are needed, 

Spreadsheet uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the Spreadsheet, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

Refer this [`link`](https://help.syncfusion.com/emberjs/getting-started "link") to add the above dependencies in to your ember application.

## Initialize Spreadsheet

The Sreadsheet component can be created with prefix of `ej-`.The code example for defining controls in EmberJS is as follows,

{% highlight html %}

	{% raw%}
	{{ej-spreadsheet id="Spreadsheet"}}
{% endraw%}	
{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
        }
    },
});
    
{% endhighlight %}

Now, the Spreadsheet is rendered with default row and column count.

![](Getting-Started_images/Getting-Started_img1.png)


## Populate Spreadsheet with data

Now, this section explains how to populate JSON data to the Spreadsheet. You can set [`dataSource`](https://help.syncfusion.com/api/js/ejspreadsheet#members:sheets-datasource "dataSource") property in [`e-sheets`](https://help.syncfusion.com/api/js/ejspreadsheet#members:sheets "sheet") settings to populate JSON data in Spreadsheet.

{% highlight html %}

	{% raw%}
	{{ej-spreadsheet id="Spreadsheet" e-sheets=model.sheets}}
{% endraw%}	
{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
         sheets: [{
                rangeSettings: [{ dataSource: [
                    { "Item Name": "Casual Shoes", Date: "02/14/2014", Time: "11:34:32 AM", Quantity: 10, Price: 20, Amount: 200, Discount: 1, Profit: 10 },
                    { "Item Name": "Sports Shoes", Date: "06/11/2014", Time: "05:56:32 AM", Quantity: 20, Price: 30, Amount: 600, Discount: 5, Profit: 50 },
                    { "Item Name": "Formal Shoes", Date: "07/27/2014", Time: "03:32:44 AM", Quantity: 20, Price: 15, Amount: 300, Discount: 7, Profit: 27 },
                    { "Item Name": "Sandals & Floaters", Date: "11/21/2014", Time: "06:23:54 AM", Quantity: 15, Price: 20, Amount: 300, Discount: 11, Profit: 67 },
                    { "Item Name": "Flip- Flops & Slippers", Date: "06/23/2014", Time: "12:43:59 AM", Quantity: 30, Price: 10, Amount: 300, Discount: 10, Profit: 70 },
                    { "Item Name": "Sneakers", Date: "07/22/2014", Time: "10:55:53 AM", Quantity: 40, Price: 20, Amount: 800, Discount: 13, Profit: 66 },
                    { "Item Name": "Running Shoes", Date: "02/04/2014", Time: "03:44:34 AM", Quantity: 20, Price: 10, Amount: 200, Discount: 3, Profit: 14 },
                    { "Item Name": "Loafers", Date: "11/30/2014", Time: "03:12:52 AM", Quantity: 31, Price: 10, Amount: 310, Discount: 6, Profit: 29 },
                    { "Item Name": "Cricket Shoes", Date: "07/09/2014", Time: "11:32:14 AM", Quantity: 41, Price: 30, Amount: 1210, Discount: 12, Profit: 166 },
                    { "Item Name": "T-Shirts", Date: "10/31/2014", Time: "12:01:44 AM", Quantity: 50, Price: 10, Amount: 500, Discount: 9, Profit: 55 },
                ], startCell: "A1" }]
            }]
        }
    },
});
    
{% endhighlight %}


![](Getting-Started_images/Getting-Started_img2.png)

N> For more details about `data binding` refer following [`link`](https://help.syncfusion.com/js/spreadsheet/data-binding "link")

## Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain color based on the cells values. You can use [`e-allowConditionalFormats`](https://help.syncfusion.com/api/js/ejspreadsheet#members:allowconditionalformats "allowConditionalFormats") property to enable/disable Conditional formats.

To apply conditional formats for a range use [`setCFRule`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcformat-setcfrule "setCFRule") method. The following code example illustrates this,

{% highlight html %}

	{% raw%}
	{{ej-spreadsheet id="Spreadsheet" e-allowConditionalFormats=true e-loadComplete=model.loadComplete}}
{% endraw%}	

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
         loadComplete: function() {
                if (!this.isImport) {
                    this.XLCFormat.setCFRule({ "action": "greaterthan", "inputs": ["10"], "color": "redft", "range": "D2:D8" });
                }
            }
        }
    },
});
    
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)

N> For more details about `Conditional Formatting` refer following [`link`](https://help.syncfusion.com/js/spreadsheet/data-presentation#conditional-formatting "link")

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set [`allowExporting`](https://help.syncfusion.com/api/js/ejspreadsheet#members:exportsettings-allowexporting "allowExporting") option in [`e-exportSettings`](https://help.syncfusion.com/api/js/ejspreadsheet#members:exportsettings "exportSettings") as `true`. Since Spreadsheet uses server side helper to save documents set [`excelUrl`](https://help.syncfusion.com/api/js/ejspreadsheet#members:exportsettings-excelurl "excelUrl") in [`exportSettings`](https://help.syncfusion.com/api/js/ejspreadsheet#members:exportsettings "exportSettings") option. The following code example illustrates this,

{% highlight html %}

	{% raw%}
	{{ej-spreadsheet id="Spreadsheet" e-exportSettings=model.exportSettings}}
{% endraw%}	

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
         exportSettings: {
                allowExporting:true,
                excelUrl: "http://js.syncfusion.com/ejservices/api/Spreadsheet/ExcelExport",
                csvUrl: "http://js.syncfusion.com/ejservices/api/Spreadsheet/CsvExport",
                pdfUrl: "http://js.syncfusion.com/ejservices/api/Spreadsheet/PdfExport"
            },
        }
    },
});
    
{% endhighlight %}

Use shortcut [`Ctrl + S`](https://help.syncfusion.com/js/spreadsheet/keyboard-shortcuts "Ctrl + S") to save Spreadsheet as excel file.

N> 1. For more details about `Export` refer following [`link`](https://help.syncfusion.com/js/spreadsheet/open-and-save#save "link")
N> 2. For more details about `Server Configuration` refer following [`link`](https://help.syncfusion.com/js/spreadsheet/open-and-save#server-configuration "link")


