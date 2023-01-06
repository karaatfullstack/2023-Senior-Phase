# Technical Mock Interview

## Overview

Drill CSS fundamentals by vertically and horizontally centering a block element.

### Question 

#### Center A Div (15 mins)

Given the HTML and CSS below, responsively center the #circle in the viewport along the vertical and horizontal axis, regardless of scroll position or any other elements on the DOM. The solution should be written in less than 4 lines of CSS. Flexbox is not needed to solve this problem.

```html

<div id="container">
  <div id="circle">
  </div>
</div>
```

```css

#container {
  position: absolute;
  width: 500px;
  height: 400px;
  background-color: cyan;
}

#circle {
  border-radius: 50%;
  background-color: red;
  width: 100px;
  height: 100px;
   /*
     Add CSS Here 
   */
}

```

[JSFiddle](https://jsfiddle.net/3sf5ntw2/)

#### Solution


```css

#circle {
  border-radius: 50%;
  background-color: red;
  width: 100px;
  height: 100px;
  
  position: fixed;
  top: calc(50vh - 50px);
  left: calc(50vw - 50px);
}

```


### Notes

Good sub-questions to ask:

* What if our div is in another parent container?
* What is the CSS Box model?
* What are the different acceptable values for the `position` attribute?
* What is responsive design?
