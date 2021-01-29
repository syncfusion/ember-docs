---
layout: post
title: Getting Started with Syncfusion Essential EmberJS Barcode widget
description: How to create one dimensional, two dimensional barcode and customizing the appearance of it. 
platform: EmberJS
control: Barcode
documentation: ug
---

# Getting Started

This section explains you briefly on how to create one dimensional and two dimensional barcodes and customizing its appearance in your EmberJS application.

You can easily configure the barcode to any DOM element such as `div` or `span`. It takes [`text`](/api/js/ejbarcode#textspan-classtype-signature-type-stringstringspan) and [`symbologyType`](/api/js/ejbarcode#symbologytypespan-classtype-signature-type-enumenumspan) as input and renders the encoded text as barcode.

Copy the `ej.web.all.min` file into the `vendor` folder.

## Adding a QR Code

Create an HTML file using the following code example for `Ember JS Barcode` creation.

{% highlight html %}

<!DOCTYPE html>
<html>
   <head>
      <title>Getting Started Essential Ember JS</title>
      <!--scripts-->
      <script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/ej.widgets.all.min.js"></script>
      <!--Add custom scripts here -->
   </head>
   <body>
      <!-- Add Barcode element here. -->
   </body>
</html>
{% endhighlight %}

Add `div` container for barcode rendering.

{% highlight html %}
<div id="barcode">
	{{ej-barcode id="barcode" e-symbologyType="qrbarcode" e-text=model.Text e-xDimension=model.xDimension}}
</div>
{{outlet}}
{% endhighlight %}

Set the `symbologyType` and provide input URL to the `text` property to render the QR Code.

{% highlight javascript %}
import Ember from 'ember';
export default Ember.Route.extend({
   model(){
    return {
            Text:"SYNCFUSION",
			xDimension: 10,
        }
    }
});

{% endhighlight %}

![](/js/Barcode/Getting-Started_images/Getting-Started_img2.png)

## Adding a Code128 Barcode

Create an HTML file using the following code example for creating a Code128 barcode.

{% highlight html %}

<!DOCTYPE html>
<html>
   <head>
      <title>Getting Started Essential Ember JS</title>
      <!--scripts-->
      <script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/ej.widgets.all.min.js"></script>
      <!--Add custom scripts here -->
   </head>
   <body>
      <!-- Add Barcode element here. -->
   </body>
</html>
{% endhighlight %}

Add `div` container for barcode rendering.

{% highlight html %}
<div id="barcode">
	{{ej-barcode id="barcode" e-symbologyType="code128a" e-text=model.Text e-quietZone=model.quietZone }}
</div>
{{outlet}}
{% endhighlight %}

Set the `symbologyType` and provide input to the `text` property to render the Code128 barcode.

{% highlight javascript %}
import Ember from 'ember';
export default Ember.Route.extend({
   model(){
    return {
            Text:"SYNCFUSION",
			quietZone: {all: 20},
        }
    }
});

{% endhighlight %}


![](/js/Barcode/Getting-Started_images/Getting-Started_img3.png)

## Customizing the Barcode appearance
The height of the barcode can be changed using the [barHeight](/api/js/ejBarcode#barheightspan-classtype-signature-type-numbernumberspan) property. The equivalent property to change the block size for two dimensional barcode is [xDimension](/api/js/ejBarcode#xdimensionspan-classtype-signature-type-numbernumberspan). You can also customize the barcode color by changing the [darkBarColor](/api/js/ejBarcode#darkbarcolorspan-classtype-signature-type-objectobjectspan) and [lightBarColor](/api/js/ejbarcode#lightbarcolorspan-classtype-signature-type-objectobjectspan) properties.

N>    This color customization is possible only for one dimensional barcodes and it is not supported for two dimensional barcodes.