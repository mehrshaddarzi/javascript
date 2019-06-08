## Request with XMLhttpRequest

> https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest

> https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState

> https://httpstatuses.com/

```javascript
// Making an HTTP request
const request = new XMLHttpRequest()

request.addEventListener('readystatechange', (e) => {
    if (e.target.readyState === 4 && e.target.status === 200) {
        const data = JSON.parse(e.target.responseText)
        console.log(data)
    } else if (e.target.readyState === 4) {
        console.log('An error has taken place')
    }
})

request.open('GET', 'http://puzzle.mead.io/puzzle?wordCount=3')
request.send()
```

### Example Get Country

```js
const countryCode = "MX"
const countryRequest = new XMLHttpRequest()

countryRequest.addEventListener('readystatechange', (e) => {
    if (e.target.readyState === 4 && e.target.status === 200) {
        const data = JSON.parse(e.target.responseText)
        const country = data.find((country) => country.alpha2Code === countryCode)
        console.log(country.name)
    } else if (e.target.readyStatet === 4) {
        console.log('Unable to fetch data')
    }
})

countryRequest.open('GET', 'http://restcountries.eu/rest/v2/all')
countryRequest.send()
```

## Callback function For Waiting

```js
const getPuzzle = (callback) => {
    const request = new XMLHttpRequest()

    request.addEventListener('readystatechange', (e) => {
        if (e.target.readyState === 4 && e.target.status === 200) {
            const data = JSON.parse(e.target.responseText)
            callback(undefined, data.puzzle)
        } else if (e.target.readyState === 4) {
            callback('An error has taken place', undefined)
        }
    })

    request.open('GET', 'http://puzzle.mead.io/puzzle?wordCount=3')
    request.send()
}

getPuzzle((error, puzzle) => {
    if (error) {
        console.log(`Error: ${error}`)
    } else {
        console.log(puzzle)
    }
})
```

## Promis

> https://www.datchley.name/es6-promises/

```js
const myPromise = new Promise((resolve, reject) => {
    if (Math.random() * 100 < 90) {
        console.log('resolving the promise ...');
        resolve('Hello, Promises!');
    }
    reject(new Error('In 10% of the cases, I fail. Miserably.'));
});

// Two functions 
const onResolved = (resolvedValue) => console.log(resolvedValue);
const onRejected = (error) => console.log(error);

myPromise.then(onResolved, onRejected);

// Same as above, written concisely
myPromise.then((resolvedValue) => {
    console.log(resolvedValue);
}, (error) => {
    console.log(error);
});

// Output (in 90% of the cases)

// resolving the promise ...
// Hello, Promises!
// Hello, Promises!


/* Example 2 */
const delay = (ms) => new Promise(
  (resolve) => setTimeout(resolve, ms)
);

delay(2000)
  .then(() => {
    console.log('Resolved after 2 seconds')
    return delay(1500);
  })
  .then(() => {
    console.log('Resolved after 1.5 seconds');
    return delay(3000);
  }).then(() => {
    console.log('Resolved after 3 seconds');
    throw new Error();
  }).catch(() => {
    console.log('Caught an error.');
  }).then(() => {
    console.log('Done.');
  });

// Resolved after 2 seconds
// Resolved after 1.5 seconds
// Resolved after 3 seconds
// Caught an error.
// Done.
```

### Request With Promis

```js
const getCountry = (countryCode) => new Promise((resolve, reject) => {
    const countryRequest = new XMLHttpRequest()

    countryRequest.addEventListener('readystatechange', (e) => {
        if (e.target.readyState === 4 && e.target.status === 200) {
            const data = JSON.parse(e.target.responseText)
            const country = data.find((country) => country.alpha2Code === countryCode)
            resolve(country)
        } else if (e.target.readyStatet === 4) {
            reject('Unable to fetch data')
        }
    })

    countryRequest.open('GET', 'http://restcountries.eu/rest/v2/all')
    countryRequest.send()
})

getCountry('MX').then((country) => {
    console.log(country.name)
}, (err) => {
    console.log(`Error: ${err}`)
})
```

## Fetch API

> https://stackoverflow.com/questions/29775797/fetch-post-json-data


```js
fetch('http://puzzle.mead.io/puzzle', {}).then((response) => {
     if (response.status === 200) {
         return response.json() 
     } else {
         throw new Error('Unable to fetch the puzzle')
     }
 }).then((data) => {
     console.log(data.puzzle)
 }).catch((error) => {
     console.log(error)
 })
 
 
 //Prepare Request Arg
let request = {
    method: type,
    mode: 'no-cors',
    redirect: 'follow',
    cache: 'no-cache'
};

request.headers = {
    'Content-Type': 'application/javascript',
    'X-WP-Nonce': wps_js.global.rest_api_nonce,
};

//Prepare Query String
let QueryString = Object.keys(params).reduce(function (str, key, i) {
    let delimiter, val;
    delimiter = (i === 0) ? '?' : '&';
    key = encodeURIComponent(key);
    val = encodeURIComponent(params[key]);
    return [str, delimiter, key, '=', val].join('');
}, '');

// Run
let inner_el = document.querySelector(wps_js.meta_box_inner(params.name));
fetch(url + QueryString, request)
    .then(data => data.json())
    .then(data => {

    })
    .catch(xhr => {
      inner_el.innerHTML = wps_js[error_callback](xhr.statusText);
    });
};
```

## Country API with Fetch

```js
const getCountry = (countryCode) => {
    return fetch('http://restcountries.eu/rest/v2/all').then((response) => {
        if (response.status === 200) {
            return response.json()
        } else {
            throw new Error('Unable to fetch data')
        }
    }).then((data) => {
        return data.find((country) => country.alpha2Code === countryCode)
    })
}


getCountry('US').then((country) => {
    console.log(country.name)
}).catch((err) => {
    console.log(`Error: ${err}`)
})
```

## Async/Await
```js
const getCountry = async (countryCode) => {
    const response = await fetch('http://restcountries.eu/rest/v2/all')

    if (response.status === 200) {
        const data = await response.json()
        return data.find((country) => country.alpha2Code === countryCode)
    } else {
        throw new Error('Unable to fetch the country')
    }
}

const getCurrentCountry = async () => {
    const location = await getLocation()
    return getCountry(location.country)
}

getPuzzle('2').then((puzzle) => {
    console.log(puzzle)
}).catch((err) => {
    console.log(`Error: ${err}`)
})

getCurrentCountry().then((country) => {
    console.log(country.name)
}).catch((error) => {
    console.log(error)
})
```
