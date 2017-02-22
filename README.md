# bootStrapModal
Libary for Promisify and Nested Modal Bootstrap Dialogs (better Modal)

## Installation

    bower install bootstrapmodal

within html just refence the .js

```html
<script src="js/bsBetterModal.js"></script>
```

## Requirements
* Bootstrap (of course)
* Jquery
* Promise Libary (we will use bluebird.js)

## Usage (see sample.html for complete example)

Inside JSCRIPT you can start a Dialog with 

```javascript
betterModal.run($('.dialogSecond'))
    .then(function (dialog) {
        // dialog holds a Jquery Object of the dialog
        // You can retrieve values from Dialog Elements
        // Using standard Jquery technics
    })
    .catch(function () {
        // Dialogs was canceld
    })
```

## More Complex Usage
You can also set references inside the dialog to change text or tags before start.  
* Add class `dlg-element` to the Element wich needs to be changed.
* Add a attribute `data-element` to the Element wich needs to be changed.

Sample:
```html
<p class="dlg-element" data-element="alerttext">This text can be changed</p>
``` 

Now you can set this text during run, using the second paramter:
```javascript
betterModal.run($('.dialogSecond'),{
    alerttext: 'This is the new Text for the element'
}) ...
```
##Modify Dialog during start
For more complex initalization scenarios you can also specify a function. This function will be executed with the JqueryDom Object of the element
Sample:
```html
<input class="dlg-element" data-element="fistname"></input>
``` 

Now you can set this text during run using the second paramter:
```javascript
betterModal.run($('.dialogSecond'),{
    firstname: function (dom) {
        dom.val('Default Value for InputElement')
    }
}) ...
```