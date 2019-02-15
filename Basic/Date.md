## Get now
```javascript

// Set variable to current date and time
const now = new Date();

// View the output
now;

now.toString();
//Wed Oct 18 2017 12:41:34 GMT+0000 (UTC)


Day of the Week	Month	Day	Year	Hour	Minute	Second	Timezone
Wed	Oct	18	2017	12	41	34	GMT+0000 (UTC)

// Get the current timestamp
now.getTime();
//1508330494000

// Date/Time	Method	Range	Example
Year	getFullYear()	YYYY	1970
Month	getMonth()	0-11	0 = January
Day (of the month)	getDate()	1-31	1 = 1st of the month
Day (of the week)	getDay()	0-6	0 = Sunday
Hour	getHours()	0-23	0 = midnight
Minute	getMinutes()	0-59	
Second	getSeconds()	0-59	
Millisecond	getMilliseconds()	0-999	
Timestamp	getTime()	Milliseconds since Epoch time	


// Initialize a new birthday instance
const birthday = new Date(1980, 6, 31);


// Get today's date
const today = new Date();

// Compare today with October 3rd
if (today.getDate() === 3 && today.getMonth() === 9) {
  console.log("It's October 3rd.");
} else {
  console.log("It's not October 3rd.");
}

```

> https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date
> https://www.digitalocean.com/community/tutorials/understanding-date-and-time-in-javascript

### Moment js
```javascript
// const now = moment()
// now.subtract(1, 'week').subtract(20, 'days')
// console.log(now.format('MMMM Do, YYYY'))
// console.log(now.fromNow())
// const nowTimestamp = now.valueOf()

// console.log(moment(nowTimestamp).toString())

// 1. Create a new moment
// 2. Set the month, day, and year to your birthday
// 3. Use format to print it in the following way: Jan 6, 1991

const birthday = moment()
birthday.year(1991).month(0).date(6)
console.log(birthday.format('MMM D, YYYY'))


//Get current timestamp
so:

moment(...).valueOf()
to parse a preexisting date and convert the representation to a unix timestamp
or

let now_timestamp = moment().valueOf()
//for the current unix timestamp

//calculate To now
moment(now_timestamp).fromNow(); //25 minute


```

