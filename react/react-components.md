# React Components & Props

### What are Components?

At the centre of all react applications are **components**, which is a **piece of the user interface.**

When building applications with react, we build a **bunch of independent, isolated and reusable components** and compose them to build complex UI.

![Visualising React](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/08/building-blocks.png)

Think of a component as a single lego block. These blocks/components are integrated together to **build a bigger and more dynamic application**.

Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

![What is React](https://www.edureka.co/blog/wp-content/uploads/2017/08/JS\_02.png)

The simplest way to define a component is to write a JavaScript function:

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

This function is a valid React component because it accepts a single **“props”** (which stands for **properties**) object argument with data and returns a React element.&#x20;

We call such components “function components” because they are literally JavaScript functions.

The simplest way to explain component props would be to say that they function similarly to **HTML attributes**.

The biggest advantage of using components is you can **change any component at any point in time** without affecting the rest of the applications.

![](<../.gitbook/assets/image (4) (1) (1).png>)

To have a better understanding, consider the entire UI as a tree. Here the starting component becomes the root and each of the independent pieces becomes branches, which are further divided into sub-branches.

This keeps our UI organized and allows the data and state changes to logically flow from the root to branches and then to sub-branches.&#x20;

![](<../.gitbook/assets/image (1) (1).png>)

Components make calls to the server directly from the client-side which allows the DOM to update dynamically without refreshing the page.&#x20;

This is because react components are built on the concept of AJAX requests.&#x20;

Each component has its own interface that can make calls to the server and update them.&#x20;

As these components are independent of one another, each can refresh without affecting others or the UI as a whole.

When using React, building Components will be a thing you will do quite often.

### Rules To Follow

From this point on we will be creating Components, more than you ever imagined, so before we begin, let's take a moment to discuss the `requirements` and `best practices` for creating Components.

Some of the requirements are specific to `JSX`, short for `JavaScript And XML`, and will be reviewed again in a later section.

**🚔 - Rules (Component Specific)**

* They must import `React`
* They must be called within the JSX using an uppercase first letter
* They must return some form of UI (user interface)
* They must be exported from the file to be imported into another Component

**🚔 - Rules (JSX Specific)**

* They can return only one top level element but that element can contain numerous children.
* Any JS within JSX must be enclosed in curly braces `{}`
* The keyword class is reserved so classes must be renamed `className`

**⭐ Best Practices**

* Each Component should be in it's own file
* Each Component file should be in a separate folder
* Each Component should reference it's own CSS

### How to Create a Component

#### Step 1: Import React

On line 1, use `import` to import the React library. Save the library in a variable named `React`.

```
import React from 'react';
```

This creates an object named `React` which contains methods necessary to use the React library.

Recall that when a JSX element is _compiled_, it transforms into a `React.createElement()` call. For this reason, you _have to_ import the React library, and save it in a variable named `React`, before you can use any JSX at all. `React.createElement()` must be available in order for JSX to work.

#### Step 2: Import ReactDOM

Import the `ReactDOM` library on line 2. Store the result in a variable named `ReactDOM`.

```
import ReactDOM from 'react-dom';
```

The methods imported from `'react-dom'` are meant for interacting with the DOM. You are already familiar with one of them: `ReactDOM.render()`. The methods imported from `'react'` don’t deal with the DOM at all. They don’t engage directly with anything that isn’t part of React.

#### Step 3: Create a Component Class

Skip line 3. On line 4, declare a new _component class_ by writing `class x extends React.Component {}`.

```
class x extends React.Component{}
```

`React.Component` is a JavaScript _class_. To create your own component class, you must _subclass_ `React.Component`. You can do this by using the syntax `class YourComponentNameGoesHere extends React.Component {}`.

#### Step 4: Name a Component Class

Edit your code so that your component class is named `MyComponentClass`.

```
class MyComponentClass extends React.Component{}
```

Subclassing `React.Component` is the way to declare a new _component class_. When you declare a new component class, you need to give that component class a _name._ Component class variable names must begin with capital letters! This adheres to JavaScript’s class syntax.

#### Step 5: Render Function

Place the cursor in between the curly braces at the end of line 4, and hit `return`. On line 5, write a render method. Inside of the render method’s body, write a `return` statement that returns the JSX expression `<h1>Hello world</h1>`.

```
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component{
  render(){
    return <h1>Hello world</h1>
  }
}
```

A component class is like a factory that builds components. It builds these components by consulting a set of instructions, which you must provide. These instructions should take the form of a class declaration body.

The instructions should be written in typical JavaScript [ES2015 class syntax](http://exploringjs.com/es6/ch\_classes.html). There is only one property that you _have to_ include in your instructions: a _render method._

A render method is a property whose _name_ is `render`, and whose _value_ is a function. The term “render method” can refer to the entire property, or to just the function part. A render method must contain a `return` statement. Usually, this `return` statement returns a JSX expression.

#### Step 6: Create a Component Instance

On line 11, create an _instance_ of `MyComponentClass`.

```
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}


<MyComponentClass />
```

To make a React component, you write a _JSX element._ Instead of naming your JSX element something like `h1` or `div` like you’ve done before, give it the same name as a _component class_.&#x20;

#### Step 7: Render A Component

Use `ReactDOM.render` to render `<MyComponentClass />`. For the second argument, pass in `document.getElementById('app')`.

```
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
)
```

In order to render a component, that component needs to have a method named `render`. It _inherited_ a method named `render` from `MyComponentClass`. To call a component’s `render` method, you pass that component to `ReactDOM.render()`.
