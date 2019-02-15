> https://developer.mozilla.org/en-US/docs/Web/API/Location

### Redirect
```javascript
// similar behavior as an HTTP redirect
window.location.replace("http://sidanmor.com");

// similar behavior as clicking on a link
window.location.href = "http://sidanmor.com";

// Location assing
document.location.assign('/edit.html');
```

### Use Hash (Get) in url
```javascript

//in url
var id = 3;
document.location.assign('/edit.html#${id}');

//For get
location.hash

//for get without hash
var $yoyo = window.location.hash.substring(1);
var $yoyo = window.location.hash.replace("#", "");

```
