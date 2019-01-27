#### start
```javascript
jQuery(document).ready(function($){

$(".title").hide();
jQuery(".title").hide()

});
```

#### Click Event
```javascript
$(document).on("click","#test-element",function() {
    alert("click bound to document listening for #test-element");
});
```

#### Ajax Get request + extend function parameter
```javascript
ajax: function (action, arg = false, dynamic = false) {
    setInterval(function () {
        let ajax = {'action': 'wpr_' + action, 'wpr_time': data.wpr_time};
        if (arg !== false) {
            ajax = $.extend({}, ajax, arg);
        }
        if (dynamic !== false) {
            ajax[dynamic.name] = $(dynamic.obj).attr(dynamic.attr);
        }
        $.get({
            url: data.wpr_ajax,
            dataType: "json",
            cache: false,
            data: ajax,
            success: function (data) {
                app[action](data);
            },
            error: function () {
            }
        });
    }, this.random_time());
}
```
