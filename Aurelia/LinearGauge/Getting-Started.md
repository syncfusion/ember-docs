---
layout: post
title: Getting-Started
description: getting started
platform: Aurelia
control: LinearGauge
documentation: ug
---

# Getting Started

This section briefly explains on how to create a Linear Gauge control for your application.

* You can provide data for a Linear Gauge and display them in a required way. You can also customize the default Linear Gauge appearance to meet your requirements.
*  In this example, you will learn how to create a Linear Gauge and how to design a thermometer, which can be used to check the body temperature of a person.

![](Getting-Started_images/Getting-Started_img1.png)


## Create a Linear Gauge

1.To create Syncfusion Aurelia application refer [Aurelia Getting Started documentation](https://help.syncfusion.com/aurelia/overview#getting-started "").
2.Create `linearGauge` folder inside `src/samples` location.
3.Create `linearGauge.html` file inside  `src/samples/linearGauge` folder and use the below code for rendering LinearGauge component 
4.Create a <div> tag.
	
 {% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="lineargauge">
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}

5.Create `linearGauge.js` file inside `src/samples/linearGauge` folder with below code snippet.

{% highlight javascript %}

export class LinearGauge {
    constructor() {}
    }

{% endhighlight %}

Run the above code example to get a default Linear Gauge with default values as follows.

![](Getting-Started_images/Getting-Started_img2.png)





## Set Height and Width values

Basic attributes of each canvas elements are height and width. You can set the height and width of the gauge using the following code example. It sets the height and width of the canvas image where the thermometer is to be rendered.

{% highlight javascript %}

export class BasicUse {
constructor() {
 
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500">
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}


Run the above code example and you will get the following gauge as similar to default. Here height and width of the canvas are set for given values.

![](Getting-Started_images/Getting-Started_img3.png)



## Set Animation option and Label Color

* You can draw the Thermometer with some Label color to display the measurement value. For example give the labelColor as “#8c8c8c”.
* Set the EnableAnimation property as false to avoid animation on the pointers.

{% highlight javascript %}

export class BasicUse {
constructor() {
 
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}

Run the above code example and you will get the following gauge as the output.

![](Getting-Started_images/Getting-Started_img4.png)



## Provide Scale Values

* The scale must have the appearance of a thermometer. By giving ScaleType as Thermometer, you can render a thermometer design.
* Minimum temperature can go up to -10 and maximum temperature can rise up to 110, so you can give minimum scale value as -10 and maximum value as 110.
* Set the location values such as vertical and horizontal position of the thermometer and give the thermometer height as Length.
* You can give the Minor Interval value as 5 to get the exact temperature on the patient.

{% highlight javascript %}

export class BasicUse {
constructor() {
  this.scales: [{
                type: "thermometer",
                backgroundColor: "transparent",
                minimum: -10,
                maximum: 110,
                minorIntervalValue: 5,
                width: 20,
                position: { x: 50, y: 18 },
                length: 355,
                border: { width: 0.5 }
                }];
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-scales.bind="scales" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}


Run the above code example and you will get the following gauge as the output.



![](Getting-Started_images/Getting-Started_img5.png)


## Add Pointers

In Linear Gauge the two types of pointers available are: Marker pointer and Bar pointer.

* Marker pointer is displayed as a pointer device that shows the actual values. But for your thermometer there is no need for the marker pointer. So you can hide the marker pointer by giving opacity as 0. 
* Bar pointer acts as the mercury metal that shows the exact temperature of the patient. Set some of the basic properties of the Bar pointer such as Width, BarPointerDistanceFromScale, BarPointerValue and BarPointerBackgroundColor.



{% highlight javascript %}

export class BasicUse {
constructor() {
  this.scales: [{
                //Add the pointers customization code here
                markerPointers: [{ opacity: 0 }],
                barPointers: [{
                    width: 10,
                    distanceFromScale: -0.5,
                    value: 37,
                    backgroundColor: "#DB3738"
                }]
                }];
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-scales.bind="scales" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}

On executing the above code sample renders a Linear Gauge with bar marker as follows.

![](Getting-Started_images/Getting-Started_img6.png)



##Add Label Customization

* For thermometer, you can display the label value on two sides, to get temperature in different scales. For that you can add two label values in an array.
* To display the value around the scales, labels are used. You can customize the label placement, font (including its style and family) and its distance from scale.


{% highlight javascript %}

export class BasicUse {
constructor() {
  this.scales: [{
                labels: [{
                    placement: "near",
                    font: {
                        size: "10px", fontFamily: "Segoe UI",
                        fontStyle: "Normal"
                    }
                },
                {
                    placement: "far",
                    distanceFromScale: { x: 10 }
                }],
               
                }];
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-scales.bind="scales" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}


On executing the above code sample renders a customized Linear Gauge as follows.

![](Getting-Started_images/Getting-Started_img7.png)



## Add Tick Details

* Tick style has two values called major interval and minor interval. You can set major ticks width and height greater than Minor ticks. And you can give TickColor, for better visibility in light backgrounds.
* Here four tick details are used for both sides having minor and major ticks. To display the tick value add the following code example.

{% highlight javascript %}

export class BasicUse {
constructor() {
  this.scales: [{
                ticks: [{
                    type: "majorInterval",
                    height: 8,
                    width: 1,
                    color: "#8c8c8c",
                    distanceFromScale: { y: -4 }
                }, {
                    type: "minorInterval",
                    height: 4,
                    width: 1,
                    color: "#8c8c8c",
                    distanceFromScale: { y: -4 }
                }, {
                    type: "majorInterval",
                    placement: "far",
                    height: 8,
                    width: 1,
                    color: "#8c8c8c",
                    distanceFromScale: { y: -4 }
                }, {
                    type: "minorInterval",
                    placement: "far",
                    height: 4,
                    width: 1,
                    color: "#8c8c8c",
                    distanceFromScale: { y: -4 }
                }]
               
                }];
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-scales.bind="scales" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}



On executing the above code sample renders a Linear Gauge with custom labels as follows.

![](Getting-Started_images/Getting-Started_img8.png)



## Add Custom Label Details

* Custom labels are used to specify the texts in the gauge.
* It can be customized through various properties.
* In order to show the custom labels, change the showIndicators property to True.
* Here you can use custom text to display three range descriptions.

{% highlight javascript %}

export class BasicUse {
constructor() {
  this.scales: [{
              showCustomLabels: true,
                 customLabels: [{
                    value: "(° C)",
                    position: { x: 44, y: 78 },
                    font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "bold" },
                    color: "#666666"
                }, {
                    value: "(° F)",
                    position: { x: 56, y: 78 },
                    font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "bold" },
                    color: "#666666"
                },
                {
                    position: { x: 51, y: 90 },
                    font: { size: "13px", fontFamily: "Segoe UI", fontStyle: "bold" },
                    color: "#666666"
                }]
                }];
}
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-scales.bind="scales" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}

Run the above code example to get the following gauge as output.



![](Getting-Started_images/Getting-Started_img9.png)



## Change Scale from Degree to Fahrenheit 

Add the function that converts the temperature in degree to Fahrenheit in the label, with an index value of 1.


{% highlight javascript %}

export class BasicUse {
constructor() {
  
}
 drawLabels (args) {
              
                if (args.label.index == 1) {
                    args.style.textValue = (args.label.value * (9 / 5)) + 32;
                    args.style.font = { size: "10px", fontFamily: "Segoe UI", fontStyle: "normal" };
                }
            }
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-on-draw-labels.trigger="drawLabels($event)" >
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}

Run the above code example and you will get the following gauge as output.

![](Getting-Started_images/Getting-Started_img10.png)



## Add Custom Label for Current Value

Add the function that displays the current temperature value in the custom label.

{% highlight javascript %}

export class BasicUse {
constructor() {
  
}
 drawCustomLabels (args) {
               if (args.customLabelIndex == 2) {

            let temp = args.scaleElement.barPointers[0].value;

            let faValue = (temp * (9 / 5)) + 32;

            if (temp == -10) {

                args.style.textValue = "Very Cold Weather" + "(" + faValue.toFixed(1) + "° F)";

            }

            else if ((temp > -10 && temp < 0) || (temp > 0 && temp < 15)) {

                args.style.textValue = "Cool Weather" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp == 0) {

                args.style.textValue = "Freezing point of Water" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp >= 15 && temp < 30) {

                args.style.textValue = "Room Temperature" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp == 30) {

                args.style.textValue = "Beach Weather" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp == 37) {

                args.style.textValue = "Body Temperature" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp == 40) {

                args.style.textValue = "Hot Bath Temperature" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp > 40 && temp < 100) {

                args.style.textValue = "Very Hot Temperature" + " (" + faValue.toFixed(1) + "° F)";

            }

            else if (temp == 100) {

                args.style.textValue = "Boiling point of Water" + " (" + faValue.toFixed(1) + "° F)";

            }

        }
            }
}

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<body>
<template>
<div>
     <ej-linear-gauge id="linearGauge" e-height="500" e-width="500" e-label-color="#8c8c8c" e-enable-animation= "false" e-on-draw-labels.trigger="drawLabels($event)" 
     e-on-draw-custom-labels.trigger="drawCustomLabels($event)">
        </ej-linear-gauge>
        </div>
</template>
</body>
</html>

{% endhighlight %}
![](Getting-Started_images/Getting-Started_img11.png)

