---
layout: post
title: Getting-Started
description: getting started
platform: EmberJS
control: CheckBox
documentation: ug
---

# Getting Started

This section explains briefly about how to create a CheckBox in your application with EmberJS.

Before we start with the CheckBox, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS Reference


To render the CheckBox control, the following list of dependencies are required.

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
ej.checkbox.min.js<br/><br/></td><td>
CheckBox plugin.<br/><br/></td></tr>
</table>

CheckBox uses one or more script files, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies.

To get the real appearance of the CheckBox, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route checkbox/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also adds the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the CheckBox.

 {% highlight html %}

      <div class="content-container-fluid">
         <div class="row">
             <div class="cols-sample-area">
                 <div class="frame">
                     <div align="center">
                         <table width="500px" align="center">
                             <tr>Hobbies</tr>
                             <br>
                             <tr>
                                <td>{{ ej-checkbox id="Check1" e-size=model.Small e-text="Music" e-checked=model.checked}}</td>
                                <td>{{ ej-checkbox id="Check2" e-size=model.Small e-text="Sports"}}</td>
                                <td>{{ ej-checkbox id="Check3" e-size=model.Small e-text="Bike Riding"}}</td>
                             </tr>
                             <br>
                             <tr>Favourite Search Engines</tr>
                             <br>
                             <tr>
                                <td>{{ ej-checkbox id="Check4" e-size=model.Medium e-text="Google" e-checked=model.checked}}</td>
                                <td>{{ ej-checkbox id="Check5" e-size=model.Medium e-text="Yahoo"}}</td>
                                <td>{{ ej-checkbox id="Check6" e-size=model.Medium e-text="Bing"}}</td>
                             </tr>
                             <br>
                             <tr>Favourite Social Networks</tr>
                             <br>
                             <tr>
                                <td>{{ ej-checkbox id="Check7" e-size=model.Medium  e-text="Facebook"  e-enableTriState=model.triState e-checkState=model.checkState}}</td>
                                <td>{{ ej-checkbox id="Check8" e-size=model.Medium  e-text="GPlus" e-enableTriState=model.triState e-checkState=model.checkState}}</td>
                                <td>{{ ej-checkbox id="Check9" e-size=model.Medium  e-text="Twitter" e-enableTriState=model.triState}}</td>
                             </tr>
                            <br>
                         </table>
                     </div>
                 </div>
             </div>
         </div>
      </div>
    
{% endhighlight %}

 * Use the below code in `default.js` in routes folder to bind the model to the CheckBox.

{% highlight javascript %}

    export default Ember.Route.extend({
      model(){
      return {

        Small:"small",
        Medium:"medium",
        roundedCorner: true,
        checked: true,
        triState: true,
        checkState: "indeterminate"
        }
        }
        });

{% endhighlight %}

## Running the Application 

To run the application, execute below command.

{% highlight javascript %}

ember server

{% endhighlight %}

Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to CheckBox sample. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files.

![](Getting-Started_images/Getting-Started_img1.png)