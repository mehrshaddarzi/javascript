## String Variable
```javascript
let city = 'Philadelphia'
let country = 'United States'
let location = city + ', ' + country

console.log(location)
```

## Number Variable
```javascript
let age = 26
let dogYears = (age + 1) / 7

console.log(dogYears)

// Challenge area

let studentScore = 41
let maxScore = 100
let percent = (studentScore / maxScore) * 100

console.log(percent)
```

## 3 points about Variable
```javascript
// 1. You can't define a variable more than once
let petName = 'Hal'

petName = 'Spot'

console.log(petName)

// 2. There are rules related to variable names
let test_ = 2
let result = 3 + 4

// 3. Variable names cannot be reserved keywords
// let let = 12
```

## Const Variable (nor Reassign)
```javascript
const person = {
    age: 27
}

person.age = 28
// person = {}

console.log(person)
```

## Typeof
```javascript
//get type of variable
//number / string / array / object

let g = typeof 123;
console.log(g); => number

if('5' == 5 ) //true
if('5' === 5) //false
```

### var vs let

Difference between var and let in JavaScript
var and let are both used for function declaration in javascript but the difference between them is that var is function scoped and let is block scoped.
It can be said that a variable declared with var is defined throughout the program as compared to let.
https://tylermcginnis.com/var-let-const/

## Operation

```javascript
// === - equality operator
// !== - no equal opeartor
// < - less than operator
// > - greater than opeartor
// <= - less than or equal to operator
// >= - greater than or equal to opeartor

let temp = 32
let isFreezing = temp <= 32

console.log(isFreezing)

// Challenge area

// Create age set to your age
let age = 65
// Calculate is child - if they are 7 or under
let isChild = age <= 7
// Calculate is senior - if they are 65 or older
let isSenior = age >= 65
// Print is child value
console.log(isChild)
// Print is senior value
console.log(isSenior)


if('5' == 5 ) //true
if('5' === 5) //false

```

## IF Statements
```java script

if (temp <= 32) {
    console.log('It is freezing outside!')
}

if (temp >= 110) {
    console.log('It is way to hot outside!')
}

// Challenge area

let age = 6

// If 7 or under print message about child pricing
if (age <= 7) {
    console.log('You will get a child discount!')
}

// If 65 or older print message about senior discount
if (age >= 65) {
    console.log('You will get a senior discount!')
}


let isAccountLocked = false
let userRole = 'user'

if (isAccountLocked) {
    console.log('Is account locked')
} else if (userRole === 'admin') {
    console.log('Welcome Admin')
} else {
    console.log('Welcome')
}

// Challenge area
let temp = 4

if (temp <= 32) {
    console.log('It is freezing outside')
} else if (temp >= 110) {
    console.log('It is hot outside')
} else {
    console.log('Go for it. It is pretty nice out')
}


let temp = 55

// Logical And Operator - True if both sides are true. False otherwise
// Logical Or Opeartor - True if at least one side is true. False otherwise

if (temp >= 60 && temp <= 90) {
    console.log('It is pretty nice out')
} else if (temp <= 0 || temp >= 120) {
    console.log('Do not go outside')
} else {
    console.log('Eh. Do what you want')
}

// Challenge area

let isGuestOneVegan = false
let isGuestTwoVegan = false

// Are both vegan? Only offer up vegan dishes.
// At least one vegan? Make sure to offer up some vegan options.
// Else, Offer up anything on the menue

if (isGuestOneVegan && isGuestTwoVegan) {
    console.log('Only offer up vegan dishes.')
} else if (isGuestOneVegan || isGuestTwoVegan) {
    console.log('Make sure to offer up some vegan options.')
} else {
    console.log('Offer up anything on the menu')
}
```

### Shorthand if
```javascript
// const myAge = 7
// const message = myAge >= 18 ? 'You can vote!' : 'You cannot vote.'
// console.log(message)

const myAge = 20
const showPage = () => {
    return 'Showing the page'
}
const showErrorPage = () => {
    return 'Showing the error page'
}
const message = myAge >= 21 ? showPage() : showErrorPage()
console.log(message)

const team = ['Tyler', 'Porter', 'Andrew', 'Ben', 'Mike']
console.log(team.length <= 4 ? `Team size: ${team.length}` : 'Too many people on your team')
```

### Truthy and falsy
```javascript

// Truthy - Values that resolve to true in boolean context
// Falsy - Values that resolve to false in boolean context
// Falsy values - false, 0, empty string, null, undefined, NaN

const products = [{ name: 'Computer mouse'}]
const product = products[0]

if (product) {
    console.log('Product found')
} else {
    console.log('Product not found')
}

if(v !==null)       => if(v)
if(x === undefined) => if(!x)
```

### undefinde and Null
```javascript
// Undefined for variable
let name

name = 'Jen'

if (name === undefined) {
    console.log('Please provide a name')
} else {
    console.log(name)
}

// Undefined for function arguments
// Undefined as function return default value
let square = function (num) {
    console.log(num)
}

let result = square()
console.log(result)

// Null as assined value
let age = 27

age = null

console.log(age)
```

## Scope varibale in javascript
```javascript
// Lexical Scope (Static Scope)
// Global Scope - Defined outside of all code blocks
// Local Scope - Defined inside a code block

// In a scope you can access variables defined in that scope, or in any parent/ancestor scope

// Global Scope (varOne)
  // Local Scope (varTwo)
    // Local Scope (varFour)
  // Local Scope (varThree)

let varOne = 'varOne'

if (true) {
    console.log(varOne)
    let varTwo = 'varTwo'
    console.log(varTwo)

    if (true) {
        let varFour = 'varFour'
    }
}

if (true) {
    let varThree = 'varThree'
}

console.log(varTwo)



// Global
  // Local
    // Local (name)
  // Local

///let name = 'Andrew'

if (true) {
    //let name = 'Mike'

    if (true) {
        let name = 'Jen'
        console.log(name)
    }
}

if (true) {
    console.log(name)
}
```
