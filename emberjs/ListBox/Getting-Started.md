---
layout: post
title: Getting-Started
description: getting started
platform: emberjs
control: ListBox
documentation: ug
---

# Getting Started

This section helps to understand the getting started of the ListBox widget with the step-by-step instructions.Before going to getting started with ListBox widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create ListBox Please Refer under [Requires](https://help.syncfusion.com/api/js/ejlistbox/)


## Create ListBox

Initialize the ListBox widget as below.

{% highlight html %}

        <div class="e-container-listbox">
			 <div class="ctrllabel">Select a Car</div>
             {% raw %}
               {{#ej-listbox id="defaultlistbox" }}
                        <li>Audi A4</li>
                        <li>Audi A5</li>
                        <li>Audi A6</li>
                        <li>Audi A7</li>
                        <li>Audi A8</li>
                        <li>BMW 501</li>
                        <li>BMW 502</li>
                        <li>BMW 503</li>
                        <li>Batch</li>
                        <li>BMW 507</li>
                        <li>BMW 3200</li>
                        <li>Cut</li>
               {{/ej-listbox}}
               {% endraw %}

            </div>
            
{% endhighlight %}

Add the below code in corresponding script file.

{% highlight javascript %}

        export default Ember.Route.extend({
        model(){
        return {     }
            }
        });

{% endhighlight %}



![Alt text](Getting-Started_images\Getting-Started_img1.png)

## Data binding

We can populate data in the ListBox widget using “e-datasource” and “e-fields” properties. 


{% highlight html %}

        <div class="e-container-listbox">
			   <div class="ctrllabel">Select a bike</div>
      {% raw %}
      {{ej-listbox id="defaultlistbox" e-dataSource=model.BikeList e-fields=model.fields}}
      {% endraw %}

            </div>
            
{% endhighlight %}

Add the below code in corresponding script file.

{% highlight javascript %}

    export default Ember.Route.extend({
        model(){
     return { 
        BikeList:[
            { bikeId: "bk1", bikeName: "Apache RTR" }, 
            { bikeId: "bk2", bikeName: "CBR 150-R" }, 
            { bikeId: "bk3", bikeName: "CBZ Xtreme" },
            { bikeId: "bk4", bikeName: "Discover" }, 
            { bikeId: "bk5", bikeName: "Dazzler" }, 
            { bikeId: "bk6", bikeName: "Flame" },
            { bikeId: "bk7", bikeName: "Fazer" }, 
            { bikeId: "bk8", bikeName: "FZ-S" }, 
            { bikeId: "bk9", bikeName: "Pulsar" },
            { bikeId: "bk10", bikeName: "Shine" }, 
            { bikeId: "bk11", bikeName: "R15" }, 
            { bikeId: "bk12", bikeName: "Unicorn" }
        ],
        fields: { 
            id: "bikeId", 
            text: "bikeName" 
        }   }
          }
      });

{% endhighlight %}
 
![Databinding Listbox](Getting-Started_images\Getting-Started_img2.png)

## Selection

The ListBox widget supports item selection. To achieve this please use "e-selectedIndex" property. 


{% highlight html %}

        <div class="e-container-listbox">
			   <div class="ctrllabel">Select a bike</div>
            {% raw %}
               {{ej-listbox id="defaultlistbox" e-dataSource=model.BikeList e-fields=model.fields e-selectedIndex=2}}
            {% endraw %}
            </div>
            
{% endhighlight %}


![Selection Listbox](Getting-Started_images\Getting-Started_img3.png)

