# JavaScriptNotes


 # -- ADVANCED JAVASCRIPT --
 var const let



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


# WINDOW OBJECT ✅
There are tons of features that javascript doesn't have itself, but it uses browsers features to do that work.
those features are available in window object of browser. Such as Prompt, Alert, Confirm are not the part of javascript but still we can use them in our code
because javascript allows us to use windows features.

# BROWSER CONTEXT API ✅
Browser Context API gives mainly 3 things : 
                    - Windows Object
                    - Stack Memory
                    - Heap Memory 





# -- BASIC JAVASCRIPT --

# WORD vs KEYWORD ✅
------------------------------------------
Word - That doesn't have some meaning in JavaScript  i.e. :  Aman, Shubham, Uncle
Keyword - That has some meaning in JavaScript :   for, while, NaN

# var const let ✅
----------------------------------------------
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


# Hoisting ✅
-------------------------------
Hoisting is when variable can be used before declaration, but it's value will be undefined.
In hoisting, variables and function declaration is moved on the top of code automatically

console.log(c);       // undefined
var c = 5;
// this will be broken down in 2 part
var c;     Declaration    -  this will be moved up
c = 5;      Definition

# Types in JS ✅  : Premitives & Reference
------------------------------

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

# Loops : ✅
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


# ARRAY ✅
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



# Object ✅

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
