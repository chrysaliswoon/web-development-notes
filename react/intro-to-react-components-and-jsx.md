---
description: >-
  Understand what is React, a declarative, efficient, and flexible JavaScript
  library for building user interfaces.
---

# Intro To React, Components and JSX

## What is React?

It is a **JS library** created by **Facebook** for building fast and interactive User Interface (UI).

![Intro. to React](https://www.edureka.co/blog/wp-content/uploads/2017/08/jsx-2.png)

#### Difference between Libraries & Framework

* **Library**: A set of code that was previously written, that can be called upon when building your own code.
* **Framework**: Supporting structure where your own code defines the "meat" of the operations by filling out the structure.

![Difference between Library & Framework](https://csharpcorner-mindcrackerinc.netdna-ssl.com/UploadFile/a85b23/framework-vs-library/Images/DqCkT.png)

#### Components

At the centre of all react applications are **components**, which is a **piece of the user interface,** so when building applications with react, we build a **bunch of independent, isolated and reusable components** and compose them to build complex UI.

![Visualising React](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/08/building-blocks.png)

Think of a component as a single lego block. These blocks/components are integrated together to **build a bigger and more dynamic application**.

The biggest advantage of using components is you can **change any component at any point in time** without affecting the rest of the applications.

![What is React](https://www.edureka.co/blog/wp-content/uploads/2017/08/JS\_02.png)

#### What is JSX

It is a **syntax extension** for JS. It was written to be used with React.

JSX code looks a lot like HTML:

```
const h1 = <h1> Hello world </h1>
```

Syntax extension means that JSX is not valid JS. Web browsers can't read it. If a JS file contains JSX code, that file will need to be **compiled**.

## Introduction to JSX

A basic unit of JSX is called a JSX **element**.

This element looks exactly like HTML, expect that we find it in a JS file instead of a HTML file.

#### JSX Elements & Their Surroundings

JSX elements are treated as JS **expressions**. They can go anywhere that JS expressions can go.

This means that JSX elements can be saved in a variable, passed to a function, stored in an object, etc.

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

## Why Choose React?

There are various reasons why one might choose React, and here are a few:

* Fast
  * Apps made in React can handle complex updates, yet feel quick and responsive.
* Modular
  * You can write smaller, reusable files which is a great solution to JS [maintainability problems](https://en.wikipedia.org/wiki/Spaghetti\_code).
* Scalable
  * React is great for programs that display a lot of changing data.
* Flexible
  * You can us to create interesting projects that isn't a web app.
* Popular
  * Many companies use React, which

## React in MVC

The MVC architecture is a JS design pattern for building applications.

![MVC Model](https://rangleio.ghost.io/content/images/2021/04/mvc\_blog\_diagrams\_MVC\_pattern1.png)

* M - Model
  * Database
* V - Views
  * Presentation Layer: What the user sees and interacts with the browser
* C - Controller
  * Makes decisions based on requests and controls what happens in response, like clicking on links and submitting forms.

### Virtual DOM For Efficiency

The `Document Object Model` or _DOM_ for short is an API that is used to interact with the HTML that is displayed on a page.

![DOM Structure](https://media.geeksforgeeks.org/wp-content/uploads/20210908120846/DOM.png)

The Virtual DOM is a representation of the actual _DOM_ object, like a lightweight copy.

It has the same properties as a real DOM object, but it lacks the real thing's power to directly change what's on the screen.&#x20;

Manipulating the DOM is slow, and it is faster to manipulate the virtual DOM as nothing gets drawn onscreen. Think of manipulating the virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.

When you render a JSX element, every single virtual DOM object gets updated. Because of that, React can keep track of changes in the actual _DOM_ by comparing different instances of the Virtual DOM.

![Compare Virtual and Real DOM](https://i.imgur.com/xTxgF0b.png)

React then isolates the changes between old and new instances of the Virtual DOM and then only updates the actual DOM with the necessary changes as opposed to re-rendering an entire view altogether which is significantly more efficient. This process is called **"diffing"**.

Once React knows which virtual DOM objects have changed, it updates only those objects, on the real DOM. This means that if you render the same thing twice in a row, the second render will do nothing:

```
const hello = <h1>Hello world</h1>;
 
// This will add "Hello world" to the screen:
 
ReactDOM.render(hello, document.getElementById('app'));
 
// This won't do anything at all:
 
ReactDOM.render(hello, document.getElementById('app'));
```

In summary, here’s what happens when you try to update the DOM in React:

1. The entire virtual DOM gets updated.
2. The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
3. The changed objects, and the changed objects only, get updated on the _real_ DOM.
4. Changes on the real DOM cause the screen to change.

## Get Started with React

\
\\
