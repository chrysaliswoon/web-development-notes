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

Think of a component as a single lego block. These blocks/components are integrated together to **build a bigger and more dynamic application**.&#x20;

The biggest advantage of using components is you can **change any component at any point in time** without affecting the rest of the applications.

![What is React](https://www.edureka.co/blog/wp-content/uploads/2017/08/JS\_02.png)

#### What is JSX

It is a **syntax extension** for JS. It was written to be used with React.&#x20;

JSX code looks a lot like HTML:

```
const h1 = <h1> Hello world </h1>
```

Syntax extension means that JSX is not valid JS. Web browsers can't read it. If a JS file contains JSX code, that file will need to be **compiled**.

## Introduction to JSX

A basic unit of JSX is called a JSX **element**.

This element looks exactly like HTML, expect that we find it in a JS file instead of a HTML file.

#### JSX Elements & Their Surroundings

JSX elements are treated as JS **expressions**. They can go anywhere that JS expressions can go.&#x20;

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

JSX elements can have **attributes** similar to HTML elements. A JSX attribute written using HTML-like syntax:&#x20;

```
<a href='http://www.example.com'>Welcome to the Web</a>;
 
const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 
```

A single JSX element can have many attributes:

```
const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px' />;
```

#### Nested JSX



#### JSX Outer Elements



#### Rendering JSX



#### ReactDOM.render()



#### Passing a Variable to ReactDOM.render()

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
  * Many companies use React, which&#x20;

## React in MVC

The MVC architecture is a JS design pattern for building applications.&#x20;

![MVC Model](https://rangleio.ghost.io/content/images/2021/04/mvc\_blog\_diagrams\_MVC\_pattern1.png)

* M - Model
  * Database
* V - Views
  * Presentation Layer: What the user sees and interacts with the browser
* C - Controller
  * Makes decisions based on requests and controls what happens in response, like clicking on links and submitting forms.

### Virtual DOM For Efficiency

The `Document Object Model` or _DOM_ for short is an API that is used to interact with the HTML that is displayed on a page.&#x20;

![DOM Structure](https://media.geeksforgeeks.org/wp-content/uploads/20210908120846/DOM.png)

The Virtual DOM is a representation of the actual _DOM_ and is a staging area for changes that will eventually be implemented. Because of that, React can keep track of changes in the actual _DOM_ by comparing different instances of the Virtual DOM.

![Compare Virtual and Real DOM](https://i.imgur.com/xTxgF0b.png)

React then isolates the changes between old and new instances of the Virtual DOM and then only updates the actual DOM with the necessary changes as opposed to re-rendering an entire view altogether which is significantly more efficient.

## Get Started with React

\
\
