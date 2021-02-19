



### ES6: Create a Module Script
```html
<script type="module" src="filename.js"></script>
```
### ES6: Use export to Share a Code Block
```javascript
export const add = (x, y) => {
  return x + y;
}
/* --- */
const add = (x, y) => {
  return x + y;
}

export { add };
```
```javascript
const uppercaseString = (string) => {
  return string.toUpperCase();
}

const lowercaseString = (string) => {
  return string.toLowerCase()
}

export {uppercaseString, lowercaseString}
```
### ES6: Reuse JavaScript Code Using import
```javascript
import { add, subtract } from './math_functions.js';
```
### ES6: Use * to Import Everything from a File
```javascript
import * as stringFunctions from './string_functions.js';

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```
### ES6: Create an Export Fallback with export default
```javascript
// named function
export default function add(x, y) {
  return x + y;
}

// anonymous function
export default function(x, y) {
  return x + y;
}
```
### ES6: Import a Default Export
```javascript
import add from "./math_functions.js";
```
### ES6: Create a JavaScript Promise
A promise has three states: pending, fulfilled, and rejected.
```javascript
const myPromise = new Promise((resolve, reject) => {

});
```
### ES6: Complete a Promise with resolve and reject
```javascript
const myPromise = new Promise((resolve, reject) => {
  if(condition here) {
    resolve("Promise was fulfilled");
  } else {
    reject("Promise was rejected");
  }
});
```
### ES6: Handle a Fulfilled Promise with then
```javascript
myPromise.then(result => {
  // do something with the result.
});
```
```javascript
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to true to represent a successful response from a server
  let responseFromServer = true;
    
  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});
/* --- */
makeServerRequest.then(result => {
  console.log(result);
});
```
### ES6: Handle a Rejected Promise with catch
```javascript
myPromise.catch(error => {
  // do something with the error.
});
```

### Regular Expressions: Using the Test Method
```javascript
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr); // Returns true
```
### Regular Expressions: Match Literal Strings
```javascript
let testStr = "Hello, my name is Kevin.";
let testRegex = /Kevin/;
testRegex.test(testStr); // Returns true
/* --- */
let wrongRegex = /kevin/;
wrongRegex.test(testStr); // Returns false
```
### Regular Expressions: Match a Literal String with Different Possibilities
```javascript
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/;
let result = petRegex.test(petString);
```
### Regular Expressions: Ignore Case While Matching
```javascript
let myString = "freeCodeCamp";
let fccRegex = /freeCodeCamp/i;
let result = fccRegex.test(myString);
```
### Regular Expressions: Extract Matches
```javascript
"Hello, World!".match(/Hello/); // Returns ["Hello"]
let ourStr = "Regular expressions";
let ourRegex = /expressions/;
ourStr.match(ourRegex); // Returns ["expressions"]
/* --- */
'string'.match(/regex/);
/regex/.test('string');
/* --- */
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/;
let result = extractStr.match(/coding/);
```
### Regular Expressions: Find More Than the First Match
```javascript
let testStr = "Repeat, Repeat, Repeat";
let ourRegex = /Repeat/;
testStr.match(ourRegex); // Returns ["Repeat"]
/* --- */
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex); // Returns ["Repeat", "Repeat", "Repeat"]
/* --- */
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /Twinkle/gi; // g-> repet words  and i -> no case sensitive
let result = twinkleStar.match(starRegex);
```
### Regular Expressions: Match Anything with Wildcard Period
```javascript
let humStr = "I'll hum a song";
let hugStr = "Bear hug";
let huRegex = /hu./;
huRegex.test(humStr); // Returns true
huRegex.test(hugStr); // Returns true
```
# Regular Expressions: Match Single Character with Multiple Possibilities
```javascript
let bigStr = "big";
let bagStr = "bag";
let bugStr = "bug";
let bogStr = "bog";
let bgRegex = /b[aiu]g/;
bigStr.match(bgRegex); // Returns ["big"]
bagStr.match(bgRegex); // Returns ["bag"]
bugStr.match(bgRegex); // Returns ["bug"]
bogStr.match(bgRegex); // Returns null
```
### Regular Expressions: Match Letters of the Alphabet
```javascript
let catStr = "cat";
let batStr = "bat";
let matStr = "mat";
let bgRegex = /[a-e]at/;
catStr.match(bgRegex); // Returns ["cat"]
batStr.match(bgRegex); // Returns ["bat"]
matStr.match(bgRegex); // Returns null
```
### Regular Expressions: Match Numbers and Letters of the Alphabet
```javascript
let jennyStr = "Jenny8675309";
let myRegex = /[a-z0-9]/ig;
// matches all letters and numbers in jennyStr
jennyStr.match(myRegex);
```
### Regular Expressions: Match Single Characters Not Specified
```javascript
let quoteSample = "3 blind mice.";
let myRegex = /[^aeiou0-9]/gi;
let result = quoteSample.match(myRegex);
```
## Regular Expressions: Match Characters that Occur One or More Times
```javascript
let difficultSpelling = "Mississippi";
let myRegex = /s+/g;
let result = difficultSpelling.match(myRegex);
console.log(result);
```
### Regular Expressions: Match Characters that Occur Zero or More Times
```javascript
let soccerWord = "gooooooooal!";
let gPhrase = "gut feeling";
let oPhrase = "over the moon";
let goRegex = /go*/;
soccerWord.match(goRegex); // Returns ["goooooooo"]
gPhrase.match(goRegex); // Returns ["g"]
oPhrase.match(goRegex); // Returns null
```
### Regular Expressions: Find Characters with Lazy Matching
```javascript
let text = "<h1>Winter is coming</h1>";
let myRegex = /<.*?>/;
let result = text.match(myRegex);
```
### Regular Expressions: Match Ending String Patterns
```javascript
let theEnding = "This is a never ending story";
let storyRegex = /story$/;
storyRegex.test(theEnding); // Returns true
let noEnding = "Sometimes a story will have to end";
storyRegex.test(noEnding); // Returns false
```
### Regular Expressions: Match All Letters and Numbers
```javascript
let longHand = /[A-Za-z0-9_]+/;
let shortHand = /\w+/;
let numbers = "42";
let varNames = "important_var";
longHand.test(numbers); // Returns true
shortHand.test(numbers); // Returns true
longHand.test(varNames); // Returns true
shortHand.test(varNames); // Returns true
```
### Regular Expressions: Match Everything But Letters and Numbers
```javascript
let shortHand = /\W/;
let numbers = "42%";
let sentence = "Coding!";
numbers.match(shortHand); // Returns ["%"]
sentence.match(shortHand); // Returns ["!"]
```
### Regular Expressions: Match All Numbers
```javascript
let movieName = "2001: A Space Odyssey";
let numRegex = /\d/g;
let result = movieName.match(numRegex).length;
```
### Regular Expressions: Match All Non-Numbers
```javascript
let movieName = "2001: A Space Odyssey";
let noNumRegex = /\D/g; // same ->    [^0-9]
let result = movieName.match(noNumRegex).length;
```

```javascript
// 1) Usernames can only use alpha-numeric characters.

//2) The only numbers in the username have to be at the end. There can be zero or more of them at the end. Username cannot start with the number.

// 3) Username letters can be lowercase and uppercase.

// 4) Usernames have to be at least two characters long. A two-character username can only use alphabet letters as characters.
let username = "JackOfAllTrades";
let userCheck = /^[a-z]([0-9][0-9]+|[a-z]+\d*)$/i;
// ^ - start of input
// [a-z] - first character is a letter
// [0-9][0-9]+ - ends with two or more numbers
// | - or
// [a-z]+ - has one or more letters next
// \d* - and ends with zero or more numbers
// $ - end of input
// i - ignore case of input
// or const userCheck = /^[a-z]([0-9]{2,}|[a-z]+\d*)$/i;
// ^ - start of input
// [a-z] - first character is a letter
// [0-9]{2,0} - ends with two or more numbers
// | - or
// [a-z]+ - has one or more letters next
// \d* - and ends with zero or more numbers
// $ - end of input
// i - ignore case of input
let result = userCheck.test(username);
```
### Regular Expressions: Match Whitespace
```javascript
let whiteSpace = "Whitespace. Whitespace everywhere!"
let spaceRegex = /\s/g; // like ->   [ \r\t\f\n\v]
whiteSpace.match(spaceRegex); // Returns [" ", " "]
```
### Regular Expressions: Match Non-Whitespace Characters
```javascript
let whiteSpace = "Whitespace. Whitespace everywhere!"
let nonSpaceRegex = /\S/g;
whiteSpace.match(nonSpaceRegex).length; // Returns 32
```
### Regular Expressions: Specify Upper and Lower Number of Matches
```javascript
let A4 = "aaaah";
let A2 = "aah";
let multipleA = /a{3,5}h/; 
// /a{3,}h/ la "a" al menos 3 veces
// /a{,5}h/ la "a" como maximo 5 veces
multipleA.test(A4); // Returns true
multipleA.test(A2); // Returns false
```
### Regular Expressions: Specify Exact Number of Matches
```javascript
let A4 = "haaaah";
let A3 = "haaah";
let A100 = "h" + "a".repeat(100) + "h";
let multipleHA = /ha{3}h/;
multipleHA.test(A4); // Returns false
multipleHA.test(A3); // Returns true
multipleHA.test(A100); // Returns false
```
### Regular Expressions: Check for All or None
```javascript
let american = "color";
let british = "colour";
let rainbowRegex= /colou?r/;
rainbowRegex.test(american); // Returns true
rainbowRegex.test(british); // Returns true
```
### Regular Expressions: Positive and Negative Lookahead
```javascript
let quit = "qu";
let noquit = "qt";
let quRegex= /q(?=u)/;
let qRegex = /q(?!u)/;
quit.match(quRegex); // Returns ["q"]
noquit.match(qRegex); // Returns ["q"]
/* --- */
// looks for between 3 and 6 characters and at least one number
let password = "abc123";
let checkPass = /(?=\w{3,6})(?=\D*\d)/;
checkPass.test(password); // Returns true
```
### Regular Expressions: Check For Mixed Grouping of CharactersPassed
```javascript
let testStr = "Pumpkin";
let testRegex = /P(engu|umpk)in/;
testRegex.test(testStr); // Returns true
```
### Regular Expressions: Reuse Patterns Using Capture Groups
```javascript
let repeatStr = "regex regex";
let repeatRegex = /(\w+)\s\1/;
repeatRegex.test(repeatStr); // Returns true
repeatStr.match(repeatRegex); // Returns ["regex regex", "regex"]
```
```javascript

```
```javascript

```


```javascript

```

```javascript

```
```javascript

```
```javascript

```


```javascript

```

```javascript

```
```javascript

```
```javascript

```


```javascript

```

```javascript

```
```javascript
if ('geolocation' in navigator) {
    navigator.geolocation.getCurrentPosition(position => {
        const lat = position.coords.latitude;
        const lon = position.coords.longitude;
        console.log(position);
    })
} else {
    console.log('geolocation not available');
}
```      
      
      // ayuda memoria ARRAYs JS

        console.log(['a', 'b'].concat(['c'])); // ['a', 'b', 'c']
        console.log(['a', 'b'].join('-')); // 'a-b'
        console.log(['a', 'b', 'c'].slice(1)); // ['b', 'c']
        console.log(['a', 'b', 'b'].indexOf('b')); // 1
        console.log(['a', 'b', 'b'].lastIndexOf('b')); // 2

        ['a', 'b', 'c'].forEach(x => console.log(x)) // a, b, c

        console.log([1, 2, 3].every(x => x < 10)); // true
        console.log([1, 2, 3].some(x => x < 2)); // true
        console.log([1, 2, 3].filter(x => x < 2)); // [1]

        console.log([1, 2, 3].map(x => x * 2)); // [2, 4, 6]
        console.log([1, 2, 3].reduce((x, y) => x * y)); // 6
        console.log([1, 20, 3].sort()); // [1, 20, 3]
        console.log([20, 5, 3].sort()); // [20, 3, 5]
        console.log([1, 2, 3].reverse()); //[3, 2, 1]
        console.log([1, 2, 3].length) // 3





















-------------------------
1.comments
// ...

/*
...
*/

2. variables

undefined, null, boolean, string, symbol, bigint, number, object

NaN -> Not a Number

Escape Sequences

\'	single quote
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	word boundary
\f	form feed

.push() -> add element at the end of an array
.unshift() -> add element at the start of an array
.pop() -> always removes the last element of an array
.shift() -> removes the first element of an arrar

OBJECT {
	property: value
}
-- Accessing Object Properties with Variables
var testObj = {
  12: "Namath",
  16: "Montana",
  19: "Unitas"
};


function propNumber(num){
	return num;
}
var playerNumber = propNumber(16); 
var player = testObj[playerNumber];
---



function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5)); // [ 1, 2, 3, 4, 5 ]


-----------------------


console.log('program start');

setTimeout(function() {
	console.log('first function');
}, 3000)
setTimeout(function() {
	console.log('second function');
}, 2000)
setTimeout(function() {
	console.log('third function');
}, 1000)

console.log('program end');

// output:
// program start
// program end
// third function
// second function
// first function

var a = 1
if(true){
	var a = 2
	console.log(a);
}
console.log(a);
// output:
// 2 (inside the if)
// 2 (outside the if)


let a = 1
if(true){
	let a = 2
	console.log(a);
}
console.log(a);
// output:
// 2 (inside the if)
// 1 (outside the if)

-------------------------

