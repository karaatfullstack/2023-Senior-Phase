# Technical Mock Interview

## Overview


### Question 

#### Get all <img> tags (5 mins)

Traverse DOM and collect all <img> tags.


#### Solution

Use the `getElementsByTagName` method on the document object to get an HTMLCollection of elements by the `<img>` tag name.

```js

const imgs = document.getElementsByTagName('img');
```

Alternatively, they can use the `querySelectorAll` method on the document object to get the results in the form of a NodeList.

```js

const imgs = document.querySelectorAll('img');
```


### Notes

* To add an extra challenge, you could ask the student to replace all the <img> tags with some other element. Or replace all the images sources.