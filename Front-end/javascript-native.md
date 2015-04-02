#### addEventListner vs onclick
* addEventListner: over IE 9, more than one event to an element
* [stackoverflow answer](http://stackoverflow.com/questions/6348494/addeventlistener-vs-onclick)

```
var element = document.getElementById('');
element.attachEvent('onclick', function() {})
element.addEventListner('click', function() {}, false)
```
