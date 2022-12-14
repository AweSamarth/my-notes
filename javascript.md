# JavaScript Notes

- onclick

```jsx
<button id="increment-btn" onclick="increment()">INCREMENT</button>
//here increment is a function
```

- var and let are both used for variable declaration in javascript but the difference between them is that **var is function scoped and let is block scope**. It can be said that a variable declared with var is defined throughout the program as compared to let. var can be re-declared. let can be updated but not re-declared
- const is also used for variable declaration. It can neither be updater nor be re-declared

```solidity
function newFunction() {
        var hello = "hello";
    }
console.log(hello); // error: hello is not defined
```

```solidity
var greeter = "hey hi";
    var times = 4;

    if (times > 3) {
        var greeter = "say Hello instead"; 
    }
    
    console.log(greeter) // "say Hello instead"
```

```jsx
let greeting = "say Hi";
   let times = 4;

   if (times > 3) {
        let hello = "say Hello instead";
        console.log(hello);// "say Hello instead"
    }
   console.log(hello) // hello is not defined
//so let is block scoped
```

- Textcontent gives the content that is rendered out and is visible to the user and innerText gives everything contained by the element including the tags. (doubt here)
- One more way to get elements:

```jsx
document.querySelector("#sum-el")
//it is more dynamic
//here we are getting from the css file
```

- We can store multiple data types in JavaScript arrays 🤯
- Math is an in-built object in JS
- Math.random() to get a random float between 0 and 1 (not inclusive of 1). We can manipulate to change the range. However these aren’t truly random

```jsx
Math.random()
//will return between 0 and 1 (not inclusive of 1)

Math.random()*6
//will return between 0 and 6 (not iclusive of 5)
```

- Math.floor() for returning an integer by completely ignoring the digits at the decimal places

```jsx
math.floor(4.5)
math.floor(4.51)
math.floor(4.4)
//will return 4

```

- Logical Operators:
    1. and: &&
    2. or: ||

- Objects in JavaScript

```jsx
let player={
name: "Sam",
age: 18,
huh: "huh"
}
//to access age we will use player.age
```

- Functions in objects are called methods

```jsx
let player = {
    name: "Per",
    chips: 200,
    sayHello: function() {
        console.log("Heisann!")
    }
}
player.sayHello()
	//output will be "Heisann!"
```

- In arrays:
    - push(): for adding something to the end of an array
    - pop(): for removing the last element of an array
    - unshift(): for adding something to the start of an array
    - shift(): for deleting the first element of an array

- Instead of doing onclick=”functionname()”  in the html, we can use addEventListener in js and define the function there itself

```html
<input type="text" id="input-el">
        <button id="input-btn">SAVE INPUT</button>
        <script src="index.js"></script>
```

```jsx
let inputBtn = document.getElementById("input-btn")

inputBtn.addEventListener("click", function() {
    console.log("Button clicked from addEventListener")
})
```

- In modern JS, both let and const are used. If possible use const, else use let
- We use backtick (` ) for using multilline strings with variables (template strings) in JS
- We use the notation ${ } for escaping html and using js variables in html expressions

```jsx
function renderLeads() {
    let listItems = ""
    for (let i = 0; i < myLeads.length; i++) {
     // listItems += "<li><a target='_blank' href='" + myLeads[i] + "'>" + myLeads[i] + "</a></li>"
        listItems += `
            <li>
                <a target='_blank' href='${myLeads[i]}'>
                    ${myLeads[i]}</a>
            </li>
    `
    }
    ulEl.innerHTML = listItems
// ${} is a life-saver because it allows us to avoid the hassle-some process of using + "" after every variable
//It also allows us to write multi-line html in js, like we would write in an html file
```

- For making data persist even after refreshing, we store it in the local storage of the browser. localStorage variable is pre-defined in the global scope.

```jsx
localStorage.setItem(key, value)
//for storing something in the local storage

localStorage.getItem(key)
//for retrieving 

localStorage.clear()
//self-explanatory

//both key and value need to be strings. It is a limitation of localStorage
//for escaping this problem we use JSON.stringify(something) while setting and 
//JSON.parse(somethingelse) while getting

```

- null keyword is used by developers to signify that the variable in question does not contain anything. undefined keyword is used by the system, ie JavaScript to signify that the variable does not have a value
- The difference between arguments and parameters can be simply explained by this example”

```jsx
function add (a,b){ // here a and b are parameters
return a+b
}
add(2,3)
//here 2 and 3 are arguments
```

- Try to minimize the number of times you manipulate the DOM. A possible solution depending on the use case of course may be making a variable as an empty string and concatenating whatever manipulations we want to make there. Then finally we can make a single statement for making all the changes to the DOM

## Object Destructuring

Earlier, for storing object properties in variables, we used to make as many const statements as the number of properties required. But this is very lengthy and we can simplify this process by using object destructuring

```jsx
const dreamHoliday = {
    destination: 'Austin, Texas',
    activity: 'visit the Tesla HQ',
    accommodation: 'luxury ranch',
    companion: 'Elon Musk'
}

const {destination, activity, accommodation, companion} = dreamHoliday

console.log(`I would love to go to ${destination} to ${activity}. 
     I'd sleep in a ${accommodation} and hang out with ${companion} all day.`)

//this will log out:
// I would love to go to Austin, Texas to visit the Tesla HQ. I'd sleep in a luxury ranch
// and hang out with Elon Musk all day.
```

- For iterating over arrays, .map method is preferred over ‘for’ loops because it is a quicker and cleaner method. It creates a new array.

```jsx
const energyCostEuros = [140, 153, 164, 153, 128, 146]
const exchangeRate = 1.13

// const energyCostDollars = []

const energyCostDollars = energyCostEuros.map(function(euroCost){
    console.log(euroCost * exchangeRate)
})
//this will log out:
/*
140
153
164
153
128
146
*/

```

- For creating strings from arrays, we use .join(). It **returns a new string**. Let’s you choose how the elements are separated.

```jsx
const cssClassesArray = ['btn', 'btn-primary', 'btn-active', 'btn-sidebar']

const cssClassesString = cssClassesArray.join('')
```

- Functions can return functions as well

```jsx
function getLottoNumbers(){
    const winningNums = []
    for (let i = 0; i < 6; i++){
        winningNums.push(Math.round(Math.random()*100))
    }
    return winningNums
}

function getWinningNumbersHtml(){
    return getLottoNumbers().map(function(num){
        return `<div class="number">${num}</div>`
    })
}
```

- For creating a new array of x elements where all are undefined, we use `new Array(x)`

```jsx
const endOfLevelBosses = new Array(2)

console.log(endOfLevelBosses)
//this will log out 
[undefined, undefined]
```

- .fill() : in-built method for filling arrays. It converts the elements in an array to a provided static value

```jsx
const mushrooms = new Array(1000).fill('🍄')
console.log(mushrooms)

//will log out 1000 mushrooms
```

- fill, map and join can be chained without hassle

- Constructor functions allow us to produce similar types of objects as and when needed. Conventionally the name of the function constructor starts with a capital letter

```jsx
function Animal(){
     this.species = 'tiger'
     this.weightKg = 56
     this.age = 2
 }
 
 const animal1 = new Animal
 
 console.log(animal1.weightKg)

//will log out 56
// notice the new keyword
```

- **In JavaScript, functions are objects**
- When we use ‘this’ in a constructor function, it refers to the new instance of the object that we are creating. ‘this’ is an object.

- **Methods** are properties on objects that contain functions.

```jsx
function Animal(data){
    this.name = data.name
    this.species = data.species
    this.weightKg = data.weightKg
    this.age = data.age
    this.dateOfRelease = data.dateOfRelease
	this.summariseAnimal = function(){
		console.log(`${this.name} is a ${this.age} year old 
		${this.species} which weighs ${this.weightKg}kg and was 
		released into the wild on ${this.dateOfRelease}`)
	}
}

//here, summariseAnimal is a method

const newnimal = new Animal(objectname)
newnimal.summariseAnimal()
//because it is a functioon we use ()
```

- Object.assign copies properties from a source object to a target object and returns the new version of the target object

```jsx
//Syntax is:
Object.assign(target, source)
```

- Holding multiple objects in an object

```jsx
const characterData = {
    hero: {
        elementId: "hero",
        name: "Wizard",
        avatar: "images/wizard.png",
        health: 60,
        diceCount: 3
    },
    monster: {
        elementId: "monster",
        name: "Orc",
        avatar: "images/orc.png",
        health: 10,
        diceCount: 1
    }
}
```

- When there are multiple js files we need importing and exporting of files in order to keep the code running

```jsx
//first method of exporting
export default name //name of whatever we want to export for example for exporting
//an object we would use the name of the object

//and in the file where we need this
import name from "path"

//we can change the name here though
```

- We need to use the attribute type=”module” in our script tag to tell js that we are importing and exporting in those files.
- Export default allows only exporting only one thing
- The other method for export and import is named export

```jsx
export {name}
```

and in the other file

```jsx
import {name} from 'path'

//here name has to be the same otherwise it won't work
```

- For things that don’t change throughout the program, we conventionally create a file called utils.js and put all that stuff there

- Eventlisteners>>>onclick

- .reduce() method: for getting one output from an array

```jsx
//example
const rainJanuaryByWeek = [ 10, 20, 0, 122 ]

const totalRainfallJanuary = rainJanuaryByWeek.reduce(function(total, currentElement){
//when reduce runs, it first assigns the first element to the variable total and the second element 
///to the variable currentElement
    console.log('total: ' + total, 'currentElement: ' + currentElement)
    return total + currentElement
})

console.log(totalRainfallJanuary)

// total: 10,"currentElement: 20"
// ›total: 30,"currentElement: 0"
// ›total: 30,"currentElement: 122"
// ›152
```

- Ternary operators in JS

```jsx
//Syntax
condition ? expression : another expression

// if the condition is true, expression is executed
// else 
// if the condition is false, another expression is executed
// so the : works like an else
```

```jsx
//example
const message = exerciseTimeMins < 30 ? 'You need to try harder!' : 'Doing good!'

console.log(message)
```

```jsx
//chaining for if else-if else
const message = exerciseTimeMins < 30 ? 'You need to try harder!' 
    : exerciseTimeMins < 60 ? 'Doing good!' 
    : 'Excellent!'
```

```jsx
//format like this
const endMessage = wizard.health === 0 && orc.health === 0 ?
    "No victors - all creatures are dead" :
    wizard.health > 0 ? "The Wizard Wins" :
    "The Orc is Victorious"
```

- Arrow functions: They are expressions. If a regular function has one parameter, then its arrow form can be written without brackets.
- One-line return statements can be written without the curly brackets and return keyword. However more complex logic requires both of those things to be there

```jsx
//regular function
function alertSpend(amount){
	return `Warning! You just spent £${amount}!`
}

//changing it to arrow function
const alertSpend = amount => `Warning! You just spent £${amount}!`

```

- setTimeout() method: it needs a function and a delay (in milliseconds) as its parameters

- Classes are essentially like constructor functions. There are differences there but they happen under the hood.

```jsx
class Module {
    constructor(){
        this.courseName = "Learn JS"
        this.studentsEnrolled = 5600
        this.studentsCompleted = 5100      
    }  
}

const learnJs = new Module
console.log(learnJs.studentsEnrolled)

//this will log out 5600
```

```jsx
class Module {
    constructor(){
        this.courseName = "Learn JS"
        this.studentsEnrolled = 5600
        this.studentsCompleted = 5100      
    }  
}

const learnJs = new Module
console.log(learnJs.studentsEnrolled)

//this will log out 5600
```

- Use toFixed(dig) to round off a number to ‘dig’ decimal places

- While doing code reviews check for:
    - Indentation
    - Code organization
    - Edge cases
    

- json (JavaScript object notation) is like a JavaScript object. Major difference is that the keys need to be in double quotes (key:value). Eg.

```json
[
    {
        "name": "Sarah",
        "age": 35,
        "birthplace": "Scotland",
        "hobbies": [
            "violin",
            "singing",
            "crafting"
        ]
    },
    {
        "name": "Michael",
        "age": 56,
        "birthplace": "South Africa",
        "hobbies": [
            "skateboarding",
            "guitar"
        ]
    }
]
```

## APIs (Application Programming Interfaces)

An API is basically a tool that helps connect our program with someone else’s program

- Internal server error code is 500

- Fetch API example

```jsx
fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
        console.log(data)
        document.getElementById("activity-name").textContent = data.activity
    })
```

- HTTP stands for HyperText Transfer Protocol: it is a protocol for determining how HyperText (text) should be transferred over the internet

- Components of a Request
    1. Path (URL) : Address where your desired resource lives
        1. BaseURL
        2. EndPoint
            
            eg. in https://scimba.com/landing, https://scrimba.com is the baseURL and landing is the endpoint
            
    2. Method (like GET, POST, PUT, DELETE etc)
        1. GET: for getting data
        2. POST: for adding new data
        3. PUT: for updating existing data
        4. DELETE: removing data
    3. Body (optional)
    4. Headers: extra information about the outgoing request
- fetch() can actually take another parameter

```jsx
fetch("url" , {options}
//for example
fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "POST"})

//default value for method key is GET
```

```jsx
fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
        method: "POST",
        body: JSON.stringify({
        title: postTitle,
        body: postBody
    }),
        headers: {
            "Content-Type": "application/json"
        }
    })
        .then(res => res.json())
        .then(data => console.log(data))
})
```

form.reset() for clearing the form

### REST

- REST stands for REpresentational State Transfer
- It is a design pattern to provide a standard way for clients and servers to communicate
- Statelessness: when the client makes a request to the server, the server fulfils that request but does not maintain any memory of that request. It forgor 💀
- We are just accessing resources
- use nouns as end points

URL Parameter

```jsx
https://mikesbikes.com/api/bikes/:id/reviews
// here, :id is called as url parameter and it has values like 1,2,3 etc.
// :id can be described as :
//Variable inside the URL that acts as a placeholder for the real value

```

- Query Strings: a way to filter results. They go like ?something=something in a url. Somewhere down the line it becomes an object.

```jsx
/bikes?type=mountain 
// will become {type:"mountain"}
/bikes?type=mountain&brand=hero
//will become {type: "mountain", brand="hero"} 
```

## Filter method in JavaScript:

Map method creates a new array by individually changing each element in the array

Filter creates a new array be removing the elements that are not required

Reduce takes all the elements in an array and reduces them to a single value according to the function that we give it.

```jsx
//example of filter
const voters = [
    {name: "Joe", email: "joe@joe.com", voted: true},
    {name: "Jane", email: "jane@jane.com", voted: true},
    {name: "Bo", email: "bo@bo.com", voted: false},
    {name: "Bane", email: "bane@bane.com", voted: false}
]

// Write your code below
const finalResult = voters.filter(voter => voter.voted).map(voter => voter.email)
console.log(finalResult)

```

## Asynchronous JavaScript

- **Synchronous** means each command must complete before the next command can execute. This implies that no two commands can be running at the same time
- Asynchronous means code that can be run out of order. This allows a length operation to start early but finish at a later time without blocking other code from running in the meantime
- JavaScript isn’t truly asynchronous though as it is single-threaded. It has callback mechanisms in place to run commands in a different order to make things more efficient.
- A callback function is a function passed as an argument to another function

### Promises

- three states
    - pending: yet to be completed
    - fulfilled: promise was completed
    - rejected: not completed
- fetch() is also a promise
- promise is an object in JavaScript

- we can use Element.children to access child elements of a node. The returned array-like object is called HTMLCollection. For example

```jsx
document.getElementById("cards").children[1].innerHTML = `something`
```

### Async / Await Functions

- async and await were introduced in ECMAScript 2017 (ES8)
- We use them in place of .then() blocks and they make an asynchronous piece of code “look/read” like synchronous functions
- Async makes a function return a promise and await makes a function wait for a promise

```jsx
//without async/await:
function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            deckId = data.deck_id
            console.log(deckId)
        })
}

//with async/await
async function handleClick() {
    const response = await fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
    const data = await res.json()
    remainingText.textContent = `Remaining cards: ${data.remaining}`
    deckId = data.deck_id
    console.log(deckId)
}
```

- Show error using throw

```jsx
throw Error("error text")
```

### Promise Rejection

- If some error arises during the attempt of fulfilling a promise, the promise gets rejected.
- We can use .catch() to execute some code if the promise gets rejected

```jsx
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=;hjksdf;kljsdfgl;kdsjfgljksdfglkjhsdfg")
    .then(res => res.json())
    .then(data => {
        console.log(data)
        throw Error("I'm an error!")

    })
    .catch(err => {
        console.log("Something went wrong! 😭")

    })
```

- For getting current time in JavaScript

```jsx
var time = new Date();
console.log(
  time.toLocaleString('en-US', { hour: 'numeric', minute: 'numeric', hour12: true })
);
//this will give us an output like: 1:32 PM

//same for this:
const date = new Date()
console.log(date.toLocaleTimeString("en-us", {timeStyle: "short"}))
```

- For getting current location using geolocation API

```jsx
navigator.geolocation.getCurrentPosition(position => {
    console.log(position)
});
//here position is a callback function and a parameter of the getCurrentPosition 
//function

```

- HTMLCollection to Array

```jsx
//example
let myPhotoImgs = Array.from(document.getElementsByClassName("my-photo"))
```

Important screenshot

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/410edf9b-a808-4af0-ae8c-aca877715ada/Untitled.png)

Classes in JavaScript are just blueprints for creating objects that have the same properties and access to the same methods.
