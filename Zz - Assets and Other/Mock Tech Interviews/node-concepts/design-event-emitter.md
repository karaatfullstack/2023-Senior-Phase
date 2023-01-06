# Technical Mock Interview

## Overview

One of the most important concepts in JavaScript is the idea of Events. The Event Emitter pattern is central to web development.

### Question 

#### Create an Event Emitter Class from Scratch with the Following Methods (30 mins)

**You are only allowed to use the [Nodejs Documentation](https://nodejs.org/api/events.html#events_events) and the [MDN Documentation](https://developer.mozilla.org/en-US/)**

**addListener(eventName, handlerToBeAdded)**

- Be able to add listeners to an object/Register an event
- eventName is the name of the event being listened to
- handlerToBeAdded is the event handler function
- https://nodejs.org/api/events.html#events_event_newlistener

**on(eventName, handlerToBeAdded)**

- An alias for addListener
- https://nodejs.org/api/events.html#events_emitter_on_eventname_listener

**removeListener(eventName, handlerToBeRemoved)**

- Be able to remove listeners from the object
- eventName is the name of the event we are trying to remove
- handlerToBeRemoved is event handler function
- https://nodejs.org/api/events.html#events_event_removelistener

**off(eventName, handlerToBeRemoved)**

- Alias for removeListener
- https://nodejs.org/api/events.html#events_emitter_off_eventname_listener

**emit(eventName, ...eventData)**

- eventName is the name of the event
- ...eventDate is the list of arguments being supplied
- Synchronously calls each of the events registered to eventName
- https://nodejs.org/api/events.html#events_emitter_emit_eventname_args

**getListeners(eventName)**

- Return the listeners registered to the event name
- https://nodejs.org/api/events.html#events_emitter_rawlisteners_eventname

**getListenersLength(eventName)**

- Return the length of the array of listeners registered to the event name
- https://nodejs.org/api/events.html#events_emitter_listenercount_eventname

**[Extra Credit] once(eventName, handlerToAddThenRemove)**

- Be able to add a one time listener to our object, and when we emit it, it's immediately removed
- eventName is the name of the event
- handlerToAddThenRemove is the event handler funciton
- https://nodejs.org/api/events.html#events_emitter_once_eventname_listener

Example Demo:

```javascript

/*
  Event emitters are a common pattern for "registering" (storing) functions to be executed at a later time in response to some sort of arbitrary "event".

*/
// Example usage of the in built Event Emitter
const EventEmitter = require('events')

const ee = new EventEmitter()

ee.on('event', () => {
console.log('an event occurred!');
})
ee.emit('event')
```

#### Solution

```javascript
class CoolerEventEmitter {
    constructor(listeners = {}) {
      this.listeners = listeners
    }

    /*
    * addListener(eventName, cb)
    * 1. Check if eventName exists already in our listener object
    * 2. If yes, return that array
    * 3. If no, return an empty array
    * 4. Push cb into our array 
    */

    addListener(eventName, cb) {
        this.listeners[eventName] = this.listeners[eventName] || []
        return this.listeners[eventName].push(cb)
    }

    /*
    * on(eventName, cb): Alias for addListener
    */

    on(eventName, cb) {
        return this.addListener(eventName, cb)
    }

    /*
    * removeListener(eventName, cb)
    * 1. Make sure that eventName exists; if not, return false
    * 2. If it does, splice that array at the index of the cb
    */

    removeListener(eventName, cb) {
        let temp = this.listeners[eventName]

        if(!temp) return false

        return temp.splice(temp.indexOf(cb), 1)

    }

    /*
    * off(eventName, cb): Alias for removeListener
    */

    off(eventName, cb) {
        return this.removeListener(eventName, cb)
    }

    /*
    * emit(eventName, ...args)
    * 1. Make sure eventName exists; if not, return false
    * 2. Call the arguments on every element of the array
    */

    emit(eventName, ...args) {
        let temp = this.listeners[eventName]

        if (!temp) return false

        return temp.forEach((f) => {
            f(...args)
        })
    }

    /*
    * once(eventName, cb)
    * 1. Same idea as addListener/on: Check if eventName exists in the object
    * 2. If yes, return that array
    * 3. If no, return empty array
    * 4. Define a wrapper function and it will fire the cb as well as remove the listener
    * 5. Push the wrapper function into the array
    */

    once(eventName, cb) {
        this.listeners[eventName] = this.listeners[eventName] || []

        const wrapper = () => {
            cb()
            return this.off(eventName, wrapper)
        }

        return this.listeners[eventName].push(wrapper)

    }

    /*
    * getListeners(eventName)
    */

    getListeners(eventName) {
        return this.listeners[eventName]
    }

    /*
    * getListenerLength(eventName)
    */

    getListenerLength(eventName) {
        let temp = this.listeners[eventName]
        return temp.length
    }

}
```

### Notes

* N/A