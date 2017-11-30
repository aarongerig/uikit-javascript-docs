# DOM (Document Object Model)

### `isRtl`

**HTML**
```html
<html dir="rtl"></html>
```

**Javascript**
```javascript
// Check if base direction of text is set to RTL
if (UIkit.util.isRtl) {
    console.log('Direction is set to RTL');
} else {
    console.log('Direction is set to LTR');
}
```

**Result**
```log
Direction is set to RTL
```
---



### `isReady()`

**Javascript**
```javascript
// Returns true as soon as the whole document and all its sub resources have been loaded completely
if (UIkit.util.isReady()) {
    console.log('Website is ready!');
} else {
    console.log('Something is still loading...');
}
```

**Result**
```log
Something is still loading...
```
---


    
### `ready(fn)`

**Javascript**
```javascript
// Runs the callback function as soon as the page's Document Object Model (DOM) becomes safe to manipulate
UIkit.util.ready(function() {
    console.log('DOM is now safely manipulable.');
});
```

**Result**
```log
DOM is now safely manipulable.
```
---



### `transition(element, props, duration = 400, transition = 'linear')`
> **Important:** Before starting a transition, a value for the CSS property to be transitioned has to be present!

**HTML**
```html
<div id="sample" class="uk-card uk-card-primary uk-card-body">Primary Card</div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Let's you transition any CSS property to a certain value
UIkit.util.transition(element, {'opacity': 0}).then(function() { console.log('Transition finished!'); });
```

**Result**
```log
Transition finished!
```
---



### `Transition { start() -> transition(), stop(element), cancel(element), inProgress(element) }`
> **Description:** With the Transition object you have four handy functions available.  
`start()`:      Is an alias for the above mentioned `transition()` function  
`stop()`:       Stops the transition  
`cancel()`:     Cancels the transition  
`inProgress()`: Either returns true or false, whether the transition is in progress or not

**HTML**
```html
<div id="sample" class="uk-card uk-card-primary uk-card-body">Primary Card</div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');
var Transition = UIkit.util.Transition;

// Start the transition
Transition.start(element, {'background': '#000', 'color': '#fff'}, 500, 'ease');

// Stop the transition
Transition.stop(element);

// Cancel the transition
Transition.cancel(element);

// Check whether transition is in progress
if (Transition.isProgress(element)){
    console.log('Transition in progress!');
} else {
    console.log('No transition running!');
}
```

**Result**
```log
No transition running!
```