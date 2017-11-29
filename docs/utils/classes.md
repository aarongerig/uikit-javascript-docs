# Classes

### `addClass(element, ...args)`

**HTML**
```html
<input id="sample">
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Add class
UIkit.util.addClass(element, 'uk-section');

// This function also supports multiple classes
UIkit.util.addClass(element, 'uk-section-primary', 'uk-section-small');
```

**Result**
```html
<input id="sample" class="uk-section uk-section-primary uk-section-small">
```
---



### `removeClass(element, ...args)`

**HTML**
```html
<input id="sample" class="uk-section uk-section-primary uk-section-small">
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Remove class
UIkit.util.removeClass(element, 'uk-section');

// This function also supports multiple classes
UIkit.util.removeClass(element, 'uk-section-primary', 'uk-section-small');
```

**Result**
```html
<input id="sample" class="">
```
---



### `removeClasses(element, cls)`

**HTML**
```html
<div id="sample" class="uk-position-top uk-overlay uk-overlay-default"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Remove classes based on a regular expression
var regexStr = 'uk-position-(top|bottom|left|right)(-[a-z]+)?';
UIkit.util.removeClass(element, regexStr);
```

**Result**
```html
<div id="sample" class=" uk-overlay uk-overlay-default"></div>
```
---



### `replaceClass(element, ...args)`

**HTML**
```html
<div id="sample" class="uk-card uk-card-default"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Replace class
UIkit.util.replaceClass(element, 'uk-card-default', 'uk-card-primary');
```

**Result**
```html
<div id="sample" class="uk-card uk-card-primary"></div>
```
---



### `hasClass(element, cls)`

**HTML**
```html
<div id="sample" class="uk-position-relative"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Check if some element has some class
if (UIkit.util.hasClass(element, 'uk-position-relative')) {
    console.log('Element has the class!');
} else {
    console.log('Class was not found!');
}
```

**Result**
```log
Element has the class!
```
---



### `toggleClass(element, ...args)`
> **Optional force parameter:** As the last argument of this function, you can pass a Boolean type (true or false).
  It turns the toggle into a one way-only operation. If set to false, the class will only be removed but not added again
  and vice versa. Further reading [MDN: classList](https://developer.mozilla.org/en/docs/Web/API/Element/classList)
  


**HTML**
```html
<div id="sample" class="uk-card uk-card-default"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Toggle a class
for (i = 0; i < 3; i++) { 
  UIkit.util.toggleClass(element, 'uk-card-default');
}
```

**Result**
```html
<div id="sample" class="uk-card"></div>
```