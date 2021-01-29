---
layout: post
title: Labels
description: emberjs 
platform: emberjs
control: PivotGauge
documentation: ug
---

# Labels

## Adding label collection

The label collection can be directly added to the scales option within the pivot gauge control.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            scales: [{
            //...
            labels: [{
                angle: 20
            }]
        }]
        }
    },
});
    
{% endhighlight %}

## Appearance customization

The appearance of the label can be customized through the following properties:

* **Angle**: Displays labels in a rotated manner. By default, the value is 0.
* **Color**: Displays the label in specified color.
* **Opacity**: Sets the opacity of the label. By default, the value is 1.
* **Type**: Indicates the label for major intervals or minor intervals. By default, it takes major intervals.
* **IncludeFirstValue**: Includes the initial value based on user requirement.  By default, the value is true.
* **Font**: Sets the font size, font style, and font family of the label.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                    scales: [{
                        //...
                        labels: [{
                            //customizing major labels
                            type: "major",
                            color: "#1AFF01",
                            opacity: 0.8,
                            includeFirstValue: false,
                            font: {
                                size: "15px",
                                fontFamily: "Arial",
                                fontStyle: "bold"
                            }
                        }, 
                        {
                            //customizing minor labels
                            type: "minor",
                            color: "#FF103F",
                            opacity: 0.8,
                            includeFirstValue: true,
                            font: {
                                size: "10px",
                                fontFamily: "Arial",
                                fontStyle: "normal"
                            }
                        }]
                    }]
        }
    },
});
    
{% endhighlight %}

![](Labels_images/AppearanceCustomization.png) 


## Unit text

The `UnitText` property is used to add some text along with labels. Normally, the unit/measurement of the numeric value is indicated through the unit text. Using the `UnitTextPosition` property, the text can be positioned in front or back.

N> By default, the text appears at the back.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                   scales: [{
                        //...
                        labels: [{
                            //for Major labels
                            type: "major",
                            unitText: "$",
                            unitTextPosition: "front"
                        }, 
                        {
                            //for Minor labels
                            type: "minor",
                            unitText: "$",
                            unitTextPosition: "front"
                        }]
                    }]
        }
    },
});
    
{% endhighlight %}

![](Labels_images/UnitText.png) 


