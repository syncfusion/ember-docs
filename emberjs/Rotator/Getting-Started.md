---
layout: post
title: Getting-Started
description: getting started
platform: emberjs
control: Rotator
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **Rotator** in EmberJS. **EmberJs Image Rotator** comes with a visual that has a spectacular zoom in and fade out effect. A single line of code invokes the **Rotator** effect. Using the following guidelines you can create **Rotator** widget for a real-time website banner. It has five images that slide automatically. When you click the center button, image slides in a rotating manner and on second click the rotation stops.

The following screenshot demonstrates the functionality of **Rotator** widget.

![](Getting-Started_images/Getting-Started_img1.png)

## Create Rotator Widget

A Rotator widget can be made by the following steps.

 Create an HTML file and add the following template in the HTML file.

{% highlight html %}

    <div class="frame">
        {% raw %}
                {{#ej-rotator id="sliderContent" e-slidewidth=model.slideWidth e-framespace=model.frameSpace
                    e-slideheight=model.slideHeight e-displayitemscount=model.displayItemsCount e-navigatesteps=model.navigateSteps
                    e-pagerposition=model.pagerPosition  e-orientation=model.orientation e-showpager=model.showPager e-enabled=model.enabled e-showcaption=model.showCaption
            e-allowkeyboardnavigation=model.allowKeyboardNavigation e-showCaption=true  e-showPlayButton=true e-isresponsive=model.isResponsive e-animationtype= model.animationType}}              
                    {{/ej-rotator}}   
            {% endraw %}    

            </div>

{% endhighlight %}

## Configure Images

The following guidelines help you to configure images.

* You can also load image from local storage.


{% highlight html %}

    <div class="frame">
        {% raw %}
               {{#ej-rotator id="sliderContent" e-slidewidth=model.slideWidth e-framespace=model.frameSpace
                   e-slideheight=model.slideHeight e-displayitemscount=model.displayItemsCount e-navigatesteps=model.navigateSteps
                   e-pagerposition=model.pagerPosition  e-orientation=model.orientation e-showpager=model.showPager e-enabled=model.enabled e-showcaption=model.showCaption
        e-allowkeyboardnavigation=model.allowKeyboardNavigation e-showCaption=true  e-showPlayButton=true e-isresponsive=model.isResponsive e-animationtype= model.animationType}}
               
                <li>
                    <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" alt="Nature" title="Nature" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" alt="bird" title="Beautiful Bird" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" alt="sculpture" title="Amazing Sculptures" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" alt="seaview" title="Sea-View" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" alt="snowfall" title="Snow Fall" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" alt="card" title="Credit Card" /></li>
                        <li>
                            <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" alt="night" title="Colorful Night" /></li>

                 
                
                {{/ej-rotator}}                      
     {% endraw %}   

            </div>



{% endhighlight %}

## Configure Styles

Add the following style in corresponding **.hbs** file or separate stylesheet.

{% highlight css %}

    <style type="text/css" class="cssStyles">

        .frame{
        width: 500px;
        height: 425px;
        padding-left: 5%;
        padding-top: 6%;
        border: 1px solid #BBBCBB;
        border-radius: 10px;
        color: #5C5C5C;
        margin: auto;
        display: block;
        }
        #sliderContent > li .image {
        width: 100%;
        height: 300px;
        }    

    </style>


{% endhighlight %}

## Set Actions

Add the following script in corresponding script file.

{% highlight javascript %}

        export default Ember.Route.extend({
        model(){
        return {
        slideWidth: "100%",
        frameSpace: "0px",
        slideHeight: "auto",
        displayItemsCount: "1",
        navigateSteps: "1",
        pagerPosition: ej.Rotator.PagerPosition.Outside,
        orientation: ej.Orientation.Horizontal,
        showPager: true,
        enabled: true,
        showCaption: true,
        allowKeyboardNavigation: true,
        showPlayButton: true,
        isResponsive:true,
        animationType: "slide"
                     }
                         }
              });

{% endhighlight %}


The above code gives the output displayed in following screenshot.

![](Getting-Started_images/Getting-Started_img2.png)

