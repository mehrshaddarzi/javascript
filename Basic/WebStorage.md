
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

## Synce DAta Beetwwen Windows Browser
```javascript
//if change storage
window.addEventListener('storage', function (e) {
    if (e.key === 'notes') {
        notes = JSON.parse(e.newValue)
        renderNotes(notes, filters)
    }
})
```

#### Use LocalStorage with time for cache
https://github.com/pamelafox/lscache

### Use INDEXEDDB in localstorage
https://github.com/localForage/localForage
