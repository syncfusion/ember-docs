---
title: Getting Started for MaskEdit
description: MaskEdit - Getting-Started
platform: EmberJS
control: MaskEdit
documentation: ug
keywords: ejMaskEdit, MaskEdit, MaskEdit widget, EmberJS MaskEdit
---
# Getting Started

Before we start with the MaskEdit, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route MaskEdit/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the MaskEdit.

{% highlight html %}
{% raw %}
            {{ej-maskedit id="mask" mask :  "999-99"}}
{% endraw %}
{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the MaskEdit.

{% highlight html %}
{% raw %}
	export default Ember.Route.extend({
      model(){
         return {
        }
    }
{% endraw %}
{% endhighlight %}


## Running the application

* To run the application, execute below command.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to MaskEdit sample (http://localhost:4200/MaskEdit/default). The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.png)



## CustomCharacter

The **MaskEdit** allows you to use the custom character option. The specified character is allowed to enter in the Mask Edit Textbox by using the **customCharacter** property.

## HidePromptOnLeave

The **MaskEdit** provides the option to hide the prompt when you focus out from the control. The mask prompt is visible when you focus again to the control. The default value of **hidePromptOnLeave** is false.

## InputMode

The **MaskEdit** supports two type of inputs such as text and password that have been assigned by using the enum values **ej.InputMode.Text** and **ej.InputMode.Password**. The default value for **inputMode** is text in **MaskEdit**.

## MaskFormat

The **MaskEdit** provides the option to define the **maskFormat** to the value. The default value for **maskFormat** property is empty string.

The following steps explain the implementation of **MaskEdit Properties**.

{% highlight html %}
{% raw %}
            {{ej-maskedit id="mask" e-maskFormat = model.mask e-customCharacter = model.customcharacter}}
{% endraw %}
{% endhighlight %}

{% highlight html %}
{% raw %}
	export default Ember.Route.extend({
      model(){
         return {
             mask :  "9C9-99",
             customcharacter : "-"
        }
    }
{% endraw %}
{% endhighlight %}
