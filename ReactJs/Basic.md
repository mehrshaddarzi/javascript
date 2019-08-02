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
