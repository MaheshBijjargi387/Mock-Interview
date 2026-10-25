# What is JavaScript, and why is it used in web development?
-> JavaScript is a high-level programming language primarily used to make web applications interactive and dynamic. It allows us to handle user events, manipulate the DOM, validate forms, communicate with APIs, and dynamically update the UI. It can also be used on the server side with environments like Node.js.

# What is the difference between var, let, and const in JavaScript?
->var, let, and const are used to declare variables in JavaScript.
var is function-scoped and can be redeclared and reassigned.
let is block-scoped and can be reassigned but cannot be redeclared in the same scope.
const is block-scoped and cannot be reassigned or redeclared after initialization.

# What is the difference between == and === in JavaScript?
->== compares values after type conversion, while === compares both value and data type without type conversion.

# What are the different data types in JavaScript?
->JavaScript has two main categories of data types:

Primitive: String, Number, BigInt, Boolean, Undefined, Null, Symbol
Non-primitive: Object
Arrays and functions are also objects in JavaScript.

# What is hoisting in JavaScript?
->Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their scope before the code is executed. Function declarations are also hoisted, so they can be called before they are declared. let and const are hoisted too, but cannot be accessed before their declaration because of the Temporal Dead Zone (TDZ).

# What is the difference between null and undefined?
->undefined means a variable has been declared but no value has been assigned, while null is an intentional value that represents the absence of a value.

# What is a function in JavaScript?
-> A function is a reusable block of code designed to perform a specific task. It can accept inputs called parameters and can return a result.

# What is a callback function?
-> A callback function is a function passed as an argument to another function and executed later, usually after a specific task or event is completed.

# What is a closure in JavaScript?
-> A closure is a function that remembers and can access variables from its outer scope even after the outer function has finished executing.

# What is the difference between function declaration and function expression?
-> A function declaration defines a function directly and is hoisted, while a function expression stores a function inside a variable and cannot be used before the assignment is executed.

# What is an arrow function?
-> An arrow function is a shorter way to write a function in JavaScript. It does not have its own this, arguments, or super.

# What is the this keyword in JavaScript?
-> this is a special keyword in JavaScript that refers to the object that is currently calling or executing the function. Its value depends on how the function is called.

# What is the difference between synchronous and asynchronous JavaScript?
-> Synchronous JavaScript executes tasks one after another, while asynchronous JavaScript allows a task to run in the background without blocking the execution of other tasks.

# What is a Promise in JavaScript?
-> A Promise is an object used to handle asynchronous operations in JavaScript. It represents a value that may be available now, in the future, or may fail.

A Promise has three states:
Pending: The operation is still in progress.
Fulfilled: The operation completed successfully and produced a result.
Rejected: The operation failed and produced an error.

# What is async/await in JavaScript?
-> async/await is a way to handle asynchronous operations in a cleaner and more readable manner.

async: Used to declare an asynchronous function. It always returns a Promise.
await: Used inside an async function to wait for a Promise to complete before continuing execution.
If the Promise is fulfilled, await returns the result.
If the Promise is rejected, an error is thrown, which can be handled using try/catch.

async/await makes asynchronous code easier to read and understand compared to using multiple .then() calls.

# What is the difference between Promise.all(), Promise.allSettled(), Promise.race(), and Promise.any()?
-> These are Promise methods used to handle multiple asynchronous operations.

Promise.all(): Waits for all Promises to fulfill. If any one Promise is rejected, the entire operation is rejected.
Promise.allSettled(): Waits for all Promises to finish, whether they are fulfilled or rejected. It returns the result of every Promise.
Promise.race(): Returns the result of the first Promise that settles, whether fulfilled or rejected.
Promise.any(): Returns the result of the first Promise that fulfills. It rejects only when all Promises are rejected.

# What is the DOM in JavaScript?
-> The DOM, or Document Object Model, is a programming interface that represents an HTML document as a tree of objects. JavaScript uses the DOM to access, modify, add, or remove HTML elements and their content, attributes, and styles dynamically.

# What is event bubbling in JavaScript?
->Event bubbling is a process where an event starts from the target element and then propagates upward through its parent elements to the document. It allows parent elements to handle events triggered by their child elements.

# What is event capturing in JavaScript?
->Event capturing is the process where an event travels from the outermost parent element down toward the target element. It is the opposite phase of event bubbling. JavaScript event propagation generally has three phases: capturing phase, target phase, and bubbling phase.

# What is event delegation in JavaScript?
 Event delegation is a technique where we attach a single event listener to a parent element instead of adding separate listeners to each child element. It works because of event bubbling and is useful for improving performance, especially when there are many child elements or dynamically added elements.

# What is the difference between map(), filter(), and reduce()?
-> map() is used to transform each element of an array and returns a new array. filter() is used to select elements that satisfy a condition and returns a new array. reduce() is used to process all elements and combine them into a single result, such as a sum, object, or other value.

# What is the difference between forEach() and map()?
-> forEach() is used to execute a function for each element of an array, but it does not return a new array. map() also executes a function for each element, but it returns a new array containing the transformed results.

# What is the difference between shallow copy and deep copy in JavaScript?
-> A shallow copy creates a new object but nested objects or arrays are still shared with the original object. A deep copy creates a completely independent copy, including nested objects and arrays, so changes in the copy do not affect the original.

# What is the difference between localStorage, sessionStorage, and cookies?
-> localStorage stores data in the browser with no automatic expiration and remains available even after the browser is closed. sessionStorage stores data only for the current browser tab or session and is cleared when that tab is closed. Cookies store small amounts of data and can be sent automatically with HTTP requests to the server.

# What is the difference between call(), apply(), and bind()?
-> call() and apply() are used to call a function with a specific this value. The main difference is that call() accepts arguments individually, while apply() accepts arguments as an array. bind() does not immediately execute the function; instead, it returns a new function with the specified this value and arguments.

# What is the difference between let, const, and var in terms of scope and hoisting?
-> var is function-scoped and is hoisted with an initial value of undefined. let and const are block-scoped and are hoisted but remain in the Temporal Dead Zone (TDZ) until their declaration is reached. let can be reassigned, while const cannot be reassigned after initialization.

# What is the Temporal Dead Zone (TDZ) in JavaScript?
-> The Temporal Dead Zone is the period between entering a block and the point where a let or const variable is declared. During this period, the variable exists but cannot be accessed. Accessing it before its declaration results in a ReferenceError.

# What is the difference between undefined, null, and NaN?
-> undefined means a variable has been declared but has not been assigned a value. null is an intentional assignment that represents the absence of a value. NaN stands for Not-a-Number and represents an invalid or undefined numerical result.

# What is the difference between primitive and non-primitive data types?
-> Primitive data types store a single value and are immutable, such as String, Number, Boolean, Undefined, Null, BigInt, and Symbol. Non-primitive data types are reference-based and can store collections of values, such as Objects, Arrays, and Functions.

# What is an object in JavaScript?
->An object is a non-primitive data type used to store data in the form of key-value pairs. An object can contain properties and methods, and it is commonly used to represent real-world entities and their behavior.

# What is an array in JavaScript?
->An array is a special type of object used to store multiple values in a single variable. Array elements are ordered and accessed using zero-based indexes. Arrays can store values of different data types and provide built-in methods for adding, removing, searching, and processing elements.

# What are JavaScript template literals?
-> Template literals are a way to create strings using backticks. They allow us to embed variables and expressions directly inside a string and also support multi-line strings.

# What is destructuring in JavaScript?
-> Destructuring is a feature that allows us to extract values from arrays or properties from objects and assign them to separate variables. It makes code cleaner and easier to read.

# What is the spread operator in JavaScript?
->The spread operator (...) is used to expand the elements of an array or the properties of an object. It is commonly used to copy or combine arrays and objects and to pass multiple values to a function.

# What is the rest parameter in JavaScript?
-> The rest parameter (...) allows a function to accept any number of arguments and collect them into an array. It is useful when the number of arguments is not known in advance.

# What is the difference between == and === in JavaScript?
-> == is the loose equality operator that compares values after type conversion, while === is the strict equality operator that compares both value and data type without type conversion. In most cases, === is preferred because it provides more predictable comparisons.

# What is the difference between slice() and splice()?
-> slice() is used to extract a portion of an array without modifying the original array. splice() is used to add, remove, or replace elements in an array and it modifies the original array.


# What is the difference between push(), pop(), shift(), and unshift()?
-> push() adds one or more elements to the end of an array. pop() removes the last element from an array. shift() removes the first element from an array. unshift() adds one or more elements to the beginning of an array.

# What is the difference between find(), findIndex(), and includes()?
-> find() returns the first element that satisfies a condition. findIndex() returns the index of the first element that satisfies a condition. includes() checks whether an array contains a specific value and returns either true or false.

# What is the event loop in JavaScript?
-> The event loop is a mechanism that allows JavaScript to handle asynchronous operations even though JavaScript is single-threaded. It continuously checks the call stack and task queues, and when the call stack is empty, it moves waiting callbacks into the call stack for execution. This allows JavaScript to perform non-blocking operations such as API calls, timers, and user events.


# What is setTimeout() in JavaScript?
-> setTimeout() is a browser-provided function used to execute a function after a specified delay. It is asynchronous, so it does not block the execution of the remaining synchronous code. The callback is placed in the task queue and executed by the event loop when the call stack is empty.

# What is the difference between synchronous and asynchronous functions in JavaScript?

Answer: Synchronous functions execute one task at a time and wait for the current task to finish before moving to the next task. Asynchronous functions allow operations such as API calls, timers, or file operations to run without blocking the rest of the program. They are commonly handled using Promises, async/await, and callbacks.

# What is a higher-order function in JavaScript?

Answer: A higher-order function is a function that takes another function as an argument, returns a function as its result, or does both. Higher-order functions are commonly used for functional programming and array operations such as map(), filter(), and reduce().

# What are JavaScript modules?
->JavaScript modules are files that allow code to be divided into smaller, reusable, and maintainable parts. Modules use export to make variables, functions, or classes available and import to use them in another module. They help organize large applications and avoid unnecessary global variables.

# What is the difference between named exports and default exports?
-> A named export allows multiple values to be exported from a module, and they are imported using their exact exported names. A default export allows one main value to be exported from a module, and it can be imported with any name.

# What is the difference between map(), filter(), and reduce()?

Answer: map() transforms each element and returns a new array. filter() selects elements that satisfy a condition and returns a new array. reduce() processes all elements and combines them into a single value. These methods are commonly used for functional programming and array data processing.

# What is garbage collection in JavaScript?
->Garbage collection is an automatic memory management process in JavaScript. It identifies objects that are no longer reachable or being used and automatically releases the memory occupied by them. This helps prevent unnecessary memory usage and memory leaks.

# What is a memory leak in JavaScript?
-> A memory leak occurs when a program keeps references to objects that are no longer needed, preventing the garbage collector from releasing their memory. Common causes include unused event listeners, global variables, timers, and unnecessary references.

# What is the difference between throw, try, catch, and finally?
-> try contains code that may produce an error. catch handles the error when it occurs. throw is used to create and manually raise an error. finally contains code that executes after try and catch, whether an error occurs or not.

# What is strict mode in JavaScript?
-> Strict mode is a feature in JavaScript that enables a stricter set of rules for writing code. It helps identify common coding mistakes, prevents certain unsafe operations, and makes JavaScript code more secure and easier to debug.

# What is a prototype in JavaScript?
->A prototype is an object from which other objects can inherit properties and methods. Every JavaScript object has an internal prototype, which allows objects to share functionality through the prototype chain. This is the basis of JavaScript's inheritance mechanism.

# What is the prototype chain in JavaScript?
The prototype chain is the mechanism JavaScript uses to look for properties and methods when they are not found directly on an object. JavaScript searches the object's prototype, then its prototype's prototype, and continues until it reaches null. This allows objects to inherit properties and methods from other objects.

 # What is the difference between Object.create() and the new keyword?
-> Object.create() creates a new object using a specified object as its prototype. The new keyword creates an object from a constructor function or class, sets its prototype, binds this to the new object, and returns the object.

# What is a constructor in JavaScript?
-> A constructor is a special method used to initialize objects when they are created from a class. It is automatically called when a new object is created using the new keyword. A constructor is mainly used to initialize the object's properties.

# What is class inheritance in JavaScript?
-> Class inheritance is a mechanism that allows one class to inherit properties and methods from another class. The extends keyword is used to create a child class from a parent class, and the super keyword is used to access the parent class's constructor and methods.

# What is the difference between a class and an object in JavaScript?
-> A class is a blueprint or template used to define the properties and methods of objects. An object is an actual instance created from that class. A class defines how an object should behave, while the object represents the actual data.

# What is JSON in JavaScript?
->JSON stands for JavaScript Object Notation. It is a lightweight data format used to store and exchange data between a client and a server. JSON represents data using key-value pairs and arrays. In JavaScript, JSON.stringify() converts a JavaScript object into a JSON string, while JSON.parse() converts a JSON string back into a JavaScript object.

# What is the difference between JSON.parse() and JSON.stringify()?
->JSON.parse() converts a JSON string into a JavaScript object, while JSON.stringify() converts a JavaScript object into a JSON string. JSON.parse() is commonly used when receiving JSON data, and JSON.stringify() is commonly used when sending or storing JavaScript data as JSON.

# What is an API in JavaScript?
->An API, or Application Programming Interface, is a way for different software applications to communicate with each other. In JavaScript, APIs are commonly used to send requests to a server, receive data, and interact with browser features such as the DOM, storage, and geolocation.

# What is the Fetch API in JavaScript?
-> The Fetch API is a built-in JavaScript API used to make HTTP requests and communicate with servers. It is commonly used to perform operations such as GET, POST, PUT, PATCH, and DELETE requests. It works asynchronously and returns a Promise, which can be handled using .then() and .catch() or async/await.

# What are HTTP methods commonly used with JavaScript APIs?
-> The commonly used HTTP methods are:

GET: Retrieves data from the server.
POST: Creates new data on the server.
PUT: Updates or replaces existing data.
PATCH: Partially updates existing data.
DELETE: Removes data from the server.

# What is CORS in JavaScript?
-> CORS stands for Cross-Origin Resource Sharing. It is a browser security mechanism that controls whether a web application from one origin can access resources from another origin. The server uses HTTP headers to specify which origins, methods, and headers are allowed.

# What is the difference between GET and POST requests?
-> GET is used to retrieve data from the server, while POST is used to send data to the server and usually create a new resource. GET parameters are commonly sent through the URL, while POST data is generally sent in the request body. GET requests should be safe and idempotent, while POST requests are generally not idempotent.

# What is the difference between PUT and PATCH?
-> PUT is generally used to completely update or replace an existing resource, while PATCH is used to partially update specific fields of an existing resource. PUT usually sends the complete resource representation, whereas PATCH sends only the changes that need to be applied.

# What is event propagation in JavaScript?
-> Event propagation is the process through which an event travels through the DOM. It has three phases: capturing phase, where the event moves from the parent elements toward the target; target phase, where it reaches the target element; and bubbling phase, where it moves from the target back up through the parent elements.

# What is preventDefault() in JavaScript?
-> preventDefault() is a method used to prevent the browser's default behavior for an event. For example, it can prevent a form from submitting automatically or prevent a link from navigating to another page. It does not stop the event from propagating through the DOM.

# What is stopPropagation() in JavaScript?
->stopPropagation() is a method used to stop an event from propagating further through the DOM. It prevents the event from continuing during the capturing or bubbling phase, but it does not prevent the element's default behavior.

# What is the difference between stopPropagation() and stopImmediatePropagation()?
->stopPropagation() stops the event from propagating to parent or child elements, but other event listeners on the same element can still execute. stopImmediatePropagation() stops the event propagation and also prevents any remaining event listeners on the same element from executing.

# What is the difference between setTimeout() and setInterval()?
->setTimeout() executes a function once after a specified delay, while setInterval() executes a function repeatedly after every specified time interval. Both are asynchronous timer functions and can be stopped using clearTimeout() and clearInterval() respectively.

# What is an IIFE in JavaScript?
-> IIFE stands for Immediately Invoked Function Expression. It is a function that is defined and executed immediately after its creation. IIFEs are commonly used to create a private scope and prevent variables from polluting the global scope.

# What is currying in JavaScript?
-> Currying is a technique of transforming a function that takes multiple arguments into a sequence of functions, where each function takes one argument at a time. It is useful for creating reusable and specialized functions.

# What is memoization in JavaScript?
-> Memoization is an optimization technique where the result of a function is stored so that when the same inputs are provided again, the stored result can be returned instead of calculating it again. It can improve performance for expensive or frequently repeated function calls.

# What is throttling in JavaScript?
-> Throttling is a technique that limits how often a function can execute within a specific time interval. It is commonly used for scrolling, mouse movement, and window resize events to improve performance and prevent excessive function calls.

 # What is lexical scope in JavaScript?
-> Lexical scope means that the accessibility of variables is determined by where they are declared in the source code. A function can access variables from its own scope and its outer scopes, but an outer scope cannot directly access variables declared inside the function.

# What is lexical environment in JavaScript?
->A lexical environment is an internal structure that stores variables and functions defined within a particular scope and maintains a reference to its outer lexical environment. It is the mechanism that allows JavaScript to determine which variables are accessible in a given scope.

# What is React.js?
-> React.js is a JavaScript library used to build user interfaces, especially for single-page applications. It is based on reusable components and uses a virtual DOM to efficiently update the user interface when data changes.

# What are the main features of React.js?
-> The main features of React.js are component-based architecture, reusable components, Virtual DOM, JSX, one-way data flow, state management, event handling, and efficient UI updates. React also supports building single-page applications (SPAs) and provides a large ecosystem of libraries and tools.

# What is JSX in React?
-> JSX stands for JavaScript XML. It is a syntax extension for JavaScript that allows us to write HTML-like code inside JavaScript. JSX makes React components easier to write and understand, and it is converted into regular JavaScript before being executed.

# What is a component in React?
-> A component is a reusable and independent piece of the user interface in React. It can contain its own logic, structure, and styling. Components can accept data through props and manage changing data through state. React applications are built by combining multiple components together.

# What is the difference between functional components and class components in React?
->Functional components are JavaScript functions that return JSX and can use React Hooks for state and lifecycle features. Class components are JavaScript classes that extend React's Component class and use methods such as render() and lifecycle methods. Functional components are preferred in modern React because they are simpler, more concise, and support Hooks.

# What are props in React?
-> Props, short for properties, are used to pass data from a parent component to a child component. Props are read-only, which means a child component should not modify the props it receives. They are mainly used to make components reusable and allow components to communicate with each other.

# What is state in React?
->State is data that belongs to a component and can change over time. When the state changes, React re-renders the component and updates the user interface. State is commonly used to manage things like form inputs, counters, loading status, and user information.

# What is the difference between props and state in React?
->Props are used to pass data from a parent component to a child component, while state is used to manage data within a component. Props are read-only and should not be modified by the receiving component, whereas state can be updated using React's state management mechanisms. Changes in state cause the component to re-render, while changes in props can also cause the receiving component to re-render.

# What is the Virtual DOM in React?
->The Virtual DOM is a lightweight JavaScript representation of the actual DOM. When the state or props of a component change, React creates a new Virtual DOM, compares it with the previous one using reconciliation, and updates only the necessary parts of the actual DOM. This improves rendering efficiency and application performance.

# What is reconciliation in React?
->Reconciliation is the process React uses to compare the previous Virtual DOM with the updated Virtual DOM after a change in props or state. React identifies what has changed and updates only the necessary parts of the actual DOM, which helps make UI updates efficient.

# What is the difference between controlled and uncontrolled components in React?
-> A controlled component is a form element whose value is controlled by React state. An uncontrolled component manages its value internally through the DOM, usually accessed using a ref. Controlled components provide better control and validation, while uncontrolled components can be simpler for basic forms.

# What are React Hooks?
-> React Hooks are functions that allow functional components to use React features such as state, lifecycle behavior, context, and refs without using class components. Common Hooks include useState, useEffect, useContext, useRef, useMemo, useCallback, and useReducer.

# What is useState in React?
->useState is a React Hook used to add and manage state in functional components. It returns two values: the current state value and a function used to update the state. When the state is updated, React re-renders the component to reflect the new value.

# What is useEffect in React?
-> useEffect is a React Hook used to perform side effects in functional components. Side effects include API calls, data fetching, subscriptions, timers, event listeners, and updating the document title. It runs after the component renders, and its behavior can be controlled using a dependency array.

# What is the dependency array in useEffect?
->The dependency array tells React when the useEffect should run again. If it is empty, the effect runs after the initial render. If it contains values, the effect runs when those values change. If the dependency array is omitted, the effect runs after every render.

# What is useRef in React?
->useRef is a React Hook used to store a mutable value that persists across renders without causing a re-render when the value changes. It is commonly used to access DOM elements directly, store previous values, and keep references to values that need to persist between renders.

# What is useContext in React?
->useContext is a React Hook used to access data from a Context directly inside a functional component without passing props through every intermediate component. It is commonly used for theme, authentication information, language settings, and other shared data.

# What is useMemo in React?
-> useMemo is a React Hook used to memoize a calculated value. It stores the result of a calculation and recalculates it only when its dependencies change. It is mainly used to optimize performance by avoiding expensive calculations on every render.

# What is useCallback in React?
->useCallback is a React Hook used to memoize a function. It returns the same function reference between renders until one of its dependencies changes. It is mainly used to prevent unnecessary re-creation of functions and can help optimize performance, especially when passing functions to memoized child components.

# What is React.memo in React?
->React.memo is a higher-order component used to prevent unnecessary re-renders of a functional component. It compares the component's previous and new props, and the component re-renders only when its props have changed. It is mainly useful for optimizing the performance of components that render frequently.

# What is useReducer in React?
->useReducer is a React Hook used to manage complex state logic in functional components. It works with a reducer function, current state, and dispatched actions. The reducer receives the current state and an action, then returns the updated state. It is useful when state changes involve multiple related actions or complex logic.

# What is prop drilling in React?
-> Prop drilling is the process of passing data from a parent component to a deeply nested child component through multiple intermediate components, even when those intermediate components do not need the data. It can make code difficult to maintain. Context API, state management libraries, or component composition can be used to avoid excessive prop drilling.

# What is conditional rendering in React?
-> Conditional rendering means displaying different UI elements or components based on a condition. React commonly uses JavaScript conditions such as if-else, ternary operators, and logical AND (&&) to decide what should be rendered.

# What are keys in React?
->Keys are special attributes used to uniquely identify elements in a list. They help React determine which items have been added, removed, or changed when the list is updated. Keys should be unique among sibling elements and should generally be stable, such as a database ID.

# What is the difference between useMemo and useCallback?

-> useMemo is used to memoize a calculated value, while useCallback is used to memoize a function.

useMemo: Returns a cached value and recalculates it when dependencies change.
useCallback: Returns a cached function reference and creates a new function when dependencies change.

Both are mainly used for performance optimization and should be used when there is a real performance benefit.

# What is the Context API in React?
-> The Context API is a built-in React feature used to share data between components without passing props through every level of the component tree. It consists mainly of createContext, Provider, and useContext. It is commonly used for global or shared data such as authentication, themes, language settings, and user preferences.

# What is React Router?
-> React Router is a library used to handle routing and navigation in React applications. It allows us to display different components for different URLs without reloading the entire page. It is commonly used to build single-page applications (SPAs) with features such as routes, nested routes, dynamic routes, navigation, and protected routes.

# What are protected routes in React?
-> Protected routes are routes that can be accessed only by authenticated or authorized users. Before displaying the protected component, the application checks whether the user is logged in or has the required role or permission. If the condition is not satisfied, the user is usually redirected to a login or unauthorized page.

# What is the difference between client-side routing and server-side routing?
-> Client-side routing is handled by the frontend application, such as React Router, where navigation between pages happens without reloading the entire web page. Server-side routing is handled by the backend server, which receives the request, processes it, and returns a response or page.

# What is lifting state up in React?
-> Lifting state up means moving state from a child component to their common parent component so that multiple child components can share and use the same data.

The parent manages the state and passes the required data and update functions to the child components through props. This helps keep the shared state synchronized between components.

# What is the difference between useEffect and useLayoutEffect in React?
-> Both Hooks are used to perform side effects, but they run at different times.

useEffect: Runs after React has updated the DOM and after the browser has generally had a chance to paint the updated UI. It is preferred for most side effects such as API calls, subscriptions, and timers.
useLayoutEffect: Runs synchronously after the DOM has been updated but before the browser paints the screen. It is useful when we need to measure or modify the DOM before the user sees the update.

# What is a Fragment in React?
-> A Fragment is used to group multiple elements without adding an extra DOM element to the page. React provides Fragment and the shorthand syntax <>...</> for this purpose. Fragments are useful when a component needs to return multiple elements without introducing an unnecessary wrapper such as a <div>.

# What is React.StrictMode?
->React.StrictMode is a development-only feature that helps identify potential problems in a React application. It can intentionally run certain functions or lifecycle-related code more than once in development to detect unexpected side effects. It does not affect the production build.

# What is a Higher-Order Component (HOC) in React?
-> A Higher-Order Component (HOC) is a function that takes a React component as input and returns a new enhanced component. It is used to reuse component logic across multiple components.

# What is forwardRef in React?
-> forwardRef is a React API that allows a parent component to pass a ref to a DOM element or child component. It is useful when the parent needs direct access to something inside the child, such as focusing an input or controlling a DOM element.

# What is useImperativeHandle in React?
->useImperativeHandle is a React Hook used with a ref to customize what a parent component can access from a child component. It is useful when a child needs to expose specific functions, such as focus() or reset(), to its parent instead of exposing the entire DOM element.

# What is the difference between useState and useReducer?
->useState is simpler and is commonly used for managing simple state values. useReducer is useful when state logic is more complex or when multiple state changes are related.

# What is useRef used for in React?
->useRef is mainly used for two purposes: accessing DOM elements directly and storing a mutable value that persists between renders without causing a re-render. For example, it can be used to focus an input field or store a timer ID.

# What is useCallback used for in React?
-> useCallback is used to memoize a function so that React can reuse the same function reference between renders until its dependencies change. It is mainly useful when passing functions to memoized child components and can help prevent unnecessary re-renders.

# What is useMemo used for in React?

-> useMemo is used to memoize a calculated value. It stores the result of a calculation and recalculates it only when its dependencies change. It is mainly useful for avoiding expensive calculations on every render.

# What is the difference between useEffect and useMemo?
->useEffect is used to perform side effects such as API calls, timers, and subscriptions. useMemo is used to memoize a calculated value and avoid repeating an expensive calculation unnecessarily.

# What is React's reconciliation process?
->Reconciliation is the process React uses to compare the previous UI representation with the new one after state or props change. React determines the minimum necessary changes and updates the actual DOM accordingly. Keys help React correctly identify elements when rendering lists.

# What is conditional rendering in React?
-> Conditional rendering means displaying different UI elements based on a condition. In React, we can use if-else, ternary operator (? :), or logical AND (&&) to conditionally render components or elements.

# What is conditional rendering with the ternary operator in React?
->The ternary operator is a short way to render one of two UI elements based on a condition.
If isLoggedIn is true, React renders Dashboard; otherwise, it renders Login.

# What is event handling in React?
->Event handling in React is the process of responding to user actions such as clicking, typing, submitting a form, or hovering. React uses camelCase event names like onClick and onChange, and we pass a function as the event handler.

# What is SyntheticEvent in React?
-> SyntheticEvent is React's wrapper around the browser's native event. It provides a consistent event interface across different browsers and works similarly to native events.

For example, events like onClick, onChange, and onSubmit receive a React SyntheticEvent object.

# What is the difference between React and Angular?
->React is a JavaScript library mainly focused on building user interfaces, while Angular is a full-featured TypeScript framework for building web applications. React gives developers more flexibility to choose additional libraries, while Angular provides many features such as routing, forms, HTTP services, and dependency injection as part of its framework.

# What is Redux in React?

Answer: Redux is a state management library used to manage and share application state in a centralized store. Components can access the shared state and dispatch actions to update it. Redux is useful when many components need to access or modify the same data, such as user authentication, shopping carts, or application settings.

# What is Redux Toolkit in React?
->Redux Toolkit (RTK) is the official recommended way to write Redux logic. It simplifies Redux development by providing tools such as configureStore, createSlice, and createAsyncThunk. It reduces boilerplate code and makes state management easier and more organized.

# What is a Redux store?
-> A Redux store is a centralized place where the application's global state is stored. It holds the current state, allows components to access that state, and updates the state when actions are dispatched through reducers.

# What is a Redux action?
-> A Redux action is a plain JavaScript object that describes what happened in the application. It usually contains a type and may also contain a payload with additional data.

# What is a Redux reducer?
-> A Redux reducer is a pure function that receives the current state and an action, then returns the new state. It contains the logic that determines how the state should change when an action is dispatched.

# What is createSlice in Redux Toolkit?

-> createSlice is a Redux Toolkit function used to create a slice of Redux state along with its reducers and actions in one place. It reduces boilerplate code and automatically generates action creators based on the reducers we define.

# What is useSelector in React Redux?
->useSelector is a React Redux Hook used to read data from the Redux store inside a functional component. It allows the component to access a specific part of the global state.

# What is useDispatch in React Redux?
->useDispatch is a React Redux Hook used to dispatch actions to the Redux store. It allows a component to trigger state changes by sending an action.

Example:

# What is Provider in React Redux?
->Provider is a React Redux component that makes the Redux store available to all components in the application. We usually wrap the root component with Provider and pass the Redux store to it.

# What is createAsyncThunk in Redux Toolkit?
->createAsyncThunk is used to handle asynchronous operations in Redux, such as API calls. It automatically creates action states for pending, fulfilled, and rejected, making it easier to manage loading, success, and error states.

# What is createEntityAdapter in Redux Toolkit?
-> createEntityAdapter is a Redux Toolkit utility used to manage collections of entities such as users, products, or orders efficiently. It provides predefined methods for adding, updating, removing, and selecting entities, which reduces the amount of Redux code we need to write.

# What is Redux middleware?
-> Redux middleware is a mechanism that allows us to intercept and process actions before they reach the reducer. It is commonly used for asynchronous API calls, logging, error handling, and other side effects.

# What is Redux middleware used for?
->Redux middleware is mainly used to handle side effects and additional logic between dispatching an action and reaching the reducer. Common uses include API calls, asynchronous operations, logging, and error handling.

Examples include Redux Thunk and Redux Saga.

# What is React Query (TanStack Query)?
->TanStack Query is a library used to manage server state in React applications. It simplifies fetching, caching, synchronizing, and updating data from APIs. It also helps handle loading, error, caching, refetching, and stale data automatically.

# What is the difference between client state and server state in React?
-> Client state is data managed within the application, such as form values, UI settings, and whether a menu is open. Server state is data that comes from a backend or API, such as users, products, and orders.

Client state can be managed with useState, Context, or Redux, while server state is often managed with tools such as TanStack Query.

# What is the difference between Redux and Context API in React?
-> Context API is mainly used to share data between components without passing props through every level. Redux is a dedicated state management library that provides a centralized store and structured ways to manage complex application state.

For simple shared data, Context API may be enough. For large applications with complex state and many updates, Redux Toolkit is often more suitable.

# What is a custom Hook in React?
-> A custom Hook is a reusable JavaScript function that starts with use and can use other React Hooks. It allows us to extract and reuse common logic between components.

# What are the Rules of Hooks in React?
-> The main Rules of Hooks are:
Only call Hooks at the top level — don't call them inside loops, conditions, or nested functions.
Only call Hooks from React functions — use them inside functional components or custom Hooks.


