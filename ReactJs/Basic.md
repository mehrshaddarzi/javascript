### Basic Example

```javascript
function Person(props) {
  return (
    <div className="person">
      <h1>{props.name}</h1>
      <p>Your Age: {props.age}</p>
    </div>
  );
}

var app = (
  <div>
     <Person name="Max" age="28" />
      <Person name="Manu" age="29" />
  </div>
);

ReactDOM.render(app, document.querySelector('#app'));
```


### Arrow Function

```javascript
const Print = name => {
  return name;
}

const Print = () => {
  return 23;
}

const Print = (v1, v2) => {
  return v1 * v2;
}

// If One Line
const Print = (v1, v2) => return v1 * v2;
```


### Import and Export

<img src="https://raw.githubusercontent.com/mehrshaddarzi/javascript/master/ReactJs/Images/export-import-1.jpg">
<img src="https://raw.githubusercontent.com/mehrshaddarzi/javascript/master/ReactJs/Images/export-import-2.jpg">


### Class

```javascript
class Person {
    constructor () {
        this.name = 'Max';
    }
    
    printMyName() {
        console.log(this.name); // this is required to refer to the class!
    }
}

const person = new Person();
console.log(person.name); // prints 'Max'
```

<img src="https://raw.githubusercontent.com/mehrshaddarzi/javascript/master/ReactJs/Images/class-1.JPG">
<img src="https://raw.githubusercontent.com/mehrshaddarzi/javascript/master/ReactJs/Images/class-2-es7.JPG">
<img src="https://raw.githubusercontent.com/mehrshaddarzi/javascript/master/ReactJs/Images/class-3-es5.JPG">


### Spread Array

```javascript
const Number = [1,2,3]
const NewNumbers = [...Number, 4]; //[1,2,3,4]
const NewNumbers = [Number, 4]; //[[1,2,3],4]


const oldObject = {
    name: 'Max'
};
const newObject = {
    ...oldObject,
    age: 28
};

newObject  would then be
{
    name: 'Max',
    age: 28
}

// Use in function
const filter = (...args) => {
  return args.filter(el => el ===1);
}
filter(1,2,8,3,6); //[1]
```

### Destructuring Array

```javascript
const array = [1, 2, 3];
const [a, b] = array;
console.log(a); // prints 1
console.log(b); // prints 2
console.log(array); // prints [1, 2, 3]

const myObj = {
    name: 'Max',
    age: 28
}
const {name} = myObj;
console.log(name); // prints 'Max'
console.log(age); // prints undefined
console.log(myObj); // prints {name: 'Max', age: 28}
```

### Arrow Function Helper

Particularly important in this course are:
map()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
find()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find
findIndex()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex
filter()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
reduce()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b
concat()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b
slice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice
splice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice
