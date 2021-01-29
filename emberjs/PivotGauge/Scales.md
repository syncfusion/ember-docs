---
layout: post
title: Scales
description: scales
platform: emberjs
control: PivotGauge
documentation: ug
---

# Scale

## Adding scale

The scale can be added to the pivot gauge control.

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
                showScaleBar: true,
                radius: 150
                //...
            }]
        }
    },
});
    
{% endhighlight %}

![](Scales_images/AddingScale.png) 

## Scale customization

### Pointer cap
The pointer cap is a circular shape element that is located at the center of the pivot gauge. It can be customized with the `PointerCap` property in the scales option. Following are the properties used to customize its appearance:

* **Radius**: Sets the radius of the pointer cap.
* **BorderColor**: Sets the color of the pointer cap border.
* **BorderWidth**: Sets the width of the pointer cap border.
* **BackgroundColor**: Sets the background color of the pointer cap.

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
                showScaleBar: true,
                pointerCap: {
                    radius: 5,
                    borderWidth: 2,
                    borderColor: "green",
                    backgroundColor: "yellow"
                }
            }]
        }
    },
});
    
{% endhighlight %}

![](Scales_images/PointerCap.png) 

### Appearance
The appearance of the scale can be customized using the following properties:

* **Radius**: Sets the radius of the scale.
* **BackgroundColor**: Sets the background color of the scale.
* **Border**: Sets the border of the scale with color and width properties.
* **Size**: Sets the size of the scale.
* **Minimum**: Sets the least value of the scale.
* **Maximum**: Sets the highest value of the scale.
* **MajorIntervalValue**: Sets the interval between minor ticks in the scale.
* **MinorIntervalValue**: Sets the interval between major ticks in the scale.
* **Direction**: Sets the direction of the scale. By default, it takes clockwise direction.

The `ShowIndicators`, `ShowTicks`, `ShowRanges`, `ShowPointers`, and `ShowScaleBar` properties are used to enable/disable the indicators, ticks, ranges, pointers, and scale bar respectively. By default, `ShowTicks` and `ShowPointers` are set to true, and other properties are set to false.

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
                showScaleBar: true,
                radius: 120,
                backgroundColor: "yellow",
                border: {
                    color: "Blue",
                    width: 3
                },
                size: 10,
                minimum: 20,
                maximum: 120,
                majorIntervalValue: 20,
                minorIntervalValue: 5,
                direction: ej.datavisualization.CircularGauge.Directions.CounterClockwise
            }]
        }
    },
});
    
{% endhighlight %}

![](Scales_images/Appearance.png)