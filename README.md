[![](https://data.jsdelivr.com/v1/package/npm/color-calendar/badge)](https://www.jsdelivr.com/package/npm/color-calendar)

# Color Calendar
A customizable events calendar component library 

![Color Calendar](https://raw.githubusercontent.com/PawanKolhe/color-calendar/master/screenshots/banner.PNG)

## 🚀 Features
- Zero dependencies
- Add events to calendar
- Perform some action on calendar date change
- Month and year picker built-in
- Themes available
- Customize using CSS variables or passing options parameters while creating calendar.
- More coming soon...

## 📦 Getting Started

### CDN
#### JavaScript
```html
<script src="https://cdn.jsdelivr.net/npm/color-calendar/dist/bundle.js">
```

#### CSS
Pick a css file according to the theme you want.
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/color-calendar/dist/css/theme-basic.css">
<!-- or -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/color-calendar/dist/css/theme-glass.css">
```

#### Fonts
Get fonts from [Google Fonts](https://fonts.google.com/)
```html
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap" rel="stylesheet">
```
Check what fonts the [theme](#themes) needs or pass your own fonts in [options](#options-fonts).

### NPM
#### Installation
```bash
npm install color-calendar
```
#### Import
```javascript
import Calendar from 'color-calendar';
```

Then add CSS and fonts.

## 🔨 Usage
### JavaScript
```javascript
new Calendar()
```
Or you can pass in **options**.
```javascript
new Calendar({
    id: '#myCalendar'
})
```

### HTML
```html
<div id="myCalendar"></div>
```

<a id="options"></a>
## ⚙️ Options

### `id`
Type: `String`  
Default: `#color-calendar`  

Selector referencing HTMLElement where the calendar instance will bind to.

### `eventsData`
Type: `Array[...Objects]`  
Default: `null`  

```javascript
[
    {
      start: '2020-08-17T06:00:00',
      end: '2020-08-18T20:30:00',
      ...
    },
    ...
]
```

Array of objects containing events information. Properties `start` and `end` care *required* for each event in the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date and time format.

### `theme`
Type: `String`  
Default: `basic`  
Options: `basic` | `glass`  

Choose from available themes.

### `primaryColor`
Type: `String`  
Default: *based on theme*  
Example: `#1a237e`  

Main color accent of calendar. *Pick a color in rgb, hex or hsl format.*

### `headerColor`
Type: `String`  
Default: *based on theme*  
Example: `rgb(0, 102, 0)`  

Color of header text.

### `headerBackgroundColor`
Type: `String`  
Default: *based on theme*  
Example: `black`  

Background color of header. *Only works on some themes.*

### `weekdaysColor`
Type: `String`  
Default: *based on theme*  

Color of weekdays text.  *Only works on some themes.*

### `weekdayType`
Type: `String`  
Default: `long-lower`  
Options: `short` | `long-lower` | `long-upper`  

Select how weekdays will be displayed. E.g. M, Mon, or MON.

### `monthDisplayType`
Type: `String`  
Default: `long`  
Options: `short` | `long`  

Select how month will be displayed in header. E.g. Feb, February.

### `startWeekday`
Type: `Number`  
Default: `0`  
Options: `0` | `1` | `2` | `3` | `4` | `5` | `6`   

Starting weekday. Mapping: 0 (Sun), 1 (Mon), 2 (Tues), 3 (Wed), 4 (Thurs), 5 (Fri), 6 (Sat)

<a id="options-fonts"></a>
### `fontFamilyHeader`
Type: `String`  
Default: *based on theme*  
Example value: `'Open Sans', sans-serif`  

Font of calendar header text.

### `fontFamilyWeekdays`
Type: `String`  
Default: *based on theme*  

Font of calendar weekdays text.

### `fontFamilyBody`
Type: `String`  
Default: *based on theme*  

Font of calendar days as well as month and year picker text.

### `dropShadow`
Type: `Boolean`  
Default: `true`  

Whether to have a calendar drop shadow.

### `border`
Type: `String`  
Default: *based on theme*  
Example value: `5px solid black`  

Set CSS style of border.

### `borderRadius`
Type: `String`  
Default: `0.5rem`  

Set CSS border radius of calendar.

## 🖱 Events

### `dateChanged`
Type: `Function`  
Props:
- `currentDate`
    - Type: `Date`
    - Currently selected date
- `filteredDateEvents`
    - Type: `EventData[]`
    - All events on that particular date
```typescript
const options = {
    ...
    dateChanged: (currentDate?: Date, filteredDateEvents?: EventData[]) => {
        // do something
    };
    ...
}
```

Emitted when the selected date is changed.

### `monthChanged`
Type: `Function`  
Props:
- `currentDate`
    - Type: `Date`
    - Currently selected date
- `filteredMonthEvents`
    - Type: `EventData[]`
    - All events on that particular month

Emitted when the current month is changed.

<!-- ## 🔧 Methods
Coming soon... -->

<a id="themes"></a>
## 🎨 Themes
Currently 2 themes available. More on the way.

### `basic`
<img src="https://raw.githubusercontent.com/PawanKolhe/color-calendar/master/screenshots/theme-basic.PNG" alt="Basic Theme" width="400" />  

#### CSS Custom Properties
`--cal-color-primary`: #0440a0;  
`--cal-font-family-header`: "Work Sans", sans-serif;  
`--cal-font-family-weekdays`: "Work Sans", sans-serif;  
`--cal-font-family-body`: "Work Sans", sans-serif;  
`--cal-drop-shadow`: 0 7px 30px -10px rgba(150, 170, 180, 0.5);  
`--cal-border`: 5px solid rgba(4, 64, 160, 0.1);  
`--cal-border-radius`: 0.5rem;  
`--cal-header-color`: black;  
`--cal-weekdays-color`: black;  

### `glass`
<img src="https://raw.githubusercontent.com/PawanKolhe/color-calendar/master/screenshots/theme-glass.PNG" alt="Glass Theme" width="400" />  

#### CSS Custom Properties
`--cal-color-primary`: #EC407A;  
`--cal-font-family-header`: 'Open Sans', sans-serif;  
`--cal-font-family-weekdays`: 'Open Sans', sans-serif;  
`--cal-font-family-body`: 'Open Sans', sans-serif;  
`--cal-drop-shadow`: 0 7px 30px -10px rgba(150, 170, 180, 0.5);  
`--cal-border`: none;  
`--cal-border-radius`: 0.5rem;  
`--cal-header-color`: white;  
`--cal-header-background-color`: rgba(0, 0, 0, 0.3);  

## Meta
[LICENSE (MIT)](https://github.com/PawanKolhe/color-calendar/blob/master/LICENSE)
