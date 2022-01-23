# Starting with JSX

## Introduction to JSX

#### What is JSX

It is a **syntax extension** for JS. It was written to be used with React. A basic unit of JSX is called a JSX **element**.

This element looks exactly like HTML, expect that we find it in a JS file instead of a HTML file.

```
const h1 = <h1> Hello world </h1>
```

Syntax extension means that JSX is not valid JS. Web browsers can't read it. If a JS file contains JSX code, that file will need to be **compiled**.

#### JSX Elements & Their Surroundings

JSX elements are treated as JS **expressions**. They can go anywhere that JS expressions can go. This means that JSX elements can be saved in a variable, passed to a function, stored in an object, etc.

Example of JSX element in a variable:

```
const navBar = <nav>I am a nav bar</nav>;
```

Example of JSX element in an object:

```
const myTeam = {
  center: <li>Benzo Walli</li>,
  powerForward: <li>Rasha Loa</li>,
  smallForward: <li>Tayshaun Dasmoto</li>,
  shootingGuard: <li>Colmar Cumberbatch</li>,
  pointGuard: <li>Femi Billon</li>
};
```

#### Attributes in JSX

JSX elements can have **attributes** similar to HTML elements. A JSX attribute written using HTML-like syntax:

```
<a href='http://www.example.com'>Welcome to the Web</a>;
 
const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 
```

A single JSX element can have many attributes:

```
const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px' />;
```

#### Nested JSX

Just like HTML, you can also nest JSX elements. But if it takes up more than one line, you will need to wrap the multi-line JSX expression in parentheses:

```
(
  <a href="https://www.example.com">
    <h1>
      Click me!
    </h1>
  </a>
)
```

Nested JSX expressions can be saved as variables, passed to functions, just like non-nested JSX expressions:

```
 const theExample = (
   <a href="https://www.example.com">
     <h1>
       Click me!
     </h1>
   </a>
 );
```

_Note: We use parentheses around multi-line JSX expressions to avoid JS automatic semicolon insertion which adds semicolons to terminate statements which we don't necessarily want that behaviour in a JSX expression._

#### JSX Outer Elements

A JSX expression must have exactly ONE outermost element. The first opening tag and the final closing tag of a JSX expression must belong to the same JSX element.

This code will not work:

```
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```

We need to add an element outside like this:

```
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);
```

#### Rendering JSX

To render a JSX expression means we are making it appear onscreen:

```
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(<h1>Hello world</h1>, document.getElementById('app'));
```

Output:

![](<../.gitbook/assets/Screenshot 2022-01-12 at 9.34.19 PM.png>)

`ReactDOM` is the **name** of a JS library. This library contains several React-specific methods.

`ReactDOM.render()` **renders** the JSX. It takes a JSX expression, creates a corresponding tree of DOM nodes, and adds that tree to the DOM.

`<h1>Hello world</h1>` is the **argument** being passed to `ReactDOM.render().`

`document.getElementById('app')` acted as a container for `ReactDOM.render()`'s first argument.

`ReactDOM.render()` first argument should evaluate to a JSX expression, which means it can also be a variable:

```
const toDoList = (
  <ol>
    <li>Learn React</li>
    <li>Become a Developer</li>
  </ol>
);
 
ReactDOM.render(
  toDoList, 
  document.getElementById('app')
);
```

The compiling is handled by [Babel](https://babeljs.io), a JS compiler. It converts ECMAScript intro a backwards compatible version of JS in current and older browsers or environments.
