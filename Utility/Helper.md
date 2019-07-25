#### Redirect with java script
```javascript
// similar behavior as an HTTP redirect
window.location.replace("http://stackoverflow.com");

// similar behavior as clicking on a link
window.location.href = "http://stackoverflow.com";
```

#### Pass Parameter to function
```javascript
var c="hello";

(function(b){
   alert(b) 
})(c);
```

#### Repeat Run function in setinterval
```javascript
setInterval(function(){ alert("Hello"); }, 3000);
```

#### Check Keyup Request
```javascript
var timer;

$("input").on('keyup', function() {
    clearTimeout(timer);  //clear any running timeout on key up
    timer = setTimeout(function() { //then give it a second to see if the user is finished
        //do .post ajax request //then do the ajax call
    }, 1000);
});
```
