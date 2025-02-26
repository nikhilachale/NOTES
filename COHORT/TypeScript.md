


```
// const x:number =2;

// console.log(x);

  
  

// giving arguments

// function heyy (fname: string)

// {

// console.log("hello "+fname)

  

// }

// heyy("nikhil");

  

// return values from an function

// function sum (a: number, b: number):number

// {

  

// return a + b;

  

// }

  

// const val=sum(1,2);

// console.log(val)

  
  
  

// function isValid(age: number): boolean {

// if (age > 18)

// return true;

// else

// return false;

// }

  

// console.log(isValid(20))

  

//function to function or callbacks

// function runAfter1S(fn:()=>void )//passed function as an argument

// {

// setTimeout(fn,1000);

  

// }

// runAfter1S(()=>{

// console.log("heyy after 1s")

// })
```


### tsconfig file

1. target :specifies the. ECMA script  target version 
2. dir : root sir and out dir  root have ts file and outdir have generated js files
3. remove comments
4. noImplicitAny

### Interfaces

you can implement interfaces as an class 
create a react app that takes an todos as an input and renders them 



### Types
types cannot implementes as an classes

UNION
types let us do union of the datatypes parameter  type stringOrNUmber = string | number 


```
//Union

type stringOrNumber = string | number;

function printAge(age: stringOrNumber) {

console.log(age)

}

printAge("21");
```

INTERSECION
can have properties of multiple class 
types allows intersection interfaces does not 
types let us do union and intersection class does not 
```
  

//intersection

type user = {

fname: string,

age: number,

email?: string // user can pass it or it can be empty

}

  

type address = {

city: string,

pincode: number,

state: string

}

  

type employee = user & address; // it can be user or address

  

const e: employee = {

fname: "nikhil",

age: 21,

city: "pune",

pincode: 411033,

state: "maharashtra"

}

  

console.log(e)
```


### arrays in TS
```
//Arrays in TS

const arr: number[] = [1, 2, 3, 4, 5];

  

// function to print the max value in an array

function max(arr: number[]): number { // this can be also wrrtien as types numarr=number[]; function max(arr:numarr):number

let max = 0;

for (let i = 0; i < arr.length; i++) {

if (arr[i] > max)

max = arr[i];

}

return max;

}

console.log(max(arr)); 
```

### Enums

 **Enums** are a special data type that allows you to define a set of named constants. They make it easier to work with sets of related values and improve code readability and maintainability.
```
  

//Enums

// type keyinput = "up" | "down" | "left" | "right"; or

enum direction {

up ,

down,

left ,

right

}

  

function dosometing( keypassed:direction) {

if(keypassed==direction.down)

{

console.log("up");

}

}

  

dosometing(direction.up);

dosometing(direction.down);

console.log(direction.up);

console.log(direction.down);

dosometing(direction.left);

dosometing(direction.right);
```


### Generics

Generics in TypeScript provide a way to create reusable components that work with a variety of data types while maintaining type safety. They allow you to write code that can handle different types without sacrificing type checking or needing to duplicate code.



### PICK
allows you to create a new type by selecting a set of properties from an existing *TYPE(Type).

```
interface user{
 name : stirng,
 age  : number,
 email: string,
 address:string,
}

type userprofile =Pick<user : userprofile , "name" | "email">;

const display(user : userprofile)
{
console.log(`Name : ${user.name}, email : ${user.email}`)
}
```

### PARTIAL
partial make all the properties optional ,creating a type with same properties
```
interface user{
 name : stirng,
 age  : number,
 email: string,
 address:string,
}

type userprofile =Pick<user : userprofile , "name" | "email">;
type UpdatePropsoptional = Partial<userprofile>;

const display(user : UpdatePropsoptional)
{
console.log(`Name : ${user.name}, email : ${user.email}`)
}
```

### READONLY 
when you have a configuration that object should not be altered after initialisation , making it readonly ensures it values would not change 

```
type user{
readonly name : stirng,
readonly  age  : number,
readonly email: string,
readonly address:string,
}
=====OOORRRR===
type user{
 name : stirng,
  age  : number,
 email: string,
 address:string,
}


const users:readonly<user>={
name = "nikhil",
age=21,
}


~~now users.age =23~~  is not possible 
```


### RECORDS AND MAP
```
type User = {
  name: string;
  age: number;
  email: string;
  address: string;
};

type Users = {
  [key: string]: User;
};

const users: Users = {
  user1: {
    name: "John Doe",
    age: 25,
    email: "john@example.com",
    address: "123 Main St",
  },
  user2: {
    name: "Jane Smith",
    age: 30,
    email: "jane@example.com",
    address: "456 Oak Ave",
  },
  user3: {
    name: "Alice Johnson",
    age: 28,
    email: "alice@example.com",
    address: "789 Pine Rd",
  },
};

console.log(users);

``

```

using records
```
type User = {
  name: string;
  age: number;
  email: string;
  address: string;
};

const usersRecord: Record<string, User> = {
  user1: {
    name: "John Doe",
    age: 25,
    email: "john@example.com",
    address: "123 Main St",
  },
  user2: {
    name: "Jane Smith",
    age: 30,
    email: "jane@example.com",
    address: "456 Oak Ave",
  },
  user3: {
    name: "Alice Johnson",
    age: 28,
    email: "alice@example.com",
    address: "789 Pine Rd",
  },
};

console.log(usersRecord);

```


using MAP

```
type User = {
  name: string;
  age: number;
  email: string;
  address: string;
};

// Creating a Map
const usersMap = new Map<string, User>();

// Adding users
usersMap.set("user1", {
  name: "John Doe",
  age: 25,
  email: "john@example.com",
  address: "123 Main St",
});

usersMap.set("user2", {
  name: "Jane Smith",
  age: 30,
  email: "jane@example.com",
  address: "456 Oak Ave",
});

usersMap.set("user3", {
  name: "Alice Johnson",
  age: 28,
  email: "alice@example.com",
  address: "789 Pine Rd",
});

// Accessing values
console.log(usersMap.get("user1")); // { name: 'John Doe', age: 25, email: 'john@example.com', address: '123 Main St' }

// Checking if a key exists
console.log(usersMap.has("user2")); // true

// Iterating over the Map
usersMap.forEach((user, key) => {
  console.log(`${key}: ${user.name}, ${user.age}`);
});

// Deleting a user
usersMap.delete("user3");

console.log(usersMap);
```

### EXCULDE

if a function that can accepts several type of inputs  but you want to exclude specific types from being passed to it .
```
type AllowedEvents = Exclude<keyof DocumentEventMap, "click">;

function handleEvent(eventType: AllowedEvents) {
  document.addEventListener(eventType, (event) => {
    console.log(`Event: ${eventType}`, event);
  });
}

// ✅ Allowed
handleEvent("scroll");
handleEvent("mousemove");

// ❌ Error: Argument of type '"click"' is not assignable
// handleEvent("click");

```

### TYPE ITERFERENCE IN ZOD

when using zod we are doing runtime validation 
![[Screenshot 2025-02-01 at 12.32.19.png]]


using .infer
![[Screenshot 2025-02-01 at 12.45.57.png]]