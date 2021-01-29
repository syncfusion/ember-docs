---
layout: post
title: getting-started
description: getting started
platform: emberjs
control: Navigation Drawer
documentation: ug
---

# Getting Started

In this section, you can learn how to create a simple navigation drawer. Before going to getting started with NavigationDrawer widget please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/)  to know how to create simple Essential EmberJS application.
If you want to know individual script reference to create NavigationDrawer Please Refer under [Requires](https://help.syncfusion.com/api/js/ejnavigationdrawer/)                     

![](getting-started_images\getting-started_img1.png)

## Create Navigation Drawer Widget

The following steps guide you in adding a **Navigation Drawer** control for a web application that displays a list of items such as home, profile, photos and location where you can navigate to desired page by clicking on the option available in the drawer. 

{% highlight html %}

    <div class="e-container-navigationdrawer">
    {% raw %}
    {{#ej-navigationdrawer id="navpane" e-enableListView=true e-listViewSettings=model.listViewSettings e-mouseUp=model.mouseUp}}
    <ul>
        <li data-ej-text="Home"></li>
        <li data-ej-text="People"></li>
        <li data-ej-text="Profile"></li>
    </ul>
    {{/ej-navigationdrawer}}

    {% endraw %}

    </div>

{% endhighlight %}

Add the following code in  corresponding "hbs" file to Create the target element.

{% highlight html %}

    <div class="e-lv">
    <div class="e-header">
    <div id="butdrawer"
    class="drawericon e-icon">
    </div>

    </div>
    </div>

{% endhighlight %}


{%highlight javascript%}

    export default Ember.Route.extend({
    model(){
        return {
            listViewSettings: { width: 200, selectedItemIndex: 0, mouseUp: function(e) {
                Ember.$("#butdrawer").parent().children("h2").text(e.text);
            }, persistSelection: true }
            
            }
        }
    });

{% endhighlight %}

To set the target icon image from sprite and to position the target icon properly use the following styles.

{% highlight css %}

    

        #navpane{
            top:6%;
        }

        .e-header {
            padding-top: 8px;
            padding-left: 0px;
        }  
        .drawericon:before {
            content: "\e76b";
            font-size: 28px;
			height: 26px;
        }
       
    

{% endhighlight %}


Create the navigation drawer control as follows. You can display the navigation items as a list (or it can be any template) by using the ListView control. This is achieved by setting the **e-enableListView** property to true. Also you can open the drawer by clicking on target element by setting the **e-targetId** property. 

Add the following code in the **script** tag.

{% highlight html %}

        <div class="e-container-navigationdrawer">
    {% raw %}                
        {{#ej-navigationdrawer id="navpane" e-targetId="butdrawer" e-enableListView=true e-listViewSettings=model.listViewSettings e-mouseUp=model.mouseUp}}
                        <ul>
                            <li data-ej-text="Home"></li>
                            <li data-ej-text="People"></li>
                            <li data-ej-text="Profile"></li>
                        </ul>
            {{/ej-navigationdrawer}}
            
            {% endraw %}

            
        </div>

{% endhighlight %}


You can display the drawer either by clicking on the target icon or by swiping from left on the page. Refer to the following screenshot.


![](getting-started_images\getting-started_img1.png)

You can set the images for Navigation Drawer by using the **data-ej-imageClass** attribute in the inner list elements.

{% highlight html %}

        <div class="e-container-navigationDrawer">
        {% raw %}
        {{#ej-navigationdrawer id="navpane" e-targetId="butdrawer" e-enableListView=true e-listViewSettings=model.listViewSettings e-mouseUp=model.mouseUp}}
        <ul>
            <li data-ej-imageclass="e-home" data-ej-text="Home"></li>
            <li data-ej-imageclass="e-profile" data-ej-text="People"></li>
            <li data-ej-imageclass="e-people" data-ej-text="Profile"></li>
        </ul>
        {{/ej-navigationdrawer}}
        
        {% endraw %}
        </div>
    
{% endhighlight %}



You can define the image classes specified for the list items as follows.

{% highlight css %}

    #navpane{
                top:6%;
            }

            .e-header {
                padding-top: 8px;
                padding-left: 0px;
            }  
            .drawericon:before {
                content: "\e76b";
                font-size: 28px;
                height: 26px;
            }
        @font-face {
            font-family: 'ej-xlfont';
            src: url('content/ejthemes/common-images/tools/icons.eot');
            src: url('content/ejthemes/common-images/tools/icons.eot') format('embedded-opentype'), url('content/ejthemes/common-images/tools/icons.woff') format('woff'),url('content/ejthemes/common-images/tools/icons.woff') format('woff'), url('content/ejthemes/common-images/tools/icons.ttf') format('truetype'), url('content/ejthemes/common-images/tools/icons.svg') format('svg');
            font-weight: normal;
            font-style: normal;
        }
        .e-home:before {
    font-family: "ej-xlfont";
    content: "\e900";
    }
    .e-profile:before {
    font-family: "ej-xlfont";
    content: "\e901";
    }
    .e-people:before {
    font-family: "ej-xlfont";
    content: "\e902";
    }
    .e-home,.e-profile,.e-people{
    font-size:24px;
    color:black;            
    }


{% endhighlight %}



Run the above code to render the following output.

![](getting-started_images\getting-started_img3.png)

You can add desired page content while selecting the options in navigation drawer as follows.



{% highlight html %}

    <div id="home" class="subpage">
        The Home screen allows you to choose the specific content type displayed.
    </div>
    <!-- Profile Page Content-->
    <div id="profile" class="subpage" style="display: none">
        The Profile page content is displayed.
    </div>
    <!-- Photos Page Content-->
    <div id="people" class="subpage" style="display: none">
        The People page content is displayed.
    </div>

{% endhighlight %}



You can load the appropriate content for the navigation items by updating the content through mouseUp handler of ListView. You can define the handler and pass the method name with **e-mouseUp** attribute through listViewSettings. Also to view which item’s content is being loaded in the page, make the list selection to persist in the drawer by setting **e-persistSelection** as true. Refer to the following code example.

Add the following code in the **script** file.

{% highlight javascript %}

        export default Ember.Route.extend({
        model(){
           return {
            listViewSettings: { width: 200, selectedItemIndex: 0, mouseUp: function(e) {
                Ember.$("#butdrawer").parent().children("h2").text(e.text);
            }, persistSelection: true },
            position: "normal",
            
                }
             }
        });

{% endhighlight %}

Run the above code to render the following output. 

![](getting-started_images\getting-started_img4.png)

