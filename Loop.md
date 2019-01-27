#### Use for…of for array
```
let names = ['Gertrude', 'Henry', 'Melvin', 'Billy Bob'];
for (let animal of animals) {

  // Random name for our animal
  let nameIdx = Math.floor(Math.random() * names.length);
  console.log(`${names[nameIdx]} the ${animal}`);
}
```

#### Use for…in for object
```
let oldCar = {
  make: 'Toyota',
  model: 'Tercel',
  year: '1996'
};

for (let key in oldCar) {
  console.log(`${key} --> ${oldCar[key]}`);
}
```

#### For loop and ForEach
```
let summary_item = ["today", "yesterday", "week", "month", "year", "total"];
for (let i = 0; i < summary_item.length; i++) {
    ["visitors", "visits"].forEach(function (key) {
        app.fade('td[class=' + summary_item[i] + '--' + key + ']', data[summary_item[i]][key]);
    });
}
```

