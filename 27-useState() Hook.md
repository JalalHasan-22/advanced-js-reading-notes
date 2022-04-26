# Read class 27: useState() Hook


## What are hooks and why to use them ?

### What is a Hook?
A Hook is a special function that lets you “hook into” React features. For example, useState is a Hook that lets you add React state to function components. We’ll learn other Hooks later.

### When would I use a Hook? 
If you write a function component and realize you need to add some state to it, previously you had to convert it to a class. Now you can use a Hook inside the existing function component. We’re going to do that right now!

Hooks let you use React features (like state) from a function — by doing a single function call. React provides a few built-in Hooks exposing the “building blocks” of React: state, lifecycle, and context.
Since Hooks are regular JavaScript functions, you can combine built-in Hooks provided by React into your own “custom Hooks”. This lets you turn complex problems into one-liners and share them across your application or with the React community.

Note that custom Hooks are not technically a React feature. The possibility of writing your own Hooks naturally follows from the way Hooks are designed.

## Rules of Hooks
Hooks are JavaScript functions, but they impose two additional rules:

- Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions.

We provide a linter plugin to enforce these rules automatically. We understand these rules might seem limiting or confusing at first, but they are essential to making Hooks work well.

## The useState hook
The React useState Hook allows us to track state in a function component.
State generally refers to data or properties that need to be tracked in an application.

To use the useState Hook, we first need to import it into our component just like the following example:
> import { useState } from "react";

After the import, We initialize our state by calling useState in our function component.

useState accepts an initial state and returns two values:

- The current state.
- A function that updates the state.

> import { useState } from "react";<br>
>function FavoriteColor() {<br>
>const [color, setColor] = useState("");<br>
>}

Notice that again, we are destructuring the returned values from useState.

The first value, color, is our current state.

The second value, setColor, is the function that is used to update our state.

Lastly, we set the initial state to an empty string: useState("").


### Read State
We can now include our state anywhere in our component.

> import { useState } from "react";<br>
> import ReactDOM from "react-dom/client";<br>
>function FavoriteColor() {<br>
>const [color, setColor] = useState("red");<br>
  return \<h1>My favorite color is {color}!\</h1><br>
>}<br><br>
>const root = ReactDOM.createRoot(document.getElementById('root'));<br>
>root.render(<FavoriteColor />);

### What Can State Hold

The useState Hook can be used to keep track of strings, numbers, booleans, arrays, objects, and any combination of these!
We could create multiple state Hooks to track individual values.