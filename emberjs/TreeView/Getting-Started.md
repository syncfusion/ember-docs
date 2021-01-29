---
title: Getting Started for TreeView
description: TreeView - Getting-Started
platform: EmberJS
control: TreeView
documentation: ug
keywords: ejTreeView, TreeView, TreeView widget, EmberJS TreeView
---
# Getting Started

Before we start with the TreeView, please refer [this page](https://help.syncfusion.com/emberjs/overview) for general information regarding integrating Syncfusion widget’s.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route treeview/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the TreeView.

{% highlight html %}
{% raw %}
         {{#ej-treeview id="defaulttreeview" }}
			   <ul>
                        <li>Discover Music
                            <ul>
                                <li>Hot Singles</li>
                                <li>Rising Artists</li>
                                <li>Live Music</li>
                                <li>Best of 2013 So Far</li>
                            </ul>
                        </li>
                        <li>Sales and Events
                            <ul>
                                <li>100 Albums - $5 Each</li>
                                <li>Hip-Hop and R&B Sale</li>
                                <li>CD Deals</li>
                            </ul>
                        </li>
                        <li>Categories
                            <ul>
                                <li>Songs</li>
                                <li>Bestselling Albums</li>
                                <li>New Releases</li>
                                <li>Bestselling Songs</li>
                            </ul>
                        </li>
                        <li>MP3 Albums
                            <ul>
                                <li>Rock</li>
                                <li>Gospel</li>
                                <li>Latin Music</li>
                                <li>Jazz</li>
                            </ul>
                        </li>
                        <li>More in Music
                            <ul>
                                <li>Music Trade-In</li>
                                <li>Redeem a Gift Card</li>
                                <li>Branded T-Shirts</li>
                                <li>Mobile MVC</li>
                            </ul>
                        </li>
                    </ul>
			   {{/ej-treeview}}
{% endraw %}
{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the TreeView.

{% highlight html %}
{% raw %}
	export default Ember.Route.extend({
      model(){
         return {
           
        }
    }
{% endraw %}
{% endhighlight %}


## Running the application

* To run the application, execute below command.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to TreeView sample (http://localhost:4200/treeview/default). The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.png)



## Check boxes

TreeView consists of built-in checkbox option and it can be displayed to the left of the tree node by setting the [showCheckbox](https://help.syncfusion.com/api/js/ejtreeview#members:showcheckbox) property as true. It allows you to select more than one node at a time.

## Indeterminate Checkboxes

TreeView supports tristate checkboxes in addition with standard two state checkboxes. By default TreeView has been enabled with tristate in checkboxes. You can enable 2-state checkboxes by using [autoCheckParentNode](https://help.syncfusion.com/api/js/ejtreeview#members:autocheckparentnode) as false.

{% highlight html %}
{% raw %}
 {{#ej-treeview id="defaulttreeview" e-showCheckbox = true e-autoCheckParentNode = false }}
			   <ul>
                        <li>Discover Music
                            <ul>
                                <li>Hot Singles</li>
                                <li>Rising Artists</li>
                                <li>Live Music</li>
                                <li>Best of 2013 So Far</li>
                            </ul>
                        </li>
                        <li>Sales and Events
                            <ul>
                                <li>100 Albums - $5 Each</li>
                                <li>Hip-Hop and R&B Sale</li>
                                <li>CD Deals</li>
                            </ul>
                        </li>
                    </ul>
			   {{/ej-treeview}}
{% endraw %}
{% endhighlight %}

## Auto Checkable

By default checkbox state of child nodes depends up on parent node checkbox state and also parent node state gets updated based on child nodes state. You can turn off this option by setting [autoCheck](https://help.syncfusion.com/api/js/ejtreeview#members:autocheck) as false to make independent parent and child nodes checkboxes.

{% highlight html %}
{% raw %}
 {{#ej-treeview id="defaulttreeview" e-showCheckbox = true e-autoCheck = false }}
			   <ul>
                        <li>Discover Music
                            <ul>
                                <li>Hot Singles</li>
                                <li>Rising Artists</li>
                                <li>Live Music</li>
                                <li>Best of 2013 So Far</li>
                            </ul>
                        </li>
                        <li>Sales and Events
                            <ul>
                                <li>100 Albums - $5 Each</li>
                                <li>Hip-Hop and R&B Sale</li>
                                <li>CD Deals</li>
                            </ul>
                        </li>
                    </ul>
  {{/ej-treeview}}
  {% endraw %}
{% endhighlight %}


## Populating data

TreeView can be populated with local or remote data source by using a property [dataSource](https://help.syncfusion.com/api/js/ejtreeview#members:fields-datasource), which is the member of [fields](https://help.syncfusion.com/api/js/ejtreeview#members:fields) property.

In TreeView, you should use “**fields**” property to go with data source. It specifies the mapping fields for the data source to receive the data, query to process the data and field mappers to map the data members.

## Fields

The following table contains the list of members with description for **fields** property.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{'[dataSource](https://help.syncfusion.com/api/js/ejtreeview#members:fields-datasource)'| markdownify }}<br/><br/></td><td>
The data source contains the list of data for generating the TreeView list.<br/><br/></td></tr>
<tr>
<td>
{{'[query](https://help.syncfusion.com/api/js/ejtreeview#members:fields-query)'| markdownify }}<br/><br/></td><td>
It specifies the query to retrieve the data from the online server.<br/><br/></td></tr>
<tr>
<td>
{{'[tableName](https://help.syncfusion.com/api/js/ejtreeview#members:fields-tablename)'| markdownify }}<br/><br/></td><td>
It specifies the name of the table from which data to be processed from given data source.<br/><br/></td></tr>
<tr>
<td>
{{'[id](https://help.syncfusion.com/api/js/ejtreeview#members:fields-id)'| markdownify }}<br/><br/></td><td>
It specifies the ID of the node.<br/><br/></td></tr>
<tr>
<td>
{{'[parentId](https://help.syncfusion.com/api/js/ejtreeview#members:fields-parentid)'| markdownify }}<br/><br/></td><td>
It specifies the parent id of the node<br/><br/></td></tr>
<tr>
<td>
{{'[text](https://help.syncfusion.com/api/js/ejtreeview#members:fields-text)'| markdownify }}<br/><br/></td><td>
It specifies the text content of the node.<br/><br/></td></tr>
<tr>
<td>
{{'[hasChild](https://help.syncfusion.com/api/js/ejtreeview#members:fields-haschild)'| markdownify }}<br/><br/></td><td>
It specifies the node has child (which is the nested or inner level of nodes). Also it’s used in load on demand of tree data.<br/><br/></td></tr>
<tr>
<td>
{{'[expanded](https://help.syncfusion.com/api/js/ejtreeview#members:fields-expanded)'| markdownify }}<br/><br/></td><td>
It specifies the tree node to be in expanded state<br/><br/></td></tr>
<tr>
<td>
{{'[selected](https://help.syncfusion.com/api/js/ejtreeview#members:fields-selected)'| markdownify }}<br/><br/></td><td>
It specifies the select node at initialize. N> only one node get selected by default. If you enable multiple selection in TreeView then you can able to select one or more nodes at initialize.<br/><br/></td></tr>
<tr>
<td>
{{'[isChecked](https://help.syncfusion.com/api/js/ejtreeview#members:fields-ischecked)'| markdownify }} <br/><br/></td><td>
It specifies the node to be in checked state, if tree node represented with checkboxes. <br/><br/></td></tr>
<tr>
<td>
{{'[imageUrl](https://help.syncfusion.com/api/js/ejtreeview#members:fields-imageurl)'| markdownify }}<br/><br/></td><td>
It defines the image location.<br/><br/></td></tr>
<tr>
<td>
{{'[imageAttribute](https://help.syncfusion.com/api/js/ejtreeview#members:fields-imageattribute)'| markdownify }}<br/><br/></td><td>
It defines the image attributes such as height, width, styles, etc.<br/><br/></td></tr>
<tr>
<td>
{{'[spriteCssClass](https://help.syncfusion.com/api/js/ejtreeview#members:fields-spritecssclass)'| markdownify }}<br/><br/></td><td>
It defines the sprite CSS for the image tag.<br/><br/></td></tr>
<tr>
<td>
{{'[htmlAttribute](https://help.syncfusion.com/api/js/ejtreeview#members:fields-htmlattribute)'| markdownify }}<br/><br/></td><td>
It defines the HTML attributes such as class and styles for a node ("li" tag).<br/><br/></td></tr>
<tr>
<td>
{{'[linkAttribute](https://help.syncfusion.com/api/js/ejtreeview#members:fields-linkattribute)'| markdownify }}<br/><br/></td><td>
It defines the HTML attributes such as class and styles for a link tag, which is child of node.<br/><br/></td></tr>
</table>


{% highlight html %}
{% raw %}
{{ej-treeview id="localData" e-fields = model.Fields  }}
{% endraw %}
{% endhighlight %}

{% highlight html %}
{% raw %}
    let dataList = [
               { id: 1, name: "Fiction Book Lists", hasChild: true, expanded: true },
               { id: 2, pid: 1, name: "To Kill a Mockingbird " },
               { id: 3, pid: 1, name: "Pride and Prejudice " },
               { id: 4, pid: 1, name: "Harry Potter" },
               { id: 5, pid: 1, name: "The Hobbit " },
               { id: 6, name: "Mystery Book Lists", hasChild: true, expanded: true },
               { id: 7, pid: 6, name: "And Then There Were None " },
               { id: 8, pid: 6, name: "Angels & Demons" },
               { id: 9, pid: 6, name: "In Cold Blood " },
               { id: 10, pid: 6, name: "The Name of the Rose " },
               { id: 11, name: "Horror Novels", hasChild: true },
               { id: 12, pid: 11, name: "The Shining (The Shining, #1) " },
               { id: 13, pid: 11, name: "The Haunting of Hill House " },
               { id: 14, pid: 11, name: "The Silence of the Lambs (Hannibal Lecter, #2) " },
               { id: 15, name: "Novel Lists", hasChild: true },
               { id: 16, pid: 15, name: "Shadow Hills (Shadow Hills, #1) " },
               { id: 17, pid: 15, name: "After Forever Ends " },
               { id: 18, pid: 15, name: "Angel Star" },
               { id: 19, pid: 15, name: "Raised by Wolves" },
               { id: 20, pid: 15, name: "Falling From Grace" }]

 export default Ember.Route.extend({
      model(){
         return {
             Fields: { id : "id", parentId: "pid", text: "name", hasChild:"hasChild", expanded:"expanded", dataSource : dataList}
        }
    }
{% endraw %}
{% endhighlight %}

