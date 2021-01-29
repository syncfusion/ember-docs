---
layout: post
title: Member Editor Paging
description: memebr editor paging
platform: emberjs
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Member editor paging

I> This feature is applicable only for the OLAP data source.

The member editor paging helps to improve the rendering performance of the dialog by dividing the large amount of data into several sections and displaying them.

You can enable the member editor paging and set the member editor page size in the pivot client control by setting the `e-enableMemberEditorPaging` and `e-memberEditorPageSize` properties.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enableMemberEditorPaging=model.enableMemberEditorPaging e-memberEditorPageSize=model.memberEditorPageSize }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            dataSource: {
                                data: "//bi.syncfusion.com/olap/msmdpump.dll", //data
                                catalog: "Adventure Works DW 2008 SE",
                                cube: "Adventure Works",
                                rows: [
                                    {
                                        fieldName: "[Date].[Fiscal]"
                                    }
                                ],
                                columns: [
                                    {
                                        fieldName: "[Product].[Product Categories]"
                                    }
                                ],
                                values: [
                                    {
                                        measures: [
                                            {
                                                fieldName: "[Measures].[Internet Sales Amount]",
                                            },
                                            {
                                                fieldName: "[Measures].[Growth in Customer Base Trend]"
                                            }, 
                                            {
                                                fieldName: "[Measures].[Growth in Customer Base Status]"
                                            }
                                        ],
                                        axis: "columns"
                                    }
                                ]
                            },
                            enableMemberEditorPaging: true,
                            memberEditorPageSize: 100
        }
    }
});

{% endhighlight %}

Following are the navigation option available in the member editor pager:
* Move first: Navigates to the first page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Move last: Navigates to the last page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in numeric value.


![](Member_Editor_images/member_editor.png)