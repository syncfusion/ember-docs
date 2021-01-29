---
layout: post
title: Getting Started for Essential JavaScript SunburstChart
description: How to create a SunburstChart.
platform: EmberJS
control: SunburstChart
documentation: ug
keywords: ejsunburstchart, sunburstchart, sunburstchart widget, EmberJS sunburstchart, Ember sunburstchart, sunburst
---

# Getting Started

Before we start with the Chart, please refer [this page](https://help.syncfusion.com/emberjs/overview)  for general information regarding integrating Syncfusion widget’s.

## Adding script reference


To render the SunburstChart control, the following list of external dependencies are needed, 

<table>
   <tr>
      <th>
         <b>Files</b>
      </th>
      <th>
         <b>Description/Usage </b>
      </th>
   </tr>
   <tr>
      <td>
         ej.core.min.js
      </td>
      <td>
        It is referred always before using all the JS controls.
      </td>
   </tr>
   <tr>
      <td>
         ej.data.min.js
      </td>
      <td>
         Used to handle data operation and is used while binding data to the JS controls.
      </td>
   </tr>
   <tr>
      <td>
        ej.sunburstchart.min.js
      </td>
      <td>
        Sunburst Chart core script file which includes chart related scripts files.
      </td>
   </tr>
   </table>

N> Refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route sunburstchart/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/)to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the sunburstchart.

{% highlight html %}

	{{ej-sunburstchart id="SunburstChart"}}

{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the sunburstchart.

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
         }
      }
    });

{% endhighlight %}

## Populate Data source:

The datasource for the Sunburst Chart is populated as a JSON object. The **default_data** contains the JSON data for rendering the Sunburst Chart as shown in the sample.
Create a document with .js extension with the below data to render sunburstchart and refer the script in index.html page as shown in below code snippet.

{% highlight js %}

var default_data = [

{ Category: "Employees", Country: "USA", JobDescription: "Sales", JobGroup: "Executive", EmployeesCount: 50 },
{ Category: "Employees", Country: "USA", JobDescription: "Sales", JobGroup: "Analyst", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Marketing", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 55 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 175 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 70 },
{ Category: "Employees", Country: "USA", JobDescription: "Management", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Accounts", EmployeesCount: 60 },

{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 43 },
{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 125 },
{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 60 },
{ Category: "Employees", Country: "India", JobDescription: "HR Executives", EmployeesCount: 70 },
{ Category: "Employees", Country: "India", JobDescription: "Accounts", EmployeesCount: 45 },

{ Category: "Employees", Country: "Germany", JobDescription: "Sales", JobGroup: "Executive", EmployeesCount: 30 },
{ Category: "Employees", Country: "Germany", JobDescription: "Sales", JobGroup: "Analyst", EmployeesCount: 40 },
{ Category: "Employees", Country: "Germany", JobDescription: "Marketing", EmployeesCount: 50 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 40 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 65 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 27 },
{ Category: "Employees", Country: "Germany", JobDescription: "Management", EmployeesCount: 33 },
{ Category: "Employees", Country: "Germany", JobDescription: "Accounts", EmployeesCount: 55 },

{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 45 },
{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 96 },
{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 55 },
{ Category: "Employees", Country: "UK", JobDescription: "HR Executives", EmployeesCount: 60 },
{ Category: "Employees", Country: "UK", JobDescription: "Accounts", EmployeesCount: 30 },

{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 40 },
{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 65 },
{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 27 },
{ Category: "Employees", Country: "France", JobDescription: "Marketing", EmployeesCount: 50 }

 ];

{% endhighlight %}

As stated earlier, refer the above script in **index.html** page.

{% highlight html %}

<script src="{{rootURL}}scripts/scripts/Sunburst_Data.js" type="text/javascript"></script>

{% endhighlight %}

### Initialize Sunburst Chart with data

Now, bind the **default_data** to `datasource` property of the Sunburst Chart. The`levels`property determines the number of hierarchical levels. Each hierarchy level is formed based on the property specified in `groupMemberPath` property, and each arc segment size is calculated using `valueMemberPath`.

{% highlight html %}

	{{ej-sunburstchart id="SunburstChart" e-valueMemberPath=model.valueMemberPath e-dataSource=model.dataSource e-levels = model.levels}}

{% endhighlight %}

* Now create a document with .js extension under `app/routes/chart` folder with the below code snippet.

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           dataSource: window.default_data,
           valueMemberPath: "EmployeesCount",
           levels: [
                { groupMemberPath: "Country" },
                { groupMemberPath: "JobDescription" },
                { groupMemberPath: "JobGroup" },
                { groupMemberPath: "JobRole" }
           ],
         }
      }
    });

{% endhighlight %}


## Running the application

* To run the application, execute below command.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to sunburstchart sample. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files. 


## Add Title to the Sunburst Chart

The title of the Sunburst chart is used to provide quick information to the user about the data being plotted in the Sunburst Chart. You can add it by using the `text` option of the `title` 

{% highlight html %}

	{{ej-sunburstchart id="SunburstChart" e-title=model.title}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           title: {text: "Employees Count"},
         }
      }
    });

{% endhighlight %}

## Enable Legend

You can enable or disable the legend by using the `visible` option present inside the `legend`

{% highlight html %}

	{{ej-sunburstchart id="SunburstChart" e-legend=model.legend}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           legend: { visible:true, position: "left" },
         }
      }
    });

{% endhighlight %}

## Add Data Labels

The data labels are used to improve the readability of the Sunburst chart. This can be achieved by enabling the `visible` option in the `dataLabelSettings`

{% highlight html %}

	{{ej-sunburstchart id="SunburstChart" e-datalabelSettings=model.datalabelSettings e-size=model.size}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           dataLabelSettings: { visible:true},
           size: { height: "600" },
         }
      }
    });

{% endhighlight %}

## Running the application

* To run the application, execute below command.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to chart tab. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files. 

Now the Sunburst Chart is rendered along with the specified customizations

![](Getting-Started_images/Getting-Started_img1.png)

[Click](http://emberjq.syncfusion.com/#/sunburstchart/default) here to view the default sample of the  Sunburst Chart.
