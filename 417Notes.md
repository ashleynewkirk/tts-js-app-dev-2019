# ES6 Notes 


//ES6 allows backticks and enter as line breaks 

``` javascript 

console.log(`Hello! I'm a string
continues on this line`);

console.log("string text 1/n"+ 
"string text2");

const name = "Ashley"; 
const day = "Wednesday";
const instructor = {
    name: "Pasha",
    lesson: "ES6",
    greet: function (){
        return `Hello ${this.name}...this lesson is ${this.lesson}.`
    }
}

console.log("Hello" + name + " I hope you have a great day on " + day);

//below is an example of interpolation - string concatenation is no longer necesary
console.log(`Hello ${name} I hope you have a great ${day}!`);

console.log(`Hello ${instructor.name}...this lesson is ${instructor.lesson}.`)
console.log(instructor.greet());
```
## Variable Examples 
``` javascript 
function foo (){
    let x = true; 
    if (x) {
        //var usingVar = 'im usin var';
        let usingVar = 'im usin let';
        
    }
    console.log(usingVar);
}
foo(); // undefined because let has local scope.


//can't rename const, but const can be modified. 
const instructors = ["Jimmy", "Christopher"];
instructors.push("Jack", "Jill", "Pasha");

console.log(instructors); */
```
## Scope 

//ES6 allows backticks and enter as line breaks 

``` javascript
*console.log(`Hello! I'm a string
continues on this line`);

console.log("string text 1/n"+ 
"string text2");

const name = "Ashley"; 
const day = "Wednesday";
const instructor = {
    name: "Pasha",
    lesson: "ES6",
    greet: function (){
        return `Hello ${this.name}...this lesson is ${this.lesson}.`
    }
}

console.log("Hello" + name + " I hope you have a great day on " + day);

//below is an example of interpolation - string concatenation is no longer necesary
console.log(`Hello ${name} I hope you have a great ${day}!`);

console.log(`Hello ${instructor.name}...this lesson is ${instructor.lesson}.`)
console.log(instructor.greet());


function foo (){
    let x = true; 
    if (x) {
        //var usingVar = 'im usin var';
        let usingVar = 'im usin let';
        
    }
    console.log(usingVar);
}
foo(); // undefined because let has local scope.


//can't rename const, but const can be modified. 
const instructors = ["Jimmy", "Christopher"];
instructors.push("Jack", "Jill", "Pasha");

console.log(instructors); */

function hello(name) {
    name = name || 'Mystery Person';
    console.log("Hello " + name + '!')
}
hello("Bobby");
hello();
function hello(name) {
    name = name || 'Mystery Person';
    console.log("Hello " + name + '!')
}
hello("Bobby");
hello();
const instructors = ["Jimm", "Christ"]
//instructors = ["Jim", "Chris"] //instructors = ["Jim", "Chris"]
                                          // ^
                                          // TypeError: Assignment to constant variable.
instructors.push("Jack", "Jill"); //instructors now consists of [ 'Jimm', 'Christ', 'Jack', 'Jill' ]
console.log(instructors);
//const also accepts uppercase
function hello(name) {
    name = name || 'Mystery Person';
    console.log("Hello" + name + "!");
};
hello("Bobby"); //HelloBobby!
hello(name); //HelloJimmy!
hello(" Bobby!"); //Hello Bobby!
hello(" "+name); //Hello Jimmy!
function hello1(name = 'Mystery Person') {
    console.log(`Hello ${name} is it me you're looking for`);
}
hello1(); //Hello Mystery Person is it me you're looking for
//NOTE: I named this function hello1 because if I'd named it hello, it would've console logged all of the previous results with these new parameters.
                    // Hello Bobby is it me you're looking for
                    // Hello Jimmy is it me you're looking for
                    // Hello Mystery Person is it me you're looking for
                    // Hello  Bobby! is it me you're looking for
                    // Hello  Jimmy is it me you're looking for
        //Which, yikes.
```

## Additional Examples 
```javascript
        let students = ["Julian", "AJ", "Matt"];
        //let [x,y,z] = students;

        let[x, ...rest] = students;
        console.log(x, rest);


let completedHomework = () => {
    return ["Julian", "AJ", "Matt"];
}
let [x,y,z] = completedHomework();
console.log(x,y,z);

let instructor = {
    name: "Jimmy",
    email: "no@no.com",
}
let { name: x, email: y} = instructor;

console.log(x);

let car = {
  make: 'Tesla' 
} 

function something(make, year = 2019) {
   console.log(make.make, year);
}

something(car);

function Person (name, job){
    this.name = job;
    this.job = job;
}

Person.prototype.getName = function getName() {

    return this.name;
}

var goodGuy = new Person ("Aang", "Airbender");
console.log(goodGuy.getName()); */

class Person {
    constructor (name, job){
    this.name = name; 
    this.job = job;
}
getName () {
    return this.name; 
 } 
getJob(){
    return this.job; 
 }
}
let goodGuy = new Person ("Neo", "the one");
console.log(goodGuy);

class SuperHero extends Person {
    constructor (name, heroName, superPower) {

    super(name);
    this.heroName = heroName;
    this.superPower = superPower;
    }
    secretIdentity(){
        return `${this.heroName} is ${this.name}!!`

    }
}
let batman = new SuperHero ("Bruce Wayne", "I'm Batman");
console.log(batman.secretIdentity());


class Person {
    constructor (name) {
    this.name = name; 
}
set name(name) {
    this._name = name; 

}
get name () {

return this._name;
}
}
let goodGuy = new Person ('Jim Gordon');
console.log (goodGuy.name); 
goodGuy.name = "James Gordon";
console.log(goodGuy.name);
```
## Additional Example 
``` Javascript
function add() {
    console.log("arguments object:", arguments);
    
    var numbers = Array.prototype.slice.call(arguments);
    
    var sum = 0;
    
    numbers.forEach(function (number){
        sum += number;
    });
    return sum;
    
}
console.log(add(1,2,3,4,5,6,7,8)); */

let add = (...numbers) => {
    console.log("rest parameters", numbers);

    let sum =0;
    
    numbers.forEach(function (number) {
        sum += number; 
    
    });
    return sum; 
}
console.log(add (1,2,3,4,5,6,7,8));

let add=(...numbers)=>numbers.reduce((sum,number)=>sum+=number,0);
console.log(add(1,2,3,4,5,6,7,8));
```