# 🕐 jQuery Timesetter

[![jQuery](https://img.shields.io/badge/jQuery-3.7.1+-0769AD?style=flat-square&logo=jquery&logoColor=white)](https://jquery.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.3+-7952B3?style=flat-square&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/Version-1.3.0-blue.svg?style=flat-square)](#)

A modern, elegant jQuery plugin that creates intuitive time input controls with hours and minutes. Features real-time validation, keyboard navigation, and a beautiful responsive design built on Bootstrap 5.

## ✨ Features

- 🎯 **Intuitive UI** - Clean, modern interface with up/down controls
- ⌨️ **Keyboard Support** - Arrow keys for quick time adjustments
- ✅ **Real-time Validation** - Instant feedback with smart error correction
- 📱 **Mobile Responsive** - Perfect on all devices with Bootstrap 5
- 🎨 **Customizable** - Extensive options for styling and behavior
- 🚀 **Lightweight** - Minimal footprint with maximum functionality
- 🔧 **Easy Integration** - Simple setup with any HTML element

## 🚀 Quick Start

### Installation

```html
<!-- Include dependencies -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css" rel="stylesheet">
<link href="css/jquery.timesetter.css" rel="stylesheet">

<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="js/jquery.timesetter.js"></script>
```

### Basic Usage

Transform any HTML element into a time picker:

```html
<div id="my-timepicker"></div>
```

```javascript
// Simple initialization
$("#my-timepicker").timesetter();

// With custom options
$("#my-timepicker").timesetter({
    hour: { value: 14, symbol: "h" },
    minute: { value: 30, symbol: "m", step: 15 },
    postfixText: " (Afternoon)"
});
```

## 📖 Documentation

### Configuration Options

Create powerful time controls with extensive customization:

```javascript
const options = {
    hour: {
        value: 0,           // Initial hour value
        min: 0,            // Minimum hour (0-23)
        max: 24,           // Maximum hour (1-24)
        step: 1,           // Hour increment step
        symbol: "h"        // Display symbol after hour
    },
    minute: {
        value: 0,          // Initial minute value
        min: 0,            // Minimum minute (0-59)
        max: 60,           // Maximum minute (1-60)
        step: 15,          // Minute increment step (1, 5, 10, 15, 30)
        symbol: "min"      // Display symbol after minute
    },
    direction: "increment",       // "increment" or "decrement"
    postfixText: "",             // Text displayed after the controls
    numberPaddingChar: '0'       // Padding character (e.g., "09" vs "9")
};

$(".timepicker").timesetter(options);
```

### API Methods

#### Setting Values
```javascript
// Set individual values
$(".timepicker").timesetter().setHour(14);
$(".timepicker").timesetter().setMinute(30);

// Set by total minutes (e.g., 175 minutes = 2h 55m)
$(".timepicker").timesetter().setValuesByTotalMinutes(175);

// Set postfix text
$(".timepicker").timesetter().setPostfixText(" (Business Hours)");
```

#### Getting Values
```javascript
// Get individual values
const hours = $(".timepicker").timesetter().getHoursValue();        // Returns: 14
const minutes = $(".timepicker").timesetter().getMinutesValue();    // Returns: 30
const total = $(".timepicker").timesetter().getTotalMinutes();      // Returns: 870
const postfix = $(".timepicker").timesetter().getPostfixText();     // Returns: " (Business Hours)"

// Get default settings
const defaults = $(".timepicker").timesetter().getDefaultSettings();
```

### Method Chaining
```javascript
// Chain multiple operations
$(".timepicker")
    .timesetter(options)
    .setHour(9)
    .setMinute(0)
    .setPostfixText(" AM");
```

## 🎨 Examples

### Basic Time Picker
```javascript
$(".basic-time").timesetter();
```

### Business Hours Picker
```javascript
$(".business-hours").timesetter({
    hour: { value: 9, min: 8, max: 18, symbol: "h" },
    minute: { value: 0, step: 30, symbol: "min" },
    postfixText: " (Business Hours)"
});
```

### Meeting Duration Picker
```javascript
$(".duration").timesetter({
    hour: { value: 1, min: 0, max: 8, symbol: "hr" },
    minute: { value: 0, step: 15, symbol: "min" },
    postfixText: " Duration"
});
```

### Appointment Scheduler
```javascript
// Start time
$(".start-time").timesetter({
    hour: { value: 9, symbol: "h" },
    minute: { value: 0, step: 15, symbol: "m" },
    postfixText: " Start"
});

// End time
$(".end-time").timesetter({
    hour: { value: 17, symbol: "h" },
    minute: { value: 0, step: 15, symbol: "m" },
    postfixText: " End"
});
```

## 🎮 Interactive Controls

- **🖱️ Click Controls**: Use ▲/▼ buttons to adjust time
- **⌨️ Keyboard Navigation**: 
  - `↑` Arrow Up - Increment current field
  - `↓` Arrow Down - Decrement current field
  - `Tab` - Switch between hour/minute fields
- **📱 Touch Friendly**: Optimized for mobile devices
- **🔄 Auto-correction**: Invalid values are automatically corrected

## 💡 Advanced Usage

### Multiple Time Pickers
```javascript
// Initialize multiple pickers with different configs
$(".morning-time").timesetter({
    hour: { value: 8, max: 12 },
    postfixText: " AM"
});

$(".evening-time").timesetter({
    hour: { value: 18, min: 12, max: 24 },
    postfixText: " PM"
});
```

### Dynamic Updates
```javascript
// Update picker based on user selection
$("#picker1").timesetter().setHour(14);

// Get values for calculations
const totalMinutes = $("#picker1").timesetter().getTotalMinutes();
const endTime = totalMinutes + 120; // Add 2 hours
$("#picker2").timesetter().setValuesByTotalMinutes(endTime);
```

## 🔧 Technical Requirements

| Component | Version | Purpose |
|-----------|---------|---------|
| **jQuery** | 3.7.1+ | Core functionality |
| **Bootstrap** | 5.3.3+ | Responsive design & styling |
| **Bootstrap Icons** | 1.11.3+ | Modern iconography |

## 🧪 Demo

Try the live demonstration:

| Demo File | Purpose |
|-----------|---------|
| **`example.html`** | Interactive demonstration of all features |

### Quick Demo
Open `example.html` directly in your browser to see the timesetter in action with various configurations and examples.

## 🤝 Contributing

We welcome contributions! Please feel free to submit issues and pull requests.

### Development Setup
```bash
git clone https://github.com/sandunangelo/jquery-timesetter.git
cd jquery-timesetter
# Open files directly in your browser or use a local web server
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Author**: Sandun Angelo Perera
- **Blog**: [jQuery Timesetter Plugin](http://sandunangelo.blogspot.com/2018/09/jquery-timesetter-plugin.html)
- **Repository**: [GitHub](https://github.com/sandunangelo/jquery-timesetter)

---

<div align="center">

**Made with ❤️ for the jQuery community**

[⭐ Star this project](https://github.com/sandunangelo/jquery-timesetter) | [🐛 Report Bug](https://github.com/sandunangelo/jquery-timesetter/issues) | [💡 Request Feature](https://github.com/sandunangelo/jquery-timesetter/issues)

</div>
