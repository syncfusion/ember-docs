---
layout: post
title: Pointers
description: pointers
platform: emberjs
control: PivotGauge
documentation: ug
---

# Pointers

## Pointer types

The pivot gauge has two types of pointers namely,

* Needle
* Marker

Needle type pointer is the default pointer that is always located at the center of the gauge. Following are the supported shapes for needle pointers:

* Rectangle
* Triangle
* Trapezoid
* Arrow
* Image.

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
                pointers: [{
                    type: "needle",
                    needleType: "trapezoid",
                }]
            }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/NeedlePointer.png) 

For marker pointer, the available shapes are rectangle, triangle, ellipse, diamond, pentagon, circle, slider, pointer, wedge, trapezoid, roundedrectangle, and image.

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
                pointers: [{
                    type: "marker",
                    markerType: "diamond",
                }]
            }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/MarkerPointer.png) 

## Adding pointer collection

The pointer collection can be directly added to the scales option within the pivot gauge control.

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
            pointers: [
                {
                    type: "needle",
                    needleType: "triangle",
                }, 
                {
                    type: "marker",
                    markerType: "diamond"
                }     
            ]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerCollection.png) 

## Appearance customization

The appearance of the pointer can be customized through the following properties:

* **Border**: Sets the color and width of the pointer border.
* **BackgroundColor**: Sets the background color of the pointer.
* **Length**: Sets the length of the pointer.
* **Width**: Sets the width of the pointer.
* **Opacity**: Sets the opacity of the pointer. By default, the value is 1.
* **Type**: Sets the type of the pointer. By default, the type is needle.

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
            pointers: [
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 120,
                    width: 7,
                    opacity: 0.6,
                    type: "needle",
                    needleType: "triangle"
                }, 
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 25,
                    width: 15,
                    opacity: 0.8,
                    type: "marker",
                    markerType: "diamond"
                }
            ]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/AppearanceCustomization.png) 

## Pointer position

The pointer can be positioned with the help of the following two properties:

* **DistanceFromScale**: Defines the distance between the scale and the pointer. By default, the value is 0.
* **Placement**: Defines the location of the pointer. By default, the value is center.

N> Both the properties can be applied only if the pointer type is set to marker. The needle pointer type appears only at the center of the control, which is its default position.

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
            pointers: [{
                //...
                type: "marker",
                placement: "far",
                distanceFromScale: 2
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerPosition.png) 

## Pointer image

You can replace the pointers with an image. To view the pointers as an image, you should set the appropriate location in the `ImageUrl` property.

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
            pointers: [{
                //For replacing needle pointer with image
                type: "needle",
                needleType: "image",
                imageUrl: "image.png"
            }, 
            {
                //For replacing marker pointer with image
                type: "marker",
                markerType: "image",
                imageUrl: "image.png"
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/MarkerPointerWithImage.png)

## Pointer value text

To display the current value of pointers in the pivot gauge control, the **"PointerValueText"** option is used. Following are the properties used to enable and customize the pointer value text:
 
* **ShowValue**: Enables the pointer value text by setting the property to true. By default, its value is true.
* **Distance**: Sets the distance between the pointer and the text.
* **Color**: Sets the color of the text.
* **Opacity**: Sets the opacity of the text. By default, its value is 1.
* **Angle**: Sets the rotation angle of the text. By default, its value is 0.
* **Font**: Sets the font size, font style, and font family of the text.

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
            pointers: [{
                //For needle type
                pointerValueText: {
                    showValue: true,
                    distance: 10,
                    color: "red",
                    opacity: 0.7,
                    angle: 20,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                }
            }, 
            {
                //For marker type
                pointerValueText: {
                    showValue: true,
                    distance: 40,
                    color: "red",
                    opacity: 0.7,
                    angle: -40,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                },
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerValueText.png) 
