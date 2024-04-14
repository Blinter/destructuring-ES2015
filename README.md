# Destructuring Exercise

### Object Destructuring 1
What does the following code return/print?
```javascript
let facts = {numPlanets: 8, yearNeptuneDiscovered: 1846};
let {numPlanets, yearNeptuneDiscovered} = facts;

console.log(numPlanets); // ?
console.log(yearNeptuneDiscovered); // ?
```
+ console.log(numPlanets);
    - returns `8`
+ console.log(yearNeptuneDiscovered);
    - returns `1846`
---
### Object Destructuring 2
What does the following code return/print?
```javascript
let planetFacts = {
  numPlanets: 8,
  yearNeptuneDiscovered: 1846,
  yearMarsDiscovered: 1659
};

let {numPlanets, ...discoveryYears} = planetFacts;

console.log(discoveryYears); // ?
```
+ console.log(discoveryYears);
    - returns `{ yearNeptuneDiscovered: 1846, yearMarsDiscovered: 1659 }`
---
### Object Destructuring 3

What does the following code return/print?
```javascript
function getUserData({firstName, favoriteColor="green"}){
  return `Your name is ${firstName} and you like ${favoriteColor}`;
}

getUserData({firstName: "Alejandro", favoriteColor: "purple"}) // ?
getUserData({firstName: "Melissa"}) // ?
getUserData({}) // ?
```
+ getUserData({firstName: "Alejandro", favoriteColor: "purple"})
    - returns `Your name is Alejandro and you like purple`
+ getUserData({firstName: "Melissa"})
    - returns `Your name is Melissa and you like green`
+ getUserData({})
    - returns `Your name is undefined and you like green`
---
### Array Destructuring 1
What does the following code return/print?
```javascript
let [first, second, third] = ["Maya", "Marisa", "Chi"];

console.log(first); // ?
console.log(second); // ?
console.log(third); // ?
```
+ console.log(first);
    - returns `Maya`
+ console.log(second);
    - returns `Marisa`
+ console.log(third);
    - returns `Chi`
---
### Array Destructuring 2
What does the following code return/print?
```javascript
let [raindrops, whiskers, ...aFewOfMyFavoriteThings] = [
  "Raindrops on roses",
  "whiskers on kittens",
  "Bright copper kettles",
  "warm woolen mittens",
  "Brown paper packages tied up with strings"
]

console.log(raindrops); // ?
console.log(whiskers); // ?
console.log(aFewOfMyFavoriteThings); // ?
```
+ console.log(raindrops);
    - returns `Raindrops on roses`
+ console.log(whiskers);
    - returns `whiskers on kittens`
+ console.log(aFewOfMyFavoriteThings);
    - returns `["Bright copper kettles", "warm woolen mittens", "Brown paper packages tied up with strings"]`
---
### Array Destructuring 3
What does the following code return/print?
```javascript
let numbers = [10, 20, 30];
[numbers[1], numbers[2]] = [numbers[2], numbers[1]]

console.log(numbers) // ?
```
+ console.log(numbers)
    - returns `[10, 30, 20]`
---
# ES2015 Refactoring
In this exercise, you’ll refactor some ES5 code into ES2015.
### ES5 Assigning Variables to Object Properties
```javascript
var obj = {
  numbers: {
    a: 1,
    b: 2
  }
};

var a = obj.numbers.a;
var b = obj.numbers.b;
```
### ES2015 Object Destructuring
```javascript
/* Write an ES2015 Version */
let obj = { numbers: { a: 1, b: 2 } };
const { numbers: { a, b } } = obj;
```
---
### ES5 Array Swap
```javascript
var arr = [1, 2];
var temp = arr[0];
arr[0] = arr[1];
arr[1] = temp;
```
### ES2015 One-Line Array Swap with Destructuring
```javascript
/* Write an ES2015 Version */
let arr = [1, 2];
[arr[0],arr[1]] = [arr[1],arr[0]];
```
---
### raceResults()
Write a function called ***raceResults*** which accepts a single array argument. It should return an object with the keys ***first***, ***second***, ***third***, and ***rest***.
+ first: the first element in the array
+ second: the second element in the array
+ third: the third element in the array
+ rest: all other elements in the array

Write a ***one line*** function to make this work using
- An arrow function
- Destructuring
- `Enhanced` object assignment (same key/value shortcut)
```javascript
raceResults(['Tom', 'Margaret', 'Allison', 'David', 'Pierre'])

/*
  {
    first: "Tom",
    second: "Margaret",
    third: "Allison",
    rest: ["David", "Pierre"]
  }
*/
```

```javascript
const raceResults = ([first, second, third, ...rest]) => ({first, second, third, rest});
```
raceResults(['Tom', 'Margaret', 'Allison', 'David', 'Pierre'])