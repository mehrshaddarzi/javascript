
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

#### Use LocalStorage with time for cache
https://github.com/pamelafox/lscache

### Use INDEXEDDB in localstorage
https://github.com/localForage/localForage
