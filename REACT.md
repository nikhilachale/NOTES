**REACT - Development**

  

Dynamic webs : LinkedIn Instagram Facebook Youtube

  

DOM represents as a tree of objects

Js was an implementation of Ecma script spec

v8 engine 
js runs in browser has extra functionality to run web APIs or fetch APIs

  

  

React is just an easier way to write HTML,CSS and JS

its a new syntax that under the hood gets converted to HTML,CSS and JS

  

  
[[React fibre architecture]]
  

**STATE & COMPONENT& ReRendering**

  

**State**

an object that represents the current of the app 

it represents the  dynamic things in your app (things that changes ) 

**Components**

how a DOM should render ,given a state,

it is reusable and dynamic ,HTML snippet  that changes the given state

a function that takes props/state as an input  and return you back as an HTML 

COMPONENT can only return a single top level XML,because it makes it easy to do reconciliation

**ReRendering**

a state change triggers a re render 

a re render represents the actual DOM being manipulated when the state changes 

React takes care of ReRendering

minimise the re-renders

a state variable that is being re rendered used inside a component changes,

 a parent component re renders triggers all children  re rendering  

  

to minimise the re rendering push the state down to a component

as much as you can 

react.memo(function ()) used to avoid unnecessary re rendering

memo lets you skip re rendering a  components   when the props are not changed

  

//JSX: a JS file inside which you can write both JS and XML

  

  

// setcount =dispatchsetstate  function ()

…todos=>"[1,2]"

…todos,3=>"[1,2,3]"

settodos(todos) or  settodos(…todos,3)

  

using react.createElement

react.createElement=`<button>

click me<button/>`

  

using jsx

<button>

click me<button/>

  

// anytime parent re-renderes all his children will be reredndered

// on changing state app () will re rendered

  

  

  

  

  

  

npm init

npm install express

  

npm install ; // it will install all the required dependencies one by one

  

  

  

  

  

  

express 

zod ,mongoose ,mongodb 

  

  

KEYS IN REACT

each child in a list should have a unique key prop.

React uses keys to understand how to update the DOM and re-render only the necessary components. Without keys, React may re-render every item in a list even if only one item changes, which is inefficient.

**keys** are a special attribute that help identify which items in a list have changed, are added, or removed. They are crucial for efficiently updating the UI, especially when rendering lists of elements.

  

  

**HOOKS**

  

==The functions that start with use are called hooks== 

hook in react are functions that allows you to “hook into ”react state and life cycle feature from function components

on component mount()_ works similar


# ==**COMMON HOOKS IN  REACT**==
use effect, use callback, use memo, custom hooks ,prop drilling

[[Jargon]]
**side effects **:
in react concept of the side effects on compasses any operation that reach outside the functional scope of the react component ,these operations can affect other components ,interact ,or perform asynchronous data fetching
- Single Page application 
- client side bundle 
- client side routing 



SetTimeout ,setInterval , fetch 

**[[hooks]]**:
introduced in 16.8 , 
that allows you to use state and the other react feature without writing the class. they enable function component to have access to stateful logic and lifecycle features ,which were  previously only possible in the class components, this has led to a more concise and readable way of writing components in react.

In React, useRef, useCallback, useMemo, and useEffect are hooks that serve different purposes, mainly for optimizing performance and managing component lifecycle. Here’s a breakdown of each:

  

**1. useRef**

  

• **Purpose**: useRef is used to create a mutable reference that persists across renders without causing the component to re-render.

• **Use case**: Typically used for storing references to DOM elements or mutable values that need to be accessed without triggering re-renders.

  

**Example:**

  

const inputRef = useRef();

  

function focusInput() {

  inputRef.current.focus(); _// Direct access to the input element without causing a re-render_

}

  

return <input ref={inputRef} />;

  

• **Key points**:

• Does **not** trigger re-renders when its value is updated.

• Can store any mutable value (DOM elements, previous values, etc.).

• It is like an “instance variable” that survives between renders.

  

**2. useCallback**

  

• **Purpose**: useCallback is used to memoize a function, preventing it from being re-created on every render, which is useful when passing functions as props to child components to avoid unnecessary re-renders.

• **Use case**: Used when you want to optimize performance by memoizing callbacks that depend on specific dependencies.

  

**Example:**

  

const handleClick = useCallback(() => {

  console.log("Clicked!");

}, []); _// The function will only be created once since there are no dependencies_

  

return <button onClick={handleClick}>Click me</button>;

  

• **Key points**:

• Returns a memoized version of a function.

• Useful to avoid unnecessary re-creations of functions (especially in child components).

• Should only be used if the function is expensive or is passed to child components that depend on referential equality for optimization.

  

**3. useMemo**

  

• **Purpose**: useMemo is used to memoize the result of an **expensive computation**, so the calculation is only recomputed when its dependencies change.

• **Use case**: Used to optimize performance by avoiding unnecessary recalculations of a value.

  

**Example:**

  

const expensiveCalculation = useMemo(() => {

  return performHeavyComputation(input);

}, [input]); _// Only recompute when 'input' changes_

  

return <div>Result: {expensiveCalculation}</div>;

  

• **Key points**:

• Returns a **memoized value** (the result of the computation).

• Useful when you have expensive operations (like filtering or sorting large datasets) that you don’t want to recalculate on every render.

• Should only be used when performance optimization is necessary.

  

**4. useEffect**

  

• **Purpose**: useEffect is used to run side effects in functional components, such as fetching data, setting up subscriptions, or manually changing the DOM.

• **Use case**: Used for side effects that need to run after rendering or when dependencies change.

  

**Example:**

  

useEffect(() => {

  document.title = `You clicked ${count} times`;

  

  return () => {

    console.log('Cleanup code'); _// Runs when component unmounts or before the effect is re-run_

  };

}, [count]); _// Only re-run when 'count' changes_

  

• **Key points**:

• Runs after the component renders or updates.

• Can return a cleanup function to handle component unmounting or dependency change.

• Useful for tasks like data fetching, subscriptions, or manually interacting with the DOM.

• Runs either **on mount**, **on update**, or **on unmount** depending on the dependencies array ([] = mount only, [dep1, dep2] = run on specific dependency updates).

  

**Summary of Differences:**

  

**Hook** **Purpose** **Common Use Cases** **Triggers Re-renders?**

useRef Stores a mutable reference that doesn’t trigger renders Accessing/manipulating DOM elements or storing mutable data No

useCallback Memoizes a function to prevent unnecessary re-creation Passing stable functions as props or handlers No

useMemo Memoizes the result of an expensive computation Avoiding expensive recalculations No

useEffect Runs side effects after rendering or when dependencies change Fetching data, updating DOM, subscriptions Yes (if state is updated)

  

Each hook has a specific use case, and using them properly can help improve your React app’s performance and behavior.


### **[[Routing]]**
how to do routing 
using react router dom


create a project

[[Paytm]]




