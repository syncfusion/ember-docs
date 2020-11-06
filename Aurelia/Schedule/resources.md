---
title: Schedule - Resource handling with multiple option
description: Handling multiple resources in Scheduler
platform: Aurelia
control: schedule
documentation: ug
keywords: resource, resources, multiple resources, grouping
---
# Resources

The Scheduler provides **Resources** support, with which the single Scheduler is shared by multiple resources simultaneously. Each resource in the Scheduler is arranged in a column/row wise, with individual spacing to display all its respective appointments on a single page. It also supports the grouping of resources, thus enabling the categorization of resources in a hierarchical structure and shows it either in expandable groups (**Horizontal** **view**) or else vertical hierarchy one after the other (**Vertical** **view**).

One or more resources can be assigned to the Scheduler appointments by making selection of the resource options available in the appointment window.

## Fields of Resources

The default options available within the [resources](/api/js/ejschedule#members:resources) collection are as follows,

### name (**String**)

A unique resource name which is used for differentiating various resource objects while grouping it in levels.

### title (**String**)

It holds the title name of the resource field to be displayed on the Scheduler appointment window.

### field (**String**)

It holds the name of the resource field to be bound to the Scheduler appointments which contains the resource Id.

### allowMultiple (**Boolean**)

When set to true, allows multiple selection of resource names, thus creating multiple instances of same appointment for the selected resources.

### resourceSettings (**Object**)

It holds the field names of the resources dataSource to be bound to the Scheduler.

The following are the resource fields which must be defined within the **resourceSettings** that holds the appropriate column names from the dataSource.

<table>
    <tr>
        <th>Field name<br/><br/></th>
        <th>Description<br/><br/></th>
    </tr>
    <tr>
        <td>text<br/><br/></td>
        <td>Binds the text field name in the dataSource to the resourceSettings <b>text</b>. These text gets listed out in the resources field of the appointment window. It’s mandatory.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>id<br/><br/></td>
        <td>Binds the id field name in the dataSource to the resourceSettings <b>id</b>. It’s mandatory.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>groupId<br/><br/></td>
        <td>Binds the groupId field name in the dataSource to the resourceSettings <b>groupId</b>. This field is not necessary for a resource object (resource data) defined as first level within the resources collection.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>color<br/><br/></td>
        <td>Binds the color field name in the dataSource to the resourceSettings <b>color</b>. It is optional.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>appointmentClass<br/><br/></td>
        <td>Binds the appointmentClass field name in the dataSource. It applies the custom CSS class name to the appointments based on the resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>start<br/><br/></td>
        <td>Binds the starting work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the starting work hour for specific resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>end<br/><br/></td>
        <td>Binds the end work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the end work hour for specific resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>workWeek<br/><br/></td>
        <td>Binds the resources working days field name in the dataSource. It's optional, and accept array of strings which is nothing but only the week day names. When provided with some values (array of day names), only those days will render for the specific resources.<br/><br/><br/><br/></td>
    </tr>
</table>

**Example**: To set the resources options using all the above specified fields,

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-current-date="11/07/2015" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            resourceSettings: {
                dataSource: [
                    { OwnerText: "Nancy", id: 1, OwnerColor: "#f8a398" },
                    { OwnerText: "Steven", id: 2, OwnerColor: "#56ca95" }
                ],
                text: "OwnerText",
                id: "id",
                color: "OwnerColor"
            }
        }, {
            field: "roomId",
            title: "Room(s)",
            resourceSettings: {
                dataSource: [{
                    text: "Room1",
                    id: 1,
                    groupId: 1,
                    color: "#f8a398", workHourStart: 10, workHourEnd: 18, customDays: ["monday","wednesday","friday"]
                }, {
                    text: "Room2",
                    id: 2,
                    groupId: 2,
                    color: "#56ca85", workHourStart: 6, workHourEnd: 10, customDays: ["monday","saturday"]
                }, {
                    text: "Room3",
                    id: 3,
                    groupId: 2,
                    color: "#56ac88", workHourStart: 11, workHourEnd: 15, customDays: ["tuesday","friday"]
                }],
                text: "text",
                id: "id",
                color: "color",
                groupId: "groupId", start: "workHourStart", end: "workHourEnd", workWeek: "customDays"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2,
                roomId: 3
            }],
            resourceFields: "ownerId,roomId"
        };
    }
}

{% endhighlight %}

N> The resource object defined at **first level** within the **resources** collection doesn’t make use of the **groupId** field, as there is no previous levels applicable to map.

## Data Binding

The resource data can be bound to the Schedule control through the **resourceSettings** options available within the **resources** property. The data-binding can be done either using JSON object collection or DataManager ([ej.DataManager](/js/datamanager/overview)) instance which contains the resources related data.

### JSON Data

**Example**: To set the resource data with array of **JSON** object collection

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-current-date="11/07/2015" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            resourceSettings: {
                dataSource: [{
                    text: "Nancy",
                    id: 1,
                    color: "#f8a398"
                }, {
                    text: "Steven",
                    id: 2,
                    color: "#56ca85"
                }],
                text: "text",
                id: "id",
                color: "color"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2
            }, {
                Id: 101,
                Subject: "Research on Clouds",
                StartTime: new Date(2015, 04, 07, 7, 00),
                EndTime: new Date(2015, 04, 07, 10, 30),
                ownerId: 1
            }],
            resourceFields: "ownerId"
        };
    }
}

{% endhighlight %}

### Remote Data

**Example**: To set the resource data through the instance of **ejDataManager**

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-width="60%" e-height="550px" e-current-date="11/07/2015" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        let dataManager = ej.DataManager({
            // referring data from remote service (url binding)
            url: "http://mvc.syncfusion.com/OdataServices/Northwnd.svc"
        });
        // query to fetch the records from the specified table “Events”
        let queryResource = ej.Query().select("CategoryID", "CategoryName").from("Categories").take(3);
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            resourceSettings: {
                dataSource: dataManager,
                query: queryResource,
                text: "CategoryName",
                id: "CategoryID"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2
            }, {
                Id: 101,
                Subject: "Research on Clouds",
                StartTime: new Date(2015, 04, 07, 7, 00),
                EndTime: new Date(2015, 04, 07, 10, 30),
                ownerId: 1
            }],
            resourceFields: "ownerId"
        };
    }
}

{% endhighlight %}

## Multiple Resources (Without Grouping)

It is possible to display the Scheduler in default look without visually showcasing all the resources on it, but it allow the user to assign the required resources to the appointments through the appointment window resource options.

The appointments belonging to all the resources will be displayed on the Scheduler which will be differentiated based on the resource color assigned in the **resourceSettings** (depicting to which resource that particular appointment belongs).

**Example**: To display default Scheduler with multiple resource options in the appointment window,

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-width="60%" e-height="550px" e-current-date="11/07/2015" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            allowMultiple: true,
            resourceSettings: {
                dataSource: [
                    { text: "Nancy", id: 1, color: "#f8a398" },
                    { text: "Steven", id: 2, color: "#56ca85" }
                ],
                text: "text",
                id: "id",
                color: "color"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2
            }, {
                Id: 101,
                Subject: "Research on Clouds",
                StartTime: new Date(2015, 04, 07, 6, 00),
                EndTime: new Date(2015, 04, 07, 9, 30),
                ownerId: 1
            }],
            resourceFields: "ownerId"
        };
    }
}

{% endhighlight %}

N> Setting **allowMultiple** to **true** in the above code snippet allows the user to select multiple resources in the appointment window and also creates multiple copies of the same appointment in the Scheduler for each resources while saving.

## Grouping

Scheduler supports both single and multiple levels of resource grouping that can be customized either in horizontal or vertical Scheduler views. In Vertical view - the levels are displayed in a tree structure one after the other, but in horizontal view – the levels are grouped in a vertically expandable/collapsible structure.

### Single-Level

This type of grouping allows the Scheduler to display all the resources at a single level simultaneously. The appointments will make use of the **color** defined for the first resource instance as its background color.

**Example**: To display the Scheduler with single level resource grouping options,

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-width="100%" e-current-date="11/07/2015" e-group.bind="ScheduleGroup" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleGroup = {
            resources: ["Owners"]
        };
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            name: "Owners",
            resourceSettings: {
                dataSource: [{
                    text: "Nancy",
                    id: 1,
                    color: "#f8a398"
                }, {
                    text: "Steven",
                    id: 2,
                    color: "#56ca85"
                }],
                text: "text",
                id: "id",
                color: "color"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2
            }, {
                Id: 101,
                Subject: "Discovery of Exoplanets",
                StartTime: new Date(2015, 04, 07, 6, 00),
                EndTime: new Date(2015, 04, 07, 9, 30),
                ownerId: 1
            }],
            resourceFields: "ownerId"
        };
    }
}

{% endhighlight %}

N> The **name** field mentioned in the **resource** object needs to be specified within the **group** property in order to enable the grouping option in Scheduler.

### Multi-Level

This type of grouping displays the resources in the Scheduler at multiple levels with a set of resources grouped under each parent. The appointments will make use of the **color** defined for the first/top level resource instance as its background color.

**Example**: To display the Scheduler with multiple level resource grouping options,

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-width="100%" e-current-date="11/07/2015" e-group.bind="ScheduleGroup" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleGroup = {
            resources: ["Owners", "Rooms"]
        };
        this.ScheduleResources = [{
            field: "ownerId",
            title: "Owner",
            name: "Owners",
            resourceSettings: {
                dataSource: [
                    { OwnerText: "Nancy", id: 1, OwnerColor: "#f8a398" },
                    { OwnerText: "Steven", id: 2, OwnerColor: "#56ca95" }
                ],
                text: "OwnerText",
                id: "id",
                color: "OwnerColor"
            }
        }, {
            field: "roomId",
            title: "Room(s)",
            name: "Rooms",
            resourceSettings: {
                dataSource: [
                    { text: "Room1", id: 1, groupId: 1, color: "#f8a398" },
                    { text: "Room2", id: 2, groupId: 2, color: "#56ca85" },
                    { text: "Room3", id: 3, groupId: 2, color: "#56ac88" }
                ],
                text: "text",
                id: "id",
                color: "color",
                groupId: "groupId"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2,
                roomId: 3
            }],
            resourceFields: "ownerId,roomId"
        };
    }
}

{% endhighlight %}

N> Here, the appointments will make use of the **color** defined for the Owners resource instance as its background color.

## Different Working days and Hours for Resources

It is possible to assign different workdays and workhours for each resources present within the Scheduler. The process of assigning different working days for every individual resources is applicable only for the vertical Scheduler mode and not for timeline view, whereas the customization of workhours for each resources is applicable on both the Scheduler orientation.  The custom workdays and workhours needs to be defined within the `resourceSettings` property using the following 3 sub-properties available within it.

* [start](/api/js/ejschedule#members:resources-resourcesettings-start) is used to define the work start hour for each individual resources.
* [end](/api/js/ejschedule#members:resources-resourcesettings-end) is used to define the work end hour for each individual resources.
* [workWeek](/api/js/ejschedule#members:resources-resourcesettings-workWeek) is used to define different working days for each individual resources.

**Example**: To display the Scheduler with each individual resources having different workhours and workdays, the code example is depicted below.

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-width="100%" e-current-view="workweek" e-current-date="11/07/2015" e-group.bind="ScheduleGroup" e-resources.bind="ScheduleResources" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.ScheduleGroup = {
            resources: ["Owners", "Rooms"]
        };
        this.ScheduleResources = [{
            field: "roomId",
            title: "Room",
            name: "Rooms", allowMultiple: false,
            resourceSettings: {
                dataSource: [
                    { text: "ROOM1", id: 1, groupId: 1, color: "#cb6bb2" },
                    { text: "ROOM2", id: 2, groupId: 1, color: "#56ca85"}
                ],
                text: "text", id: "id", groupId: "groupId", color: "color"
            }
        }, {
            field: "ownerId",
            title: "Owner",
            name: "Owners", allowMultiple: true,
            resourceSettings: {
                dataSource: [
                    { text: "Nancy", id: 1, groupId: 1, color: "#ffaa00", on: 10, off: 18, customDays: ["monday","wednesday","friday"] },
                    { text: "Steven", id: 3, groupId: 2, color: "#f8a398", on: 6, off: 10, customDays: ["tuesday","thursday"] },
                    { text: "Michael", id: 5, groupId: 1, color: "#7499e1", on: 11, off: 15, customDays: ["sunday","tuesday","thursday","saturday"] }
                ],
                text: "text", id: "id", groupId: "groupId", color: "color", start: "on", end: "off", workWeek: "customDays"
            }
        }];
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 04, 05, 9, 00),
                EndTime: new Date(2015, 04, 05, 10, 30),
                ownerId: 2,
                roomId: 3
            }],
            resourceFields: "ownerId,roomId"
        };
    }
}

{% endhighlight %}
