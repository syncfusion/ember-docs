---
layout: post
title: Dimensions
description: dimensions
platform: emberjs
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Dimensions

## Set size in percentage

You can customize the pivot chart dimension by setting the width and height of the control in percentage.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-size=model.size }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                size: { 
                    height: "80%", 
                    width: "80%" 
                },
        }
    }
});

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    width:100%;
    height:450px;
}

{% endhighlight %}

{% endtabs %}

## Set size in pixels

You can customize the pivot chart dimension by setting the width and height of the control in pixels.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-size=model.size }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                size: { 
                    height: "540px", 
                    width: "950px" 
                },
        }
    }
});

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    width:950px;
    height:450px;
}

{% endhighlight %}

{% endtabs %}
 
![](Dimensions_images/Dimensions.png) 

## Responsive

The pivot chart control supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot chart by setting the `isResponsive` property to true.


{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-isResponsive=model.isResponsive e-size=model.size }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                size: { 
                    height: "540px", 
                    width: "950px" 
                },
                isResponsive: true
        }
    }
});

{% endhighlight %}

{% highlight CSS %}

ej-pivotchart {
    min-width:525px;
    min-height:460px;
    width: 100%;
    height:450px;
}

{% endhighlight %}

{% endtabs %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

