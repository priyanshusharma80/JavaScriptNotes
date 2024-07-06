# COMPLETE JAVASCRIPT NOTES


Note: 
- JavaScript is a dynamically typed language
- all no premitive datatype has typeof an object


// *********************** Variables & datatypes✅ ****************************
let name = "aman";        // string
let isStudent = true;       // boolean
                                         // null - standalone value (null is an object)
let age = 21;                   // number  - range 2 to the power 53
// bigint - usually used in stock market 
let brother;                    // undefined 
// symbol - unique
// object

console.table([typeof name,typeof isStudent, typeof age, typeof null, typeof brother]);

// here null type will return "OBJECT", hence null is an object

// ---------------------- Datatypes ✅ ------------------------------

  // Premitives: 7 types -> string, boolean, number, null, undefined, symbol, BigInt (call by value)
  // Reference (non premitive) -> array, objects, functions  (call by reference)

// ********************** Conversion Operations: ✅ ******************************
/*
        Quick Overview: 
        "33"  -> 33
        "33abc" -> NaN
        true  -> 1
        null   -> 0
        undefined -> NaN

        "" -> false
        "aman" -> true
        1 -> true
        0 - > false

        Conversion could be done using, Number(), Boolean(), String() etc functions.
*/

let score = "33";        // now if you want this score to be changed from string to number
console.log(score);
let numscore = Number(score);
console.log(numscore);          // will print 33 as number

// MISTAKE ->
let score2 = "33abc";
let numscore2 = Number(score2);
console.log(typeof numscore2)         // will print number
console.log(numscore2)                     // will print NaN - Not a Number

console.log(Number(null))                 // will print 0
console.log(Number(undefined))      // will print NaN

console.log(Number(true))                // will print 1 for true and 0 for false;

const obj = {
    name: "aman",
    age: 32
}

console.log(obj)                              // will print "Function"



// ***********************   Memory in JavaScript ✅  ****************************

// Stack (Primitive Datatypes ke liye)
// Heap (Non Primitive Datatypes ke liye)

// Note: Jb bhi koi value stack se milti h to vo copy milti h brna agar heap se milti h to vo reference provide krti h

// ********************** Number and Maths in JavaScript ✅ ***********************

const score = 400;
console.log(score)                        // will print 400

You can explicitly define a number even though javascript is pretty smart to know which variable to store in which type

const num = new Number(40);                // like this
console.log(num);                          // will print [Number: 40]
console.log(num.toString());        // will print 40 as string
console.log(num.toString().length);           // will print 2
console.log(num.toFixed(2));       // 

// toPrecision() method
let num = 123.899;
console.log(num.toPrecision(3))      // will return 124
console.log(num.toPrecision(4))      // will return 123.9
console.log(num.toPrecision(2))      // 1.2e+2

// toLocaleString();
let number = 1000000;
console.log(number.toLocaleString());            // will print 1,000,000 - US based like 100 thousand
console.log(number.toLocaleString('en-IN'));    // now will print 10,00,000 - indian based


// there are some other things with Number
Number.MAX_VALUE
Number.MIN_VALUE
Number.MIN_SAFE_INTEGER
Number.MAX_SAFE_INTEGER
Number.isInteger("23");                              // false;



// ********************** MATH ✅ *******************************
console.log(Math);                          // object with several useful methods
console.log(Math.abs(-4))              // will print 4;
console.log(Math.round(4.6))        // will print 5
console.log(Math.ceil(4.6))            // will print 5;
console.log(Math.floor(4.6))          // will print 4

console.log(Math.min(2,3,5,6));     // will print 2
console.log(Math.max(2,3,6,2,5))  // will print 6

console.log(Math.random());         // hmesha 0 se 1 ke beech me value aati h randomly 

// ab agar hme badi value chaiye to hm multiply kr skte h like by 10 aur 100 or 1000
console.log(Math.random()*10);
// kabhi kabhi value 0 bhi ho skti h, to usko avoid krne ke liye hm +1 kr dete h
console.log((Math.random()*10)+1);

// formula to get value through random function in a certain range
const min = 10;
const max = 20;

console.log(Math.floor(Math.random()*(max-min+1))+min);


// *********************** DATE & TIME ✅ ******************************

const mydate = new Date();
console.log(mydate.toString());
console.log(mydate.toDateString());
console.log(mydate.toLocaleString());

console.log(typeof(mydate))              // will print Object

let mycreatedDate = new Date(2023,0,23);
console.log(mycreatedDate.toDateString())            // Mon Jan 23 2023  - month start with 0 in javascript

let mydate = new Date(2023-01-25);
console.log(mydate.toLocaleString())         // 25/1/2023

let mytimestamp = Date.now();
console.log(mytime)                           // will print time in miliseconds from Jan 1970

// if you want to convert date into miliseconds then
console.log(mydate.getTime());        // now will print time in miliseconds
console.log(Math.floor(Date.now()/1000))     // will print time in seconds

// to get specific things from date
console.log(mydate.getDate());
console.log(mydate.getFullYear());
console.log(mydate.getDay());
console.log(mydate.getMonth());
console.log(mydate.get)


// *********************** PLAYING WITH ARRAYS ✅ **********************************

const arr = [1,2,3,4,5,"hello",false];
const newarr = new Array(1,2,3,5,6,8);

// SHALLOW COPY :  reference is passed
// DEEP COPY :     only value is passed

console.log(arr);
arr.unshift(9)                                   // adds 9 at the starting of the array
arr.shift();                                        // removes first element of the array
arr.push(5);
arr.pop();
console.log(arr.includes(5));          // returns true;
console.log(arr.includes('priyanshu'))  // return false;
console.log(arr.indexOf(4))             // returns 3
console.log(arr.indexOf(19))           // returns -1

const stringarr = arr.join();            // convert array elements into string form 12345Hellofalse like this


const ar = [1,2,3,4,5,6];

// ----------------------- slice and splice function ✅ --------------------------

console.log(ar)                            // [1, 2, 3, 4, 5, 6]

const slicearr = ar.slice(2,4)          
console.log(slicearr)                  // [ 3, 4 ]
console.log(ar)                           // [1,2,3,4,5,6]  nothing changed in the actual array

const splicear = ar.splice(1,3)   // [ 2, 3, 4 ]
console.log(ar)                           // [ 1, 5, 6 ]    mtlb that portion gayab ho gya


// SOME ADVANCED
const arr1 = [1,2,3,4];
const arr2 = [2,3,4,3];

arr1.push(arr2);                      //  [1,2,3,4,[2,3,4,3]];
const newarr = arr1.concat(arr2)                    
console.log(newarr)              // [1,2,3,4,2,3,4,3];

// or use spread operator
const allelem = [...arr1, ...arr2];                 // [1,2,3,4,2,3,4,3]

const array = [1,2,3,4,[10,22,[33,45]],55,0,[3,5,3]];
// ab agar is array ko single dimension bnana h to 
const newar = array.flat(Infinity);           //   [1,2,3,4,10,22,33,45,55,0,3,5,3];

console.log(Array.from("aman"));          // will print ['a','m','a', 'n'];
console.log(Array.from({name: "priyanshu"}))    // will return [] - empty array because it's not able to convert in array

const a = 100;
const b = 200;
const c = 300;

console.log(Array.of(a,b,c));                  // will print [a,b,c]


// *********************** OBJECTS ✅ *********************************

// In JavaScript, Objects can be declared in 2 ways 
//              1. Through Object Constructor
//              2. Through Object Literal 

// Agar hm constructor ke through object create krte h to vo ek singleton object hota h
Object.create()
// or 
const objd = new Object();

const mySym = Symbol('key1');

// another way : Through object literal 
const obj = {
    name: "priyanshu",                           // by default ye name ko "name" consider krta h
    "full name": "Priyanshu Sharma",
    age: 21,
    isLoggedIn: false,
    course: "MCA",
    [mySym]: "mySym",                         // symbol object
    lastLoginDays: ["Sunday","Monday","Saturday"],
};

// accessing properties in Object
console.log(obj.name);                      // hmesha ye method kaam ni krta
console.log(obj[name]);                  // name is not defined error
console.log(obj["name"])                // ab thik h - priyanshu aayega

console.log(obj."full name")               // Not Possible
console.log(obj["full name"])             // this is the role you understood?
console.log(obj[mySym]);                  // syntax to print symbol in javascript

// making changes in object
obj.name = "Shubham";
console.log(obj.name);

Object.freeze(obj);                            // ab koi bhi changes propagate ni honge


obj.greeting = function(){
    console.log("Hello Priyanshu!");
}

console.log(obj);
console.log(obj.greeting);             // returns function body - function execute ni hua h sirf function ka reference aaya h 
console.log(obj.greeting());           // will print : Hello Priyanshu! 

obj.greetings2 = function(){
    console.log(`Hello ${this.name}`);        // will print Hello priyanshu
}

console.log(obj.greetings2());


// NESTED OBJECT
const user = {
    id: 123,
    fullname: {
        username: {
            firstName: "Priyanshu",
            lastName: "Sharma",
        }
    }
}

console.log(user.fullname.username.firstName);          // Priyanshu
console.log(user.fullname.username.lastName);           // Sharma
console.log(user.fullname?.username.lastName);           // Sharma, in case agar fullname exist ni krega to ye expression error ni dega

const ob1 = {1:'a', 2:'b'};
const ob2 = {3:'c',4:'d'};
const ob3 = {5:'e',6:'f'};

const obj4 = {ob1,ob2, ob3}                        // will print { {1:'a', 2:'b'}, {3:'c',4:'d'} {5:'e',6:'f'} }
const obj4 = Object.assign({ }, ob1, ob2, ob3 )      // where first parameter in assign is target object in which the next objects are to be stored!
const  ob4 = {...ob1, ...ob2, ...ob3};               // using spread operator

// Now if you want to get keys/values list of an object, Here's how you can do it!
console.log(Object.keys(obj));              // will return the array of keys exist in obj object
console.log(Object.values(obj));           // will return the array of values for each key
console.log(Object.entries(obj));          // [ ['name': "Priyanshu"], ['age':21] , ['course':"MCA"] ];

console.log(obj.hasOwnProperty('isLoggedIn'));             // will return true, since it contains isLoggedIn

// Destructuring of Objects

const {name} = obj;
console.log(name)                 // will print "priyanshu" 

// agar aapko lagta h ki ye bda nam h to isko customize bhi kr skte ho
const {name: nm} = obj;               // this usecase is widely used in react while receiving props
console.log(nm);                    // will also print "priyanshu"



// *********************** FUNCTIONS ✅ ****************************** 

function addTwoNumbers(num1,num2){                    // parameters
    console.log(num1+num2);
}

addTwoNumbers(3,"4")                 // arguments  

const res = addTwoNumbers(2,4);     
console.log(`Result : ${res}`)                              // Result: undefined - Kyunki function koi value return ni krra


function printMessage ( user = 'defaultValue :)' ){
    return `${user}, You're logged in!`;
} 

console.log(printMessage("Priyanshu"));         // will print Priyanshu, You're logged in! 

// but jb aap kuchh paas ni kroge tb kya hoga
console.log(printMessage());                         // will print undefined, You're logged in -  agar default value ni dete!


// USAGE OF REST 
// imagine a scenario where you want to add cart value on an ecommerce website, but if you'll receive only one parameter, that would not be the right way
//  that's where we use Rest Operator

function addNumbers( ...nums ){
    return nums;
}

console.log(addNumbers(200,300,232,435)); 


// Functions with Objects 

function playwithObj ( obj ){
    return `My Name is ${obj.name} and I'm pursuing ${obj.course}`;
}

console.log(playwithObj({
    name: "Priyanshu",
    course: "MCA",
}))                                                 // will print "My Name is Priyanshu and I'm pursuing MCA"


// *********************** SCOPE ✅ ************************************

var a = 300;

if(true){
    var a = 400;
    const b = 230;
    console.log("Inner: ",a);
}

console.log(a);                 // will print 400
console.log(b)                  // will print : Undefined



let a = 300;

if(true){
    let a = 400;
    const b = 230;
    console.log("Inner: ",a);
}

console.log(a);                      // will print 300 na ki 400 
console.log(b);                       // will print undefined


function one() {
    const username = "aman";
    function two () {
        const website = "grosocial.in";
        console.log(username);              // will print username - because child can access parents variable
    }

    console.log(website);                     // not possible- Error: Website is undefined
    two();
}

one();

// IMPORTANT CONCEPT 
console.log(addOne(5))                    // will print 6
function addOne(num){
    return num+1;
}

console.log(addTwo(4))                    // Error:  addTwo Undefined 
const addTwo = function (num){                      // this is called function expression
    return num+2;
}


// ********************** THIS & ARROW FUNCTION *******************************

const obj = {
    username: "hitesh",
    price: 999,
    welcomeMessage: function(){
        console.log(`hello ${this.username}, How Are You?`);
        console.log(this)
    }
}

obj.welcomeMessage                 // will print nothing
obj.welcomeMessage();             // will print hello hitesh, How Are You?

obj.username = 'Priyanshu';
obj.welcomeMessage();             // will print hello Priyanshu, How Are You?

console.log(this)                       // returns { } - an empty object, But in Browser this returns the windows object


function chai(){
    console.log(this);                     // will print so much clutter
    let username = 'hitesh';
    console.log(username)           // will print hitesh obviously
    console.log(this.username)    // will print undefined - ye sirf object me hi kaam krta h functions me nhi
}

// same with function expression
const chai = function () {
    console.log(this);                     // will print so much clutter
    let username = 'hitesh';
    console.log(username)           // will print hitesh obviously
    console.log(this.username)    // will print undefined - isko bhi ni pta what is this.username   
}

chai();


// ARROW FUNCTIONS -> 

// syntax of arrow function 
( ) => { }                // ab isko aap ek variable ke andar bhi hold kr skte h

const fun = ( ) =>{
    let username = 'hitesh';
    console.log(this.username)    // will print undefined - Yhan pe bhi ni kr skte
}


const addnum = (num1,num2) =>{
    return num1+num2;
}

// implicit version of this function 
const addnum = ( num1,num2) => (num1+num2)

console.log(addnum(2,3));

const example2 = (num1,num2) => {name: "hitesh"}           // will print undefined kyunki aise object ko return ni krte h
const example2 = (num1,num2) => ({name: "hitesh"})

console.log(example2(2,3)); 


// ************************ CONCEPT OF IIFE ✅ ********************************

// IIFE (Immediately Invoked Function Expression) helps to limit the scope of variables, preventing them from polluting the global namespaces


// NAMED IIFE
(function() {
  var localVariable = 'This is private';
  console.log(localVariable); // 'This is private'
})();                     // semicolon jroori h yhan dhyan rkhna

console.log(localVariable); // ReferenceError: localVariable is not defined

// second way to define

// SIMPLE IIFE
( ( name ) => {
    console.log(`Hello ${name}`);
} ) ('Priyanshu');


// ********************** LOOPS ✅ ***********************

// Ye sb to aata hi h : )


// ********************* MAPS ************************
const map = new Map();
map.set("IN","INDIA");
map.set("USA", "United States of America");
map.set("UK", "United Kingdom");

// for of loop

for(const i of map){
    console.log(i);                            
}

for(const [key,value] of map){
    console.log(key + '->' + value)           // this doesn't work for obj
}

const obj = {
    js: "javascript",
    cpp: "C++",
    py: "Python",
}

for(const key in obj){
    console.log(key + '->' + obj[key]); 
}

const langArr = ["javaScript","C++","Java",'Python'];
for(const key in langArr){
    console.log(key)                                    // will print 0,1,2,3 since it is an array
    console.log(langArr[key]);
}

// forEach loop

langArr.forEach(function (item){
    console.log(item);
})

function greet(item){
    console.log(item);
}

langArr.forEach(greet);                    // sirf reference pass kra h run ni kra h function ko

langArr.forEach((item) =>{
    console.log(item);
})


// *********************** FILTER, MAP & REDUCE ✅ *************************

// what is the use? Sometimes we might needed that forEach should return some value based on some condition
// but forEach doesn't return any value that's why we use these 3 methods

langArr.forEach((item)=>{
    return item;                                           // will print undefined only
});

// filter method

const exm = [1,3,4,5,6,7];

const newexm = [];
exm.forEach((item)=>{
    if(item>3) newexm.push(item);                 // thik hi h
})

const newexm = exm.filter((item)=>item>3);                   // but ye bdia h
console.log(newexm); 

// map method

const newAns = newexm.map((item)=>item+10);              
console.log(newAns)                      // 11,13,14,15,16,17


// chaining
const newans = newexm
                                 .map((num)=>num*10)
                                 .map((num)=>num+1)
                                 .filter((item)=> item>40);


// Reduce Method

const arr = [1,2,3,4,5];

const myTotal = arr.reduce(function (acc, currVal){
    console.log(`acc: ${currVal}, currVal:${currVal}`);
    return acc + currVal;
}, 0);

const myTotal2 = arr.reduce((acc,currVal)=>acc+currVal,0);

console.log(myTotal);


// *********************** Strings and their Functions ✅*******************************

krna h 

// *********************** DOM MANIPULATION ✅ **********************************

console.log(document)                // to HTML document form me dikhayega
console.dir(document)                 // directory form mtlb jaise object ki form me dikhaega


Popular Methods to select any element:
There are mainly 6 methods to select any DOM element;

document.getElementById('id');                           // return type - Element
document.getElementsByClassName('classname');   // return type - HTMLCollection
document.getElementsByTagName('h1');             // return type - HTMLCollection
document.getElementsByName('name')            // returntype - nodelist
document.querySelector('.myclass')                   // returntype - element  - agar class select krni h to ".classname" agar id to "#idname" and tag select krna h to simple 'tagname';
document.querySelectorAll('.myclass')               // returntype - nodelist


// practice
document.getElementById('id').className         // returns class of the element selected using id
document.getElementById('id').getAttribute('id')     // this will return id of that element
document.getElementById('id').getAttribute('class')     // this will return id of that element

document.getElementById('id').setAttribute('class', 'myclass')     // this will return id of that element


// Accessing content in an HTML Element ✅

there are three methods:

- textContent  - shows all the content, both hidden and not hidden
- innerText  -   doesn not show up the hidden content
- innerHTML - ye andar ka html bhi aapko laake dedeta h



// ******************* DOM SELECTORS - NodeList and HTMLCollection ✅ ************************

// templist - array jaisa h but map and reduce jaise function ni hote, so we can't use them

const templist = document.querySelectorAll('li');

// if we'll do this
templist.style.color = 'green'           // there comes are error because it is a nodelist
templist[0].style.color = 'green'      // this will make the first li color green

// we can also access templist using forEach function - because it doesn't have map function but has forEach method
templist.forEach(function(list){
    list.style.color = 'green';
});

// to convert HTMLCollection to array
// if you'll collect elements through its classname method, you'll get a HTMLCollection
// but HTMLCollection neither have map function neither have forEach method. so in order to access elements of HTMLCollection we'll have to convert it into array

const collection = document.getElementsByClassName('list-class');       // returns a HTMLCollection

Array.from(collection);

// now we'll be able to use forEach and map method

// let's work on wikipedia

const headinglist = document.getElementsByTagName('h3');

const headingarr = Array.from(headinglist);

headingarr.forEach(function(heading){
    heading.style.color = 'red';
    heading.innerText = 'Hello Priyanshu';
    heading.style.backgroundColor = 'gray';
})




// LEARN WHAT MATTERS 


Var : 
  - var exists in ES5 Version
  - var is function scoped
  - var adds itself to window object 

let & Const :
  - let & const exists in ES6 version 
  - let & consts are braces scoped 
  - let & const does not add itself in windows object



var - function scoped - var can be used anywhere in the function in which it's defined. 
let - braces scoped

function abcd(){
    for(var i=0;i<4;i++) 
        console.log(i);
    console.log(i);           // prints 4

    for(let j=0;j<4;j++)
        console.log(j);
    console.log(j)           // error : j is not defined
}

abcd();


// ------------------------ WINDOW OBJECT ✅ ---------------------------------
There are tons of features that javascript does not have itself, but it uses browsers features to do that work.
those features are available in window object of browser. Such as Prompt, Alert, Confirm are not the part of javascript but still we can use them in our code
because javascript allows us to use windows features.

// --------------------- BROWSER CONTEXT API ✅ ---------------------
Browser Context API gives mainly 3 things : 
                    - Windows Object
                    - Stack Memory
                    - Heap Memory 



// -------------------------- WORD vs KEYWORD ✅ ------------------------------
Word - That does not have some meaning in JavaScript  i.e. :  Aman, Shubham, Uncle
Keyword - That has some meaning in JavaScript :   for, while, NaN

// ---------------------------   var const let ✅ ------------------------------
var - var is something which value can be changed later
const - const is something which values can't be changed

var a = 5;
console.log(a);
a = 6;
console.log(a);

const b = 6;
console.log(b);
b = 7;      (Not Possible)
console.log(b);


// -------------------------------- Hoisting ✅ -------------------------
Hoisting is when variable can be used before declaration, but it's value will be undefined.
In hoisting, variables and function declaration is moved on the top of code automatically

console.log(c);       // undefined
var c = 5;
// this will be broken down in 2 part
var c;     Declaration    -  this will be moved up
c = 5;      Definition

// -------------------  Types in JS ✅  : Premitives & Reference -----------------------

Premitives:  Variable that can be copied without passing reference to it.   : String, null, boolean etc
References : Variables that cannot be copied directly, but their reference is passed   { },[ ],( )

let ex = 5;
let ex2 = ex;
ex2 = 6;
console.log("ex2: ",ex2)      // ex will not be changed
console.log("ex: ", ex)

var arr = [1,2,4,5];
let arr2 = arr;
arr2.pop();
console.log("arr2: ",arr2);
console.log("arr: ",arr);        // arr will also get changed since passed with reference


if else : to tum jante hi ho ✅

// -------------------------------- Loops : ✅ ---------------------------------
For loop

for(let i=0;i<5;i++) console.log(i);

# FUNCTIONS ✅
types :  Anonymous, Normal, Callback, Asynchronous
to perform specific operations, help reusable the code.

hellobolo();
function hellobolo(){
    console.log("hello Priyanshu :) ");
}

printNum([1,2,3,4]);
function printNum(a){
    // a.pop();   - mtlb ye bhi by reference pass hora h 
    console.log(a[3]);
}


// ------------------------------ ARRAY ✅ ------------------------------------
var arr = [1,2,3,4,5];
arr.push(6);
console.log(arr);

arr.unshift(0);
console.log(arr);

arr.shift();
console.log(arr);

arr.shift();
console.log(arr);

arr.pop();
console.log(arr);

arr.splice(2,2);
console.log(arr);



// ------------------------- Object ✅ ----------------------------

let obj = {
    name: "Priyanshu",
    age: 21,
    college: "NIT Raipur",
    greet: function(){
        console.log(`hello ${this.name}! Good to See you Again :)`);
    }
}

console.log(obj);
console.log(obj[0]);       // wrong way
console.log(obj.name);
console.log(obj.age);
console.log(obj.college);
console.log(obj.greet());




// ********************* EXTRAS✅ ********************************

console.log("Hello, World!");

let name = 
    "Priyanshu"+" Sharma";
console.log(name);

const object = {course: "BCA", rollno: 66};

console.log(object.course);
console.log(object.rollno);
console.log(object.name);


let a = 5;
let b = 7;


console.log("Before Swapping: ");
console.log("a = " + a + " b = " + b);
a = a+b;
b = a-b;
a = a - b;
console.log("After Swapping: ");
console.log("a = "+ a + " b = " + b);
