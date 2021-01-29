---
layout: post
title: Getting-Started
description: getting started
platform: EmberJS
control: RadioButton
documentation: ug
---

# Getting Started

This section explains briefly about how to create a RadioButton in your application with EmberJS.

Before we start with the RadioButton, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS Reference

To render the RadioButton control, the following list of dependencies are required.

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
ej.radiobutton.min.js<br/><br/></td><td>
RadioButton plugin.<br/><br/></td></tr>
</table>

RadioButton uses one or more script files, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies.

To get the real appearance of the RadioButton, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route radiobutton/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also adds the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the RadioButton.

 {% highlight html %}

      <div class="content-container-fluid">
          <div class="row">
             <div class="cols-sample-area">
                 <div class="frame">
                     <div align="center">
                         <table width="500px" align="center">
                             <tr> Category </tr>
                             <br>
                             <br>
                             <tr>
                                 <td>
                                     {{ ej-radiobutton id="Radio1" e-size=model.Medium e-name="category" e-text="Fresher"}}
                                 </td>
                                 <td>
                                     {{ ej-radiobutton id="Radio2" e-size=model.Medium e-name="category" e-text="Experienced" e-checked=model.checked}}
                                 </td>
                             </tr>
                             <br>
                             <br>
                             <tr> Expreienced </tr>
                             <br>
                             <br>
                             <tr>
                                 <td>
                                     {{ ej-radiobutton id="Radio3" e-size=model.Medium e-name="exprience" e-text="1+years" e-checked=model.checked}}
                                 </td>
                                 <td>
                                     {{ ej-radiobutton id="Radio4" e-size=model.Medium e-name="exprience" e-text="2.5+years"}}
                                 </td>
                                 <td>
                                     {{ ej-radiobutton id="Radio5" e-size=model.Medium e-name="exprience" e-text="5+Years"}}
                                 </td>
                             </tr>
                         </table>
                     </div>
                 </div>
             </div>
         </div>
      </div>

{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the RadioButton.

{% highlight javascript %}

    export default Ember.Route.extend({
       model(){
          return {
        Medium:"medium",
        checked: true
        }
        }
        });

{% endhighlight %}

## Running the Application 

To run the application, execute below command.

{% highlight javascript %}

ember server

{% endhighlight %}

Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to RadioButton sample. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files.

![](Getting-Started_images/Getting-Started_img1.png)
