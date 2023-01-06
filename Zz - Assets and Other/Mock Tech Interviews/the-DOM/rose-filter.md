# Technical Mock Interview

## Overview

Implement an Instagram-esque color filter. Topics include DOM logic and numerical programming.

_They say life is nicer through rose-colored glasses!_

### Question 

#### Rose Colorizer (30 mins)

Design a simple web app that features a color swatch preview (in 6 color hex notation, e.g. #a02bff), and filter button. When pressed, the filter button should apply a 'Rose' fitler, making the color of the swatch 20% more red, 10% less green, and 10% more blue. You should write this web app in pure JS, HTML, and CSS if possible. 



#### Solution

```html

<body>
  <div id=swatch></div>
  <p>
    You are viewing: <span id='value'></span>
  </p>
  <button id='filter'>Rose Filter</button>
</body>

```

```css

#swatch {
  height: 250px;
  width: 250px;
  border: 2px solid black
}

```

```javascript

let colorStr = '1AB20D';

const swatch = document.getElementById('swatch');
const span = document.getElementById('value')
const roseBtn = document.getElementById('filter');


swatch.style.backgroundColor = span.innerHTML = `#${colorStr}`;

const colorize = () => {
  // slice each 2-digift color hex val, convert to base-10;
  // NB: 255 === FF in hex
  let redVal = (parseInt(colorStr.slice(0, 2), 16));
  let greenVal = (parseInt(colorStr.slice(2, 4), 16));
  let blueVal = (parseInt(colorStr.slice(4, 6), 16));

  // adjust values to be more rose, within (0,255) range
  // NB: 25 == 10% of 255 (FF)
  redVal < 205 ? redVal += 50 : redVal = 255; 
  greenVal > 24 ? greenVal -= 25 : greenVal = 0;
  blueVal < 230 ? blueVal += 25 : blueVal = 255;
  
  //convert back to hex && add buffer 0 to single-digit strings
  const convertAndAddBuffer = val => val.toString(16).length === 1 ? '0' + val.toString(16) : val.toString(16);

  colorStr = [redVal, greenVal, blueVal].map(convertAndAddBuffer).join('');
  swatch.style.backgroundColor = span.innerHTML = `#${colorStr.toUpperCase()}`;

};

roseBtn.addEventListener('click', colorize));

```


### Notes

Good sub-questions to ask:

* How is measuring a number hexadecimal (base-16) different from decimal (base-10). What is 10% in base-16?

* How is a 6-digit hex string constructed? How do those values correspond the a given RGB color value?

* How can we convert numbers from decimal to hex, and vice versa?

W* hat are some edge cases to consider? What if a color is completely saturated (#FF) or completely unsaturated (#00)?

* [js-fiddle](https://jsfiddle.net/d1oescjn/)