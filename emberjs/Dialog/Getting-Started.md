---
layout: post
title: Getting Started with Dialog widget for Essential EmberJS
description: How to create Dialog widget with the step-by-step instructions.
platform: emberjs
control: Dialog
documentation: ug
---

# Getting Started

This section helps to understand the getting started of the Dialog widget with the step-by-step instructions.
Before going to getting started with Dialog widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create Dialog Please Refer under [Requires](https://help.syncfusion.com/api/js/ejdialog/)


## Create Dialog

* Use below code in `default.hbs` in templates folder to render the Dialog widget.

{% highlight html %}

    <div class="e-control">
	 {% raw %}
      {{#ej-dialog id="defaultdialog" }} {{/ej-dialog}} 
     {% endraw %}
	</div>                  

{% endhighlight %}



* Use the below code in `default.js` in routes folder to bind the model to the Dialog and initialize widget.

{% highlight js %}

    export default Ember.Route.extend({
         model(){
          return { }
               }
          });

{% endhighlight %}



![Create Dialog](getting-started_images\getting-started_img1.png)

### Add dialog content

Add the contents for the dialog as below.

* Use below code in `default.hbs` in templates folder to render the Dialog widget.

{% highlight html %}

    <div class="e-control">
    {% raw %}
    {{#ej-dialog id="defaultdialog" }}
                <!--dialog content-->
            <p>This is a simple dialog</p>
                {{/ej-dialog}}
     {% endraw %}
	</div>                  

{% endhighlight %}



* Use the below code in `default.js` in routes folder to bind the model to the Dialog and initialize widget.

{% highlight js %}

    export default Ember.Route.extend({
         model(){
          return { }
               }
          });

{% endhighlight %}




![Add dialog content](getting-started_images\getting-started_img2.png)

### Set the title

The Dialog widget’s title can be set as follows.

* Use below code in `default.hbs` in templates folder to render the Dialog widget with title and content.

{% highlight html %}

    <div class="e-control">
    {% raw %}
     {{#ej-dialog id="defaultdialog" e-title="Dialog"}}
                <!--dialog content-->
            <p>This is a simple dialog</p>
                {{/ej-dialog}}
     {% endraw %}
	</div>                  

{% endhighlight %}



* Use the below code in `default.js` in routes folder

{% highlight js %}

    export default Ember.Route.extend({
         model(){
          return { }
               }
          });

{% endhighlight %}

![Set the title](getting-started_images\getting-started_img3.png)

### Open Dialog dynamically

In most cases, the Dialog widgets are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So the Dialog widget provides “open” and “close” methods to open/close the dialogs dynamically.

The Dialog widget can be hidden on initialize using `e-showOnInit` property which should be set to false. 

Refer the below example to open dialog on button click.


* Use below code in `default.hbs` in templates folder to render and open dialog on button click.

{% highlight html %}

    <div class="e-control">

      <div class="cols-sample-area">
      {% raw %}
            {{ej-button id="btnOpen" e-text="Click to open dialog" e-click=model.onOpen }}
		   <div class="e-container-dialog">
               {{#ej-dialog id="defaultdialog" e-title="Dialog" e-target=".cols-sample-area" e-showOnInit=false e-close=model.onDialogClose e-open=model.dlgOpen}}
                <!--dialog content-->
            <p>This is a simple dialog</p>
                {{/ej-dialog}}
            {% endraw %}
            </div>
        </div>
	</div>                  

{% endhighlight %}



* Use the below code in `default.js` in routes folder

{% highlight js %}

        export default Ember.Route.extend({

        model() {
        return {
            
            dlgOpen: function () {
                Ember.$("#btnOpen").hide();
            },
            onDialogClose: function () {
                Ember.$("#btnOpen").show();
            },
            onOpen: function () {
                Ember.$("#btnOpen").hide();
                Ember.$("#defaultdialog").ejDialog("open");
            },
        }
        }
        });

{% endhighlight %}


![Open-Dialog-dynamically](getting-started_images\getting-started_img4.png)

