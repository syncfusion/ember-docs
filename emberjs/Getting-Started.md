---
layout: post
title: Getting Started with Syncfusion Ember CLI
description: Getting Started.
platform: emberjs
control: Common
documentation: ug
---

# Essential JS for Ember

## System Requirements

To work with Ember, you need to install the followings on your machine.

* Node JS [5.x.x+ version](https://nodejs.org/en/).

* NPM [3.x.x+ version](https://blog.npmjs.org/post/85484771375/how-to-install-npm)

* Ember CLI [2.x.x+ version](https://ember-cli.com/).

* Any Text Editor

## Create a simple Ember Application

Please follow the below steps to use Syncfusion Ember add-on in your Ember CLI application. 

* Create Ember CLI application using the command [ember new ember-app](https://ember-cli.com/user-guide/#create-a-new-project).

* Add syncfusion-ember in `package.json` to add the Syncfusion Ember add-on into your application `ember-app`.

* Add [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) package for source files (`scripts` and `css`).

{% highlight js %}
    "devDependencies": {
        ...
        "syncfusion-ember":"*"; //To install the latest version
        "syncfusion-javascript": "*"; // To install source files
    }
{% endhighlight %}

* Disable `EXTEND_PROTOTYPES` option in the `environment.js` file under `config` folder to prevent `on` function prototype extension in our controls events.

{% highlight js %}
    EmberENV: {
		FEATURES: {
			// Here you can enable experimental features on an ember canary build
			// e.g. 'with-controller': true
		},
		EXTEND_PROTOTYPES: false
    },
{% endhighlight %}

* Open the command prompt in the root folder and run the command `npm install` to download the dependent files in node-modules.

* Copy the files `ej.web.all.min` and `jsrender.min` from `web/scripts` folder which is in JavaScript build samples location `(Click Explore Demos button from the Javascript Dashboard)` or copy `ej.web.all.min` from `node_modules/syncfusion-javascript/Scripts/ej/web` and download `jsrender.min` file from [CDN](https://cdn.syncfusion.com/js/assets/external/jsrender.min.js) into the `vendor` folder. Import the same into the application using below code in `ember-cli-build.js`.

{% highlight js %}
    module.exports = function(defaults) {
        var app = new EmberApp(defaults, {
            // Add options here
        });
        app.import('vendor/ej.web.all.min.js');
        app.import('vendor/jsrender.min.js');
        return app.toTree();
    };
{% endhighlight %}

* Create the folder `scripts` and `content` in public folder and copy JavaScript and CSS files from `web/scripts` and `web/themes` folder which is in JavaScript build samples location `(Click Explore Demos button from the Javascript Dashboard)` or copy the `themes` files from `node_modules/syncfusion-javascript/Content/ej/web` into created folders.

* And include the necessary file references in Index page which is in `app` folder of the Ember application.

{% highlight html %}
    <head>
        <link rel="stylesheet" href="{% raw %}{{rootURL}}{% endraw %}
        content/ejthemes/default-theme/ej.web.all.min.css">
    </head>
    <body>
        <script src="{% raw %}{{rootURL}}{% endraw %}scripts/scripts/jsondata.min.js" type="text/javascript"></script>
    </body>
{% endhighlight %}

## Create Grid sample in the Ember CLI application

* Open the command prompt in the folder `ember-app`.

* Use the command [ember generate route grid/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/) to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the Grid.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true }}
	{% endraw %}
	</div>
{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the Grid.

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
                data: window.gridData,
                cols: [
                    { field: "OrderID", headerText: "Order ID", width: 75, textAlign: ej.TextAlign.Right },
                    { field: "CustomerID", headerText: "Customer ID", width: 80 },
                    { field: "EmployeeID", headerText: "Employee ID", width: 75, textAlign: ej.TextAlign.Right},
                    { field: "Freight", width: 75, format: "{0:C}", textAlign: ej.TextAlign.Right, priority: 3 },
                    { field: "OrderDate", headerText: "Order Date", format: "{0:MM/dd/yyyy}"},
                    { field: "ShipCity", headerText: "Ship City", width: 110, priority: 2 }
               ]
           }
        }
    });
{% endhighlight %}

* Use the below code in `.eslintrc` file to ignore the ESLint errors while using `ej` in samples as like `ej.TextAlign.Right`.

{% highlight js %}
    ...
    rules: {
        ...
    },
    globals: {
	    ej: false
    }
    ...
{% endhighlight %}

## Build or Run the Ember CLI application

* To Build the Ember CLI application using the command `ember build` which builds the application and creates the `dist` folder. Now you can host the `dist` folder in IIS.

* To Run the Ember CLI application using the command `ember serve` which builds the application and creates the `dist` folder. However it hosts the application in the url `http://localhost:4200`.

* Open the browser and navigates to `http://localhost:4200`.

![](/emberjs/Getting-Started_images/Getting-Started_img1.png)