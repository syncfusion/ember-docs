---
layout: post
title: Getting-Started
description: getting started
platform: EmberJS
control: DateRangePicker
documentation: ug
---

# Getting Started

This section explains briefly about how to create a DateRangePicker in your application with EmberJS.

Before we start with the DateRangePicker, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS Reference

To render the DateRangePicker control, the following list of dependencies are required.

<table>
<tr>
<th>
File </th><th>
Description / Usage </th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Includes only the widget basic functions and Framework features. Must be referred always before using all the JS controls<br/><br/></td></tr>
<tr>
<td>
ej.globalize.min.js<br/><br/></td><td>
To support the globalization.<br/><br/></td></tr>
<tr>
<td>
ej.datepicker.min.js<br/><br/></td><td>
DatePicker plugin.<br/><br/></td></tr>
<tr>
<td>
ej.timepicker.min.js<br/><br/></td><td>
TimePicker plugin.<br/><br/></td></tr>
<tr>
<td>
ej.daterangepicker.min.js<br/><br/></td><td>
DateRangePicker plugin.<br/><br/></td></tr>
<tr>
<td>
ej.scroller.min.js<br/><br/></td><td>
It is referred when scrolling is used in the DateRangePicker.<br/><br/></td></tr>
</table>

DateRangePicker uses one or more script files, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies.

To get the real appearance of the DateRangePicker, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

# Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route daterangepicker/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also adds the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the DateRangePicker.

 {% highlight html %}

       {{ ej-daterangepicker id="dateRangePick"}}

{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the DateRangePicker.

{% highlight javascript %}

    export default Ember.Route.extend({
      model(){
            return {
           }
        }
    });

{% endhighlight %}

## Running the Application 

To run the application, execute below command.

{% highlight javascript %}

ember server

{% endhighlight %}

Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to DateRangePicker sample. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files.

![](Getting-Started_images/Getting-Started_img1.png)

# Get/Set Value

DateRangePicker provides an option to configure all its properties and to get its value. DateRangePicker value can be assigned during initialization or at run time. Below code shows how to assign the values at initialization.

* Use below code in `default.hbs` in templates folder to render the DateRangePicker.

 {% highlight html %}

        {{ ej-daterangepicker id="dateRangePick" e-value= model.Value}}
        
{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the DateRangePicker.

{% highlight javascript %}

    export default Ember.Route.extend({
            model(){
      return {
        Value: "11/1/2013 - 12/3/2019"
              }
        }
        });

{% endhighlight %}

Execution of above code will render the following output.

![](Getting-Started_images/Getting-Started_img2.png)
