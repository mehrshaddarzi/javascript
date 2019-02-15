
## intro check exist

if my element had an `id` of "find-me", I could simply use...

var elementExists = document.getElementById("find-me");

This is spec'd to either return a reference to the element or `null`. 
If you must have a Boolean value, simply toss a ``!!`` before the method call.
In addition, you can use some of the many other methods that exist for finding elements, such as (all living off document):
```
getElementById()
querySelector()/querySelectorAll()
getElementsByClassName()
getElementsByName()
```
Some of these methods return a NodeList, so be sure to check its length property, because a NodeList is an object, and therefore truthy.

https://blog.bitsrc.io/dom-selectors-explained-70260049aaf0
https://developer.rackspace.com/blog/using-querySelector-on-elements/

## Selector
```javascript
$('#test')
document.querySelector('#test')
//We use querySelector since an id is unique in the page

$('div')
document.querySelectorAll('div')

$('div, span')
document.querySelectorAll('div, span')

$('[data-example="test"]')
document.querySelectorAll('[data-example="test"]')

$(':nth-child(4n)')
document.querySelectorAll(':nth-child(4n)')

$('#test li')
document.querySelectorAll('#test li')

//ForEach in Selector
document.querySelector('#add-todo').forEach(function(key, index){

});
```

## List Method
``` javascript

// Query and remove
const p = document.querySelector('p')
p.remove()

// Query all and remove
const ps = document.querySelectorAll('p')

ps.forEach(function (p) {
    p.textContent = '******' //change Text Contetn
    // console.log(p.textContent)
    // p.remove()
})

//Remove Dom By Search Content
const paragraphs = document.querySelectorAll('p')
paragraphs.forEach(function (paragraph) {
    if (paragraph.textContent.includes('the')) {
        paragraph.remove()
    }
})


// Add a new element
const newParagraph = document.createElement('p')
newParagraph.textContent = 'This is a new element from JavaScript'
document.querySelector('body').appendChild(newParagraph)

//Add Loop Create Element
const todos = [{
    text: 'Order cat food',
    completed: false
}, {
    text: 'Clean kitchen',
    completed: true
}, {
    text: 'Buy food',
    completed: true
}, {
    text: 'Do work',
    completed: false
}, {
    text: 'Exercise',
    completed: true
}]

const incompleteTodos = todos.filter(function (todo) {
    return !todo.completed
})

const summary = document.createElement('h2')
summary.textContent = `You have ${incompleteTodos.length} todos left`
document.querySelector('body').appendChild(summary)

todos.forEach(function (todo) {
    const p = document.createElement('p')
    p.textContent = todo.text
    document.querySelector('body').appendChild(p)
})

```

## Handle User
```javascript
document.querySelector('button').addEventListener('click', function (e) {
    console.log('Add a new todo...')
    e.target.textContent = 'ddfdf'
    document.getElementById("demo").innerHTML = "Hello World";
})
```
> https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener

## input Data
```javascript
// Listen for todo text change with any keyboard
document.querySelector('#new-todo-text').addEventListener('input', function (e) {
    console.log(e.target.value)
})

// Listen for todo text change after focus
document.querySelector('#new-todo-text').addEventListener('change', function (e) {
    console.log(e.target.value)
})
```
