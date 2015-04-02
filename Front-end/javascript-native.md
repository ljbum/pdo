#### addEventListner vs onclick
* addEventListner: over IE 9, more than one event to an element
* [Ref: stackoverflow](http://stackoverflow.com/questions/6348494/addeventlistener-vs-onclick)
```
var element = document.getElementById('');
element.attachEvent('onclick', function() {})
element.addEventListner('click', function() {}, false)
```
* without using jQuery to support old browsers
```
function addEvent(element, evnt, funct){
  if (element.attachEvent)
   return element.attachEvent('on'+evnt, funct);
  else
   return element.addEventListener(evnt, funct, false);
}

// example
addEvent(
    document.getElementById('myElement'),
    'click',
    function () { alert('hi!'); }
);
```
