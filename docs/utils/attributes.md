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
if (UIkit.util.hasAttr(element, 'ballz') {
    console.log('Deez Nuts for president!');
} else {
    console.log('No "ballz" where found!');
}
```

**Result**
```log
No "ballz" where found!
```
---



### `removeAttr(element, name)`

**HTML**
```html
<div id="sample" class="uk-container" kill-it="with fire, before it lays eggs"></div>
```

**Javascript**
```javascript
var element = document.getElementById('sample');

// Remove attribute
UIkit.util.removeAttr(element, 'kill-it');
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
// Here we exchange the class uk-position-top with uk-position-bottom.
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
