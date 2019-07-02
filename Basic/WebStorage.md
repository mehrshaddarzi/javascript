
> The only difference is that localStorage has a different expiration time, sessionStorage will only be accessible while and by the window that created it is open. 
localStorage lasts until you delete it or the user deletes it.
localStorage - use for long term use.
sessionStorage - use when you need to store somthing that changes or somthing temporary


#### Add New
```javascript
localStorage.setItem('key', 'value');
sessionStorage.setItem('key', 'value');
```

#### Get Storage
```javascript
localStorage.getItem('key');
sessionStorage.getItem('key');
```

#### Remove
```javascript
localStorage.removeItem('key');
```

#### Remove All
```javascript
localStorage.clear();
```

#### Add Array to Local Storage
```javascript
let itemsArray = [];
localStorage.setItem('items', JSON.stringify(itemsArray));
const data = JSON.parse(localStorage.getItem('items'));

itemsArray.push(input.value);
localStorage.setItem('items', JSON.stringify(itemsArray));

//example two
// const user = {
//     name: 'Andrew',
//     age: 27
// }
// const userJSON = JSON.stringify(user)
// console.log(userJSON)
// localStorage.setItem('user', userJSON)

const userJSON = localStorage.getItem('user')
const user = JSON.parse(userJSON)
console.log(`${user.name} is ${user.age}`)

```

#### Use if Condition to Get
```javascript
let itemsArray = localStorage.getItem('items') ? JSON.parse(localStorage.getItem('items')) : [];

const todosJSON = localStorage.getItem('todos')
if (todosJSON !== null) {
    todos = JSON.parse(todosJSON)
}
```

#### User time Expire
```javascript
var filter_data = localStorage.getItem('wp-statistics-visitors-filter') ? JSON.parse(localStorage.getItem('wp-statistics-visitors-filter')) : {};
if (!wps_js.isset(filter_data, 'timestamp') || !wps_js.isset(filter_data, 'value') || (wps_js.isset(filter_data, 'timestamp') && wps_js.isset(filter_data, 'value') && (new Date().getTime().toString() > parseInt(filter_data.timestamp)))) {

// Create Params
let params = {
    'wps_nonce': wps_js.global.rest_api_nonce,
    'action': 'wp_statistics_visitors_page_filters'
};
params = Object.assign(params, wps_js.global.request_params);

// Create Ajax
jQuery.ajax({
    url: wps_js.global.ajax_url,
    type: 'GET',
    dataType: "json",
    data: params,
    timeout: 30000,
    success: function (data) {

        // Set LocalStorage , Cached for 3 Hour
        localStorage.setItem('wp-statistics-visitors-filter', JSON.stringify({
            value: JSON.stringify(data),
            timestamp: (new Date().getTime() + (3 * 60 * 60 * 1000))
        }));

        // Load function
        wp_statistics_show_visitors_filter(tickBox_DIV, data);
    },
    error: function (xhr, status, error) {
        jQuery("span.tb-close-icon").click();
    }
});
} else {
wp_statistics_show_visitors_filter(tickBox_DIV, JSON.parse(filter_data['value']));
}

/**
 * Isset Property in Object
 *
 * @param obj
 */
wps_js.isset = function (obj) {
    let args = Array.prototype.slice.call(arguments, 1);

    for (let i = 0; i < args.length; i++) {
        if (!obj || !obj.hasOwnProperty(args[i])) {
            return false;
        }
        obj = obj[args[i]];
    }
    return true;
};
```


#### Example Function App
```javascript
// Read existing notes from localStorage
const getSavedNotes = function () {
    const notesJSON = localStorage.getItem('notes')

    if (notesJSON !== null) {
        return JSON.parse(notesJSON)
    } else {
        return []
    }
}

// Save the notes to localStorage
const saveNotes = function (notes) {
    localStorage.setItem('notes', JSON.stringify(notes))
}

// Generate the DOM structure for a note
const generateNoteDOM = function (note) {
    const noteEl = document.createElement('p')

    if (note.title.length > 0) {
        noteEl.textContent = note.title
    } else {
        noteEl.textContent = 'Unnamed note'
    }

    return noteEl
}

// Render application notes
const renderNotes = function (notes, filters) {
    const filteredNotes = notes.filter(function (note) {
        return note.title.toLowerCase().includes(filters.searchText.toLowerCase())
    })

    document.querySelector('#notes').innerHTML = ''

    filteredNotes.forEach(function (note) {
        const noteEl = generateNoteDOM(note)
        document.querySelector('#notes').appendChild(noteEl)
    })
}
```

## Synce Data Beetwwen Windows Browser
```javascript
//if change storage
window.addEventListener('storage', function (e) {
    if (e.key === 'notes') {
        notes = JSON.parse(e.newValue)
        renderNotes(notes, filters)
    }
})
```

### Use try catch in get item
```javascript
// Fetch existing todos from localStorage
const getSavedTodos = () => {
    const todosJSON = localStorage.getItem('todos')

    try {
        return todosJSON ? JSON.parse(todosJSON) : []
    } catch (e) {
        return []
    }
}
```

#### Use LocalStorage with time for cache
https://github.com/pamelafox/lscache

### Use INDEXEDDB in localstorage
https://github.com/localForage/localForage
