# Virtual DOM

Time: 5 mins

### Prompt

What is React's Virtual DOM?

### Answer

The virtual DOM is a programming concept where an ideal, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called _reconciliation_. It abstracts out the attribute manipulation, event handling, and manual DOM updating that you would otherwise have to use to build your app.

#### Key points

* "virtual" copy of the "real" DOM
* manipulating the virtual DOM is faster than manipulating the real DOM
  * JS operations (on the virtual DOM) are faster than UI changes (on the real DOM)
* Changes through "diffing" or "comparing" the virtual DOM with the real DOM (aka "reconciliation")
