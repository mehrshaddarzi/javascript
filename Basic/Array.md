## Basic Structure
```javascript
const todos = ['Order cat food', 'Clean kitchen', 'Buy food', 'Do work', 'Exercise']
todos.length //Gent Number count

console.log(`You have ${todos.length} todos!`)
console.log(`Todo: ${todos[0]}`)
console.log(`Todo: ${todos[todos.length - 2]}`)

// Create an array with five todos
// You have x todos
// Print the first and second to last items -> Todo: walk the dog
```
> https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

## Helper Function
```javascript
const notes = ['Note 1', 'Note 2', 'Note 3']

// console.log(notes.pop()) //remove last item
// notes.push('My new note') //add item

// console.log(notes.shift()) //remove first item
// notes.unshift('My first note') //add first item

notes.splice(1, 1) //start key=1 and removed one item which push in twice parameter
 
notes.splice(1, 0, 'This is the new second item') // add new item after key=1
 
notes.splice(1, 0, 'This is the new second item') // replace key = 1 with this item

notes[2] = 'This is now the new note 3'

console.log(notes.length)
console.log(notes)
```

## Loop
```javascript
const notes = ['Note 1', 'Note 2', 'Note 3']

notes.forEach(function (item, index) {
    console.log(index)
    console.log(item)
})

for(let count =0; count < notes.lentgh; count++) {
}
```

## Search in Array
```javascript

cont n = ["Strawberry", "Banana", "Mango"]
var pos = n.indexOf('Banana');
// 1 return key of Banana

if(element.find('div').eq(3).text().indexOf('whatever') > -1) {
}

const notes = [{
    title: 'My next trip',
    body: 'I would like to go to Spain'
}, {
    title: 'Habbits to work on',
    body: 'Exercise. Eating a bit better.'
}, {
    title: 'Office modification',
    body: 'Get a new seat'
}]

const index = notes.findIndex(function (note, index) {
    return note.title === 'Habbits to work on'
})
console.log(index)


//Show array by search
const notes = [{
    title: 'My next trip',
    body: 'I would like to go to Spain'
}, {
    title: 'Habbits to work on',
    body: 'Exercise. Eating a bit better.'
}, {
    title: 'Office modification',
    body: 'Get a new seat'
}]

const findNote = function (notes, noteTitle) {
    return notes.find(function (note, index) {
        return note.title.toLowerCase() === noteTitle.toLowerCase()
    })
}

const note = findNote(notes, 'some other office modification')
console.log(note)


//Delete Array By Search
const todos = [{
    text: 'Order cat food',
    completed: true
}, {
    text: 'Clean kitchen',
    completed: false
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

const deleteTodo = function (todos, todoText) {
    const index = todos.findIndex(function (todo) {
        return todo.text.toLowerCase() === todoText.toLowerCase()
    })

    if (index > -1) {
        todos.splice(index, 1)
    }
}
 
deleteTodo(todos, '!!buy food')
console.log(todos)

```


## Filter Array
```javascript
const notes = [{
    title: 'My next trip',
    body: 'I would like to go to Spain'
}, {
    title: 'Habbits to work on',
    body: 'Exercise. Eating a bit better.'
}, {
    title: 'Office modification',
    body: 'Get a new seat'
}]

const findNotes = function (notes, query) {
    return notes.filter(function (note, index) {
        const isTitleMatch = note.title.toLowerCase().includes(query.toLowerCase())
        const isBodyMatch = note.body.toLowerCase().includes(query.toLowerCase())
        return isTitleMatch || isBodyMatch
    })
}

console.log(findNotes(notes, 'eating'))


//example two
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


const getThingsToDo = function (todos) {
    return todos.filter(function (todo) {
        return !todo.completed
    })
}

console.log(getThingsToDo(todos))
```


## Sort
```javascript
//Sort By Alphabix
const notes = [{
    title: 'my next trip',
    body: 'I would like to go to Spain'
}, {
    title: 'Habbits to work on',
    body: 'Exercise. Eating a bit better.'
}, {
    title: 'Office modification',
    body: 'Get a new seat'
}]

const sortNotes = function (notes) {
    notes.sort(function (a, b) {
        if (a.title.toLowerCase() < b.title.toLowerCase()) {
            return -1
        } else if (b.title.toLowerCase() < a.title.toLowerCase()) {
            return 1
        } else {
            return 0
        }
    })
}
sortNotes(notes)

//Sort By Boolean
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

const sortTodos = function (todos) {
    todos.sort(function (a, b) {
        if (!a.completed && b.completed) {
            return -1
        } else if (!b.completed && a.completed) {
            return 1
        } else {
            return 0
        }
    })
}

//sort by date
var array = [{id: 1, date: "Mar 12 2012 10:00:00 AM"},{id: 2, date: "Mar 28 2012 08:00:00 AM"}];
function sortFunction(a,b){  
    var dateA = new Date(a.date).getTime();
    var dateB = new Date(b.date).getTime();
    return dateA > dateB ? 1 : -1;  
}; 

var array = [{id: 1, date: "Mar 12 2012 10:00:00 AM"},{id: 2, date: "Mar 28 2012 08:00:00 AM"}];
array.sort(sortFunction);
```


## Complete Example Working Array
```javascript
const account = {
    name: 'Andrew Mead',
    expenses: [],
    income: [],
    addExpense: function (description, amount) {
        this.expenses.push({
            description: description,
            amount: amount
        })
    },
    addIncome: function (description, amount) {
        this.income.push({
            description: description,
            amount: amount
        })
    },
    getAccountSummary: function () {
        let totalExpenses = 0
        let totalIncome = 0
        let accountBalance = 0

        this.expenses.forEach(function (expense) {
            totalExpenses = totalExpenses + expense.amount
        })

        this.income.forEach(function (income) {
            totalIncome = totalIncome + income.amount
        })

        accountBalance = totalIncome - totalExpenses

        return `${this.name} has a balance of $${accountBalance}. $${totalIncome} in income. $${totalExpenses} in expenses.`
    }
}

account.addExpense('Rent', 950)
account.addExpense('Coffee', 2)
account.addIncome('Job', 1000)
console.log(account.getAccountSummary())
```
