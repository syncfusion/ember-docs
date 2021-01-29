---
layout: post
title: getting-started
description: getting started
platform: emberjs
control: Radial Slider
documentation: ug
---

# Getting Started

In this section, you can learn how to create a simple **Radial Slider**. Before going to getting started with RadialSlider widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create RadialSlider Please Refer under [Requires](https://help.syncfusion.com/api/js/ejradialslider/)

![](getting-started_images\getting-started_img1.png)


## Create your first Radial Slider control in EmberJS

Create a **div** element that is a container for **Radial Slider**. Initialize the "RadialSlider" widgets by adding the following code example.

        {% highlight html %}
        
          <div class="e-container-radialslider">
            {% raw %}
                {{ej-radialslider id="defaultslider"}}
          {% endraw %}
            </div>
                
        {% endhighlight %}

Add the following code in corresponding script file,
 
 {% highlight js %}
    
            export default Ember.Route.extend({
          model(){
             return {   }
               }
            });

            
    {% endhighlight %}

To render image in radialSlider please use **e-innerCircleImageUrl** property,

Include following code in your hbs and js file,

  {% highlight html %}
        
          <div class="e-container-radialslider">
              {% raw %}
                {{ej-radialslider id="defaultslider" e-innerCircleImageUrl=model.imageurl}}
                {% endraw %}
            </div>
                
    {% endhighlight %}


Please add following code to render the image in center of Radial Slider.

{% highlight js %}
    
            export default Ember.Route.extend({
          model(){
             return { 
                  imageurl:"http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"
               }
               }
            });

            
{% endhighlight %}

   


The following screenshot shows the output for the above code example.


![](getting-started_images\getting-started_img2.png)

