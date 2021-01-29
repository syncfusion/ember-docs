---
layout: post
title: Getting Started with AutoComplete widget for Essential EmberJS
description: How to create Autocomplete widget with the step-by-step instructions.
platform: emberjs
control: AutoComplete
documentation: ug
api: /api/js/ejautocomplete
---

# Getting Started

This section helps to understand the getting started of the AutoComplete widget with the step-by-step instructions. Before going to getting started with Autocomplete widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create Autocomplete Please Refer under [Requires] (https://help.syncfusion.com/api/js/ejautocomplete)

## Create an AutoComplete

* Use below code in `default.hbs` in templates folder to render the Autocomplete widget.

{% highlight html %}
	
    <div class="e-control">
	{% raw %}
        {{ej-autocomplete id="autocomplete"}}
    {% endraw %}
	</div>

{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the Autocomplete and initialize widget.

{% highlight js %}

    export default Ember.Route.extend({
         model(){
          return { }
               }
          });

{% endhighlight %}


## Data binding

The data for the suggestion list can be populated using the e-dataSource property. 

{%seealso%}[Data Binding](https://help.syncfusion.com/emberjs/autocomplete/data-binding){%endseealso%}


{% highlight js %}
   
    export default Ember.Route.extend({
         model(){
          return {
            dataSource: [
                   "Anemone Galilee", "Allium drumstick", "Artichoke thistle",
                   "Boronia ", "Bouvardia", "Blue lace flower", "Bird of paradise",
                   "Cone flower", "Cosmos", "Calla lily white", "Common Yarrow",
                   "Dahlia", "Daffodil", "Eucalyptus seeded", "Freesia", "Foxtail fern", "Feverfew",
                   "Godetia", "Gardenia", "Gayfeather", "Heather", "Hydrangea","Ivy",
                   "Japhette orchid", "Kangaroo paw yellow","Lace fern", "Lumex", "Lavender" ]
            }
           }
        });

{% endhighlight %}

![Autocomplete-GettingStarted](getting-started_images\getting-started_img1.png)



## Enable Popup Button

This button helps you to show all the available suggestions by click on it instead of the search text.

{% highlight html %}

	<div class="e-control">
    {% raw %}
    {{ej-autocomplete id="autocomplete" e-dataSource=model.dataSource e-showPopupButton=true}}
    {% endraw %}
	</div>
{% endhighlight %}

![Autocomplete-PopupButton](getting-started_images\getting-started_img2.png)

