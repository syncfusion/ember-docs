---
layout: post
title:  getting started
description:  getting started
platform: emberjs
control: Signature
documentation: ug
---

# Getting Started

The Essential EmberJS Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature using mouse or touch.

This section explains briefly about how to create a **Signature** in EmberJS by the following step-by-step instructions. The following screenshot demonstrates the functionality of Signature widget.
Before going to getting started with Signature widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create Signature Please Refer under [Requires](https://help.syncfusion.com/api/js/ejsignature/)

![](Getting_Started_images\gettingstarted_img1.png)

## Create Signature Control

Create an HTML file and add the following template in the HTML file.

{% highlight html %}

            <div class="control">
                    <h3>Sign here</h3>
                {% raw %}
                  {{ej-signature id="signature" e-height=model.height }}
                 {% endraw %}
            </div>

{% endhighlight %}

Add the following code in corresponding script file.

{% highlight js %}

    export default Ember.Route.extend({
    model(){
        return {
                height: "400px"
            }
        }
    });

{% endhighlight %}

The following screenshot is the output for the above code.

![](Getting_Started_images\createsignaturecontrol_img1.png)

## Adjusting Signature Size

You can customize the width and height of the Signature by width and height properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature control with customized width and height.

Add the following HTML to render signature with customized width and height.

{% highlight html %}

      <div class="control">
                    <h3>Sign here</h3>
                {% raw %}
                  {{ej-signature id="signature" e-height=model.height e-width=model.width e-isResponsive=true e-strokeWidth=model.strokeWidth}}
                  {% endraw %}
        </div>

{% endhighlight %}

Add the following in correcponding script file to render signature with customized width and height.

{% highlight javascript %}

        export default Ember.Route.extend({
        model(){
        return {
            height: "400px",
            isResponsive: true,
            strokeWidth: 3,
            width:"350px"
         }
        }
        });


{% endhighlight %}


The following screenshot illustrates signature with customized width and height.


![](Getting_Started_images\adjustingsignaturesize_img1.png)







