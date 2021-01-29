---
title: Getting Started for NumericTextbox
description: NumericTextbox - Getting-Started
platform: EmberJS
control: NumericTextbox
documentation: ug
keywords: ejNumericTextbox, NumericTextbox, NumericTextbox widget, EmberJS NumericTextbox
---
# Getting Started

Before we start with the Textboxes, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route numeric/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the Textboxes.

{% highlight html %}
{% raw %}
       {{ej-numerictextbox id="numeric" e-value=model.numeric}}
{% endraw %}
{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the Textboxes.

{% highlight html %}
{% raw %}
	export default Ember.Route.extend({
      model(){
         return {
           numeric : 35
        }
    }
{% endraw %}
{% endhighlight %}


## Running the application

* To run the application, execute below command.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to numeric sample (http://localhost:4200/numeric/default). The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.png)


## Decimal Places

The **decimalPlaces** property specifies number of values allowed after the decimal point. The default value of **decimalPlaces** property is 0. i.e., By default you cannot specify decimal value in NumericTextbox. We need to add this property to allow decimal values.

{% highlight html %}
{% raw %}
{{ej-numerictextbox id="numeric" e-value=model.numeric e-decimalPlaces = model.decimals}}
{% endraw %}
{% endhighlight %}

## Strict Mode Support

NumericTextbox allows you to use the strict mode option by setting the **enableStrictMode** property. You can set the **minValue** and **maxValue** to the controls to enable strict mode functionality. Default value of this property is **false**. When the textbox value exceeds the **maxValue**, it restricts the exceeded value and returns the **maxValue**. Likewise when the textbox value goes below **minValue**, it restricts the new value and returns the **minValue**. When this property is true, it will not restrict the specified value and an error class will be added to indicate wrong value is provided to the NumericTextbox.

### Configure Strict Mode Support 

The following steps explain the implementation of **enableStrictMode** in **NumericTextbox** .

{% highlight html %}
{% raw %}
{{ej-numerictextbox id="numeric"  e-value=model.numeric e-enableStrictMode = true e-minValue = model.min e-maxValue = model.max e-decimalPlaces = model.decimals}}
{% endraw %}
{% endhighlight %}


{% highlight html %}
{% raw %}
export default Ember.Route.extend({
    model(){
    return {
        numeric : 35,
        min: 10,
        max : 30
        }
    }
});
{% endraw %}
{% endhighlight %}

## Increment Step

The **incrementStep** property is used to increase or decrease the amount of value in the NumericTextbox control. 

### Configure Increment Step

The following steps explain the implementation of **incrementStep** in NumericTextbox.


{% highlight html %}
{% raw %}
{{ej-numerictextbox id="numeric" e-incrementStep = model.step e-value=model.numeric e-enableStrictMode = true e-minValue = model.min e-maxValue = model.max e-decimalPlaces = model.decimals}}
{% endraw %}
{% endhighlight %}


{% highlight html %}
{% raw %}
export default Ember.Route.extend({
    model(){
    return {
        numeric : 35,
        min: 10,
        max : 30,
        step: 5
        }
    }
});
{% endraw %}
{% endhighlight %}
