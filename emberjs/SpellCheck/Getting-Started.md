---
title: Getting started with SpellCheck component	
description: Rendering a basic SpellCheck
platform: emberjs
control: spellcheck
documentation: ug
keywords: ejSpellCheck, spellcheck, spellcheck widget, emberjs spellcheck, getting started, service reference
---
# Getting Started 

To get start with how to use the SpellCheck component in an Ember application, refer the basic system requisites and also the steps to create an Ember CLI application from [here](https://help.syncfusion.com/emberjs/getting-started).

## Script/CSS References

The following list of external dependencies are mandatory in order to render any of the Syncfusion controls.

* [jQuery](http://jquery.com) - 1.7.1 and later versions.
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates.

Refer the `ej.web.all.min.js` script file (which encapsulates all the `ej` controls and frameworks in a single file) and CSS file `ej.web.all.min.css` (which includes styles of all the widgets) in your application for the proper creation and rendering of the SpellCheck control.

## Control Initialization

The SpellCheck component can be created with a prefix of `ej-`.The code example for defining control in EmberJS is as follows,

{% highlight html %}

	{% raw %}
	{{ej-spellcheck id="spellcheck"}}
    {% endraw %}

{% endhighlight %}

Define the below code in order to bind any model data to the SpellCheck.

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
        return {
        }
    }
});
    
{% endhighlight %}

## Service Reference

Assign the service method (CheckWords) path to the property `dictionaryUrl` within the dictionary settings, which is mandatory to check the spelling of the words.

{% highlight html %}

<div class="e-container-spellcheck">
    {{#ej-spellcheck id="TextArea" e-dictionarySettings=model.dictionarySettings }}
    {{/ej-spellcheck}}
</div>

{% endhighlight %}

The `CheckWords` method will perform the splitting of the target sentence into separate words, and then check whether each word in it is erroneous or not. If the word is erroneous, then it fetches the possible suggestions for it and returns those details as result. 

{% highlight js %}

    export default Ember.Route.extend({
        model() {
            return {
                dictionarySettings: {
                    dictionaryUrl: "http://js.syncfusion.com/ejservices/api/SpellCheck/CheckWords",
                    customDictionaryUrl: "http://js.syncfusion.com/ejservices/api/SpellCheck/AddToDictionary"
                }
            };
        }
    });

</script>

{% endhighlight %}

## Spell Checking

To check the spelling of a target element's content, you need to add a button on the page and then calling either of the available SpellCheck methods `showInDialog` or `validate` on this button click, so as to highlight the error words.

The following code example depicts the way of checking the target element's spelling through `validate` method.

{% highlight html %}

<div class="e-container-spellcheck">
    {{#ej-spellcheck id="TextArea" contenteditable="true" e-create=model.create e-dictionarySettings=model.dictionarySettings }} 
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    {{/ej-spellcheck}}
</div>
<div>
    {{ej-button id="SpellCheck" e-text="Spell check" e-click=model.click }}
</div>

{% endhighlight %}

In the below code example, `validate` method of SpellCheck is called on the click action of the button.

{% highlight js %}

    export default Ember.Route.extend({
        model() {
            return {
                dictionarySettings: {
                    dictionaryUrl: "http://js.syncfusion.com/ejservices/api/SpellCheck/CheckWords",
                    customDictionaryUrl: "http://js.syncfusion.com/ejservices/api/SpellCheck/AddToDictionary"
                },                
                create: function () {
                    Ember.$("#TextArea").attr("contenteditable", true);
                },
                click: function () {
                    var spellObj = Ember.$("#TextArea").data("ejSpellCheck");
                    spellObj.validate();
                }
            };
        }
    });

{% endhighlight %}

## Run the application

Execute the below command in the command prompt to run the application.

{% highlight javascript %}
 
 ember serve

{% endhighlight %}
