## basic Structure
```javascript
// Function - input (argument), code, output (return value)

let greetUser = function () {
    console.log('Welcome user!')
}

greetUser()
greetUser()
greetUser()

let square = function (num) {
    let result = num * num
    return result
}

let value = square(3)
let otherValue = square(10)

console.log(value)
console.log(otherValue)

// Challenge Area

let convertFahrenheitToCelsius = function (fahrenheit) {
    let celsius = (fahrenheit - 32) * 5 / 9
    return celsius
}

let tempOne = convertFahrenheitToCelsius(32)
let tempTwo = convertFahrenheitToCelsius(68)

console.log(tempOne)
console.log(tempTwo)
```

## Argument
```javascript
// Multiple arguments
let add = function (a, b, c) {
    return a + b + c
}

let result = add(10, 1, 5)
console.log(result)

// Deafult arguments
let getScoreText = function (name = 'Anonymous', score = 0) {
    return 'Name: ' + name + ' - Score: ' + score
}

let scoreText = getScoreText(undefined, 99)
console.log(scoreText)

// Challenge area
let getTip = function (total, tipPercent = .2) {
    return total * tipPercent
}

let tip = getTip(40, .25)
console.log(tip)
```

## function Scope
```javascript
// Global scope (convertFahrenheitToCelsius, tempOne, tempTwo)
  // Local scope (fahrenheit, celsius)
    // Local scope (isFreezing)

let convertFahrenheitToCelsius = function (fahrenheit) {
    let celsius = (fahrenheit - 32) * 5 / 9

    if (celsius <= 0) {
        let isFreezing = true
    }

    return celsius
}

let tempOne = convertFahrenheitToCelsius(32)
let tempTwo = convertFahrenheitToCelsius(68)

console.log(tempOne)
console.log(tempTwo)
```

## Template String
```javascript
// Challenge area
// A 25% tip on $40 would be $10
let getTip = function (total, tipPercent = .2) {
    let percent = tipPercent * 100
    let tip = total * tipPercent
    return `A ${percent}% tip on $${total} would be $${tip}`
}
```

### Example Function
```javascript
// students score, total possible score
// 15/20 -> You got a C (75%)!
// A 90-100, B 80-89, C 70-79, D 60-69, F 0-59

let gradeCalc = function (score, totalScore) {
    let percent = (score / totalScore) * 100
    let letterGrade = ''

    if (percent >= 90) {
        letterGrade = 'A'
    } else if (percent >= 80) {
        letterGrade = 'B'
    } else if (percent >= 70) {
        letterGrade = 'C'
    } else if (percent >= 60) {
        letterGrade = 'D'
    } else {
        letterGrade = 'F'
    }

    return `You got a ${letterGrade} (${percent}%)!`
}

let result = gradeCalc(9, 20)
console.log(result)
```

### Check exist Function
```javascript
Try something like this:

if (typeof me.onChange !== "undefined") { 
    // safe to use the function
}
or better yet (as per UpTheCreek upvoted comment)

if (typeof me.onChange === "function") { 
    // safe to use the function
}


function abc(){
}
!!window.abc; // return true
!!window.abcd; // return false
```

### es6 arrow function
```javascript

const squareLong = function(num) {
    return num * num
}

const squareLong = (num) => {
    return num * num
}

//if only return we can remove brace
const square = (num) => num * num

console.log(square(5))

const people = [{
    name: 'Andrew',
    age: 27
}, {
    name: 'Vikram',
    age: 31
}, {
    name: 'Jess',
    age: 22
}]

// const under30 = people.filter(function (person) {
//     return person.age < 30
// })

const under30 = people.filter((person) => person.age < 30)
console.log(under30)

const person = people.find((person) => person.age === 22)
console.log(person.name)
```

### Get argument in function
```javascript

const add = function() {
    //return arguments[0] + arguments[1]
    console.log( arguments );
}
console.log(add(11, 22, 33, 44))
```
دو تفاوت حالت اصلی با خلاصه :
در حالت خلاصه ما مانند مثال بالا نمیتوانیم به آرگومان های آزاد دسترسی پیداکنیم
2. در شی گرایی در حالت خلاصه ما نمتواینم به this دسترسی داشته باشیم
و باید از مورد پایینی اصتفاده شود :

```javascript
const car = {
    color: 'Red',
    getSummary() {
        return `The car is ${this.color}`
    }
}
console.log(car.getSummary())
```

### Try Catch
``` javascript
const getTip = (amount) => {
    if (typeof amount === 'number') {
        return amount * .25
    } else {
        throw Error('Argument must be a number')
    }
}

try {
    const result = getTip(10)
    console.log(result)
} catch (e) {
    console.log('catch block is running')
}

```
