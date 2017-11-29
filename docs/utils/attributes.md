# Attributes

### `attr(element, name, value)`

**HTML**
```html
<input id="thanks">
```

**Javascript**
```javascript
var element = document.getElementById('thanks');

// Get value
var elementId = UIkit.util.attr(element, 'id');

// Set value
// This also creates the attribute, if it doesn't already exist.
UIkit.util.attr(element, 'butno', elementId);
```

**Result**
```html
<input id="thanks" butno="thanks">
```
---



### `hasAttr(element, name)`

**HTML**
```html
<div id="sample" class="uk-container"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Check if some element has some attribute
if (UIkit.util.hasAttr(element, 'long-gone')) {
    console.log('Element has attribute!');
} else {
    console.log('Attribute was not found!');
}
```

**Result**
```log
Attribute was not found!
```
---



### `removeAttr(element, name)`

**HTML**
```html
<div id="sample" class="uk-container" invalid="non-sense"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Remove attribute
UIkit.util.removeAttr(element, 'invalid');
```

**Result**
```html
<div id="sample" class="uk-container"></div>
```
---



### `filterAttr(element, attribute, pattern, replacement)`

**HTML**
```html
<div id="sample" class="uk-position-top"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Filter an attribute's value
var regexStr = '(^|\\s)uk-position-top(?!\\S)';
UIkit.util.filterAttr(element, 'class', new RegExp(regexStr, 'g'), 'uk-position-bottom');
```

**Result**
```html
<div id="sample" class="uk-position-bottom"></div>
```
---



### `data(element, attribute)`

**HTML**
```html
<p id="sample" data-artist="Queen">Bohemian Rhapsody</p>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Get value of data-attribute
var artist = UIkit.util.data(element, 'artist');
console.log(artist);
```

**Result**
```log
Queen
```
