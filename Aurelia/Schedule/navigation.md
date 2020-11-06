---
title: Date, Appointment, and View navigation
description: Navigation between views, appointments, and date
platform: Aurelia
control: schedule
documentation: ug
keywords: view navigation, date navigation, appointment navigation
---
# Navigation

Navigation in Scheduler can be classified based on Scheduler views, date and also the appointments in it.

## View Navigation

By default, all the available [view options](/aurelia/schedule/views) except the Custom View are available at the top right corner of the Schedule header, which can be traverse through continuously as and when needed.

Clicking on the particular date header in the Week/Work Week/Month/Custom View will navigate to the day view automatically. Also, clicking on the week header ranges displayed at the left side in the month view will navigate to the Week view. These particular actions can take place only if the Week and Day view options are present in the [views](/api/js/ejschedule#members:views) Collection.

### Handling View navigation actions

Usually, the [navigation](/api/js/ejschedule#events:navigation) event gets triggered whenever the views/dates are being navigated. To block the navigation to day and week views from month view, the **navigation** event can be used in the following way.

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-current-date="11/07/2015" e-on-navigation.trigger="onNavigation($event)" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    onNavigation(event) {
        let args = event.detail;
        //args.target.currentTarget – target element which is clicked.
        let target = $(args.target.currentTarget);
        if (args.requestType == "viewNavigate" && (target.hasClass("e-headercells") || target.hasClass("e-monthheader") || target.hasClass("e-timecells")))
            args.cancel = true;
    }
    constructor() {
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 11, 2, 9, 00),
                EndTime: new Date(2015, 11, 2, 10, 30)
            }]
        };
    }
}

{% endhighlight %}

N> Based on the navigation, the appointments that lies between the particular date ranges of the current view are fetched and rendered in the Scheduler.

## Date Navigation

The Scheduler date can be navigated on two aspects either in a continuous or random manner. On pressing the previous and next navigation arrow icons in the Scheduler header will move the scheduler one date back and forth respectively.

Another way of navigating through date is by making use of the built-in calendar available within the Scheduler, which pops out when the header date range is clicked. Selecting any date in the calendar will make the Scheduler to move to that particular date appropriately.

### Handling date navigation actions

To handle the date navigation actions, the [navigation](/api/js/ejschedule#events:navigation) event can be used. For example, to block the date navigation, follow the below code example.

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-current-date="11/07/2015" e-on-navigation.trigger="onNavigation($event)" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    onNavigation(event) {
        let args = event.detail;
        //args.target – target element which is clicked.
        //args.currentDate – current date of the Scheduler.
        //args.requestType – Specifies the navigation type.
        if (args.requestType == "dateNavigate")
            args.cancel = true;
    }
    constructor() {
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 11, 2, 9, 00),
                EndTime: new Date(2015, 11, 2, 10, 30)
            }]
        };
    }
}

{% endhighlight %}

## Appointment Navigation

The Appointment navigation bars (labeled **Previous/Next Appointment**) are rendered parallel to each other on the left and right centric corners of the Schedule control. It is controlled by an API [showAppointmentNavigator](/api/js/ejschedule#members:showappointmentnavigator) which is set to true by default. When it is set to false, these bars will not be displayed on the Scheduler.

Whenever the previous/Next Appointment bars are clicked, it navigates the Scheduler to the corresponding closest date where the appointments are available. If no appointments are available beyond the current date, then these appointment bars will be in a disabled state.

The following code example shows the way to define the **showAppointmentNavigator** property for Scheduler.

{% highlight html %}

<template>
    <div>
        <ej-schedule id="Schedule1" e-current-date="11/07/2015" e-show-appointment-navigator="true" e-appointment-settings.bind="AppointmentList"></ej-schedule>
    </div>
</template>

{% endhighlight %}

{% highlight javascript %}

export class Schedule {
    constructor() {
        this.AppointmentList = {
            dataSource: [{
                Id: 100,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2015, 11, 7, 9, 00),
                EndTime: new Date(2015, 11, 7, 10, 30)
            }]
        };
    }
}

{% endhighlight %}
