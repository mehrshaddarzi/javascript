#### Redirect with java script
```javascrip

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

