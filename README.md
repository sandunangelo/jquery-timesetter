# jQuery-Timesetter
jquery-timesetter is a jQuery plugin which generates a UI component useful to take user inputs or to display time values with hour and minutes in a friendly format. UI provide intuitive behaviors for better user experience such as validations in real-time and keyboard arrow key support.

## Dependencies
 - jQuery 2.2.4
 - Bootstrap 3.3.7 CSS file

## How to use
Simplest usage to start with you can use any HTML container element such as `<div/>` or `<p/>`.
To apply timesetter capabilities you need to call .timesetter() on the HTML element as shown below.

```javascript
$(".div1").timesetter();
```

#### Customize options
While there is a default set of options built in inside the plugin, you are free to customize them as you need as shown below.

```javascript
var options = {
    hour: {
        value: 0,
        min: 0,
        max: 24,
        step: 1,
        symbol: "hrs"
    },
    minute: {
        value: 0,
        min: 0,
        max: 60,
        step: 15,
        symbol: "mins"
    },
    direction: "increment", // increment or decrement
    inputHourTextbox: null, // hour textbox
    inputMinuteTextbox: null, // minutes textbox
    postfixText: "", // text to display after the input fields
    numberPaddingChar: '0' // number left padding character ex: 00052
};

$(".div1").timesetter(options);
```

#### Set values
Below functions supports in setting values into the plugin of the element.

```javascript
$(".div1").timesetter(options).setHour(17);
$(".div1").timesetter(options).setMinute(15);
$(".div2").timesetter().setValuesByTotalMinutes(175);
$(".div2").timesetter().setPostfixText();
```

#### Read values
Below functions supports in reading values from the plugin of the element.

```javascript
var defaultOptions = $(".div1").timesetter().getDefaultSettings();
var hours = $(".div1").timesetter().getHoursValue();
var minutes = $(".div1").timesetter().getMinutesValue();
var totalMinutes = $(".div1").timesetter().getTotalMinutes();
var postfixText = $(".div1").timesetter().getPostfixText();
```

### Authors blog:
http://sandunangelo.blogspot.com/2018/09/jquery-timesetter-plugin.html
