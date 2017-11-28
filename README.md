# UIkit Javascript
This is a attempt to make things a bit more clear to other developers concerning UIkit v3's javascript functionality.


## Util
UIkit comes with a lot of free tools for you to use. Once [UIkit is installed](https://getuikit.com/docs/installation) correctly on your website, you can access its util functions under the `UIkit.util` namespace. Below are some examples of the provided helper functions.

### Attributes

#### `attr(element, name, value)`

```html
<input id="thanks">
```

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


#### `hasAttr(element, name)`
```html
<div id="sample" class="uk-container"></div>
```

```javascript
var element = document.getElementById('sample');

// Check if some element has some attribute
if (UIkit.util.hasAttr(element, 'class') {
    console.log('Deez Nuts for president!');
} else {
    console.log('No "ballz" where found!');
}
```

**Result**
```log
No "ballz" where found!
```


#### `removeAttr(element, name)`
```html
<div id="sample" class="uk-container" kill-it-with-fire="before it lays eggs"></div>
```

```javascript
var element = document.getElementById('sample');

// Remove attribute
UIkit.util.removeAttr(element, 'kill-it-with-fire');
```

**Result**
```html
<div id="sample" class="uk-container"></div>
```


#### `filterAttr(element, attribute, pattern, replacement)`
```html
<div id="sample" class="uk-position-top"></div>
```

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


#### `data(element, attribute)`

```html
<p data-artist="Queen">Bohemian Rhapsody</p>
```

```javascript
// Get value of data-attribute
var artist = UIkit.util.data(element, 'artist');
console.log(artist);
```

**Result**
```log
Queen
```
