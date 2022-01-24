# React Components

### What are Components?

At the centre of all react applications are **components**, which is a **piece of the user interface,** so when building applications with react, we build a **bunch of independent, isolated and reusable components** and compose them to build complex UI.

![Visualising React](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/08/building-blocks.png)

Think of a component as a single lego block. These blocks/components are integrated together to **build a bigger and more dynamic application**.

![What is React](https://www.edureka.co/blog/wp-content/uploads/2017/08/JS\_02.png)

The biggest advantage of using components is you can **change any component at any point in time** without affecting the rest of the applications.

![](<../.gitbook/assets/image (4).png>)

To have a better understanding, consider the entire UI as a tree. Here the starting component becomes the root and each of the independent pieces becomes branches, which are further divided into sub-branches.

This keeps our UI organized and allows the data and state changes to logically flow from the root to branches and then to sub-branches.&#x20;

![](<../.gitbook/assets/image (1).png>)

Components make calls to the server directly from the client-side which allows the DOM to update dynamically without refreshing the page. This is because react components are built on the concept of AJAX requests. Each component has its own interface that can make calls to the server and update them. As these components are independent of one another, each can refresh without affecting others or the UI as a whole.

When using React, building Components will be a thing you will do quite often.

### Rules To Follow

From this point on we will be creating Components, more than you ever imagined, so before we begin, let's take a moment to discuss the `requirements` and `best practices` for creating Components.

Some of the requirements are specific to `JSX`, short for `JavaScript And XML`, and will be reviewed again in a later section.

🚔 - Rules (Component Specific)

* They must import `React`
* They must be called within the JSX using an uppercase first letter
* They must return some form of UI (user interface)
* They must be exported from the file to be imported into another Component

🚔 - Rules (JSX Specific)

* They can return only one top level element but that element can contain numerous children.
* Any JS within JSX must be enclosed in curly braces `{}`
* The keyword class is reserved so classes must be renamed `className`

⭐ Best Practices

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

### Create a Floor Plan Using Components

Creating a Floor Plan is a great way to understand and apply our knowledge of React components. Before starting on this activity, create an account at [Code Sandbox](https://codesandbox.io) and create a new React project.

#### ![](<../.gitbook/assets/image (2) (1).png>)**CODING TIME**&#x20;

#### Setting Up Your Files

The React template in Code Sandbox will automatically generate the following files and codes for you:

![](<../.gitbook/assets/Screenshot 2022-01-24 at 10.57.39 AM.png>)

Let's ignore what's inside these boilerplate code first and start thinking about what files we need to create for our Floor Plan.&#x20;

![](<../.gitbook/assets/image (7).png>)

Based on the diagram above, these are the various components we need to create:

* FloorPlan
* Bedroom1
* Bedroom2
* Bedroom3
* FullBath
* HalfBath
* Kitchen
* Oven
* Sink
* LivingRoom

You will notice that the naming for the components are in UpperCamelCase, for example, a `<SomeComponent>` component's file would be named `SomeComponent.js`, and each component has its own file, like FullBath and HalfBath instead of just Bath.&#x20;

![](<../.gitbook/assets/Screenshot 2022-01-24 at 12.02.52 PM.png>)

To visualise each component's wrapping, add the following inside your styes.css.

{% code title="styles.css" %}
```
div {
  border: 1px solid grey;
  margin: 5px;
  padding: 5px;
}
```
{% endcode %}

A border should appear around the div. This will help us identify whether we have structured our components correctly:

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.15.21 AM.png>)

#### Create Bedroom1 Component

1. [Use `import` to import the React library. Save the library in a variable named `React`.](react-components.md#step-1-import-react)
2. Create a variable called `Bedroom1` returning a `<h1 classname>`
3. Export the component from it's module

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.41.35 AM.png>)

#### Import Bedroom1 Component into FloorPlan

1. [Use `import` to import the React library. Save the library in a variable named `React`.](react-components.md#step-1-import-react)
2. Use import to import the `Bedroom1` component
3. Create a variable called `Floorplan` returning a `<div classname>`
4. Export the component from it's module

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.38.19 AM.png>)

#### Import React and FloorPlan Component into App

1. [Use `import` to import the React library. Save the library in a variable named `React`.](react-components.md#step-1-import-react)
2. Use import to import the `FloorPlan` component
3. Remove the `<h1>` and `<h2>` from the \<div section> and replace it with `<FloorPlan />`.

Now your bedroom should appear in your browser!

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.46.50 AM.png>)

#### Create the rest of the FloorPlan components

Now that you know how to import and export the components, create the rest of the FloorPlan components before referencing the solution below:

{% embed url="https://codesandbox.io/s/react-floorplan-6ot1z?file=%2Fsrc%2FLivingRoom.js" %}

**! Note: You will need to adjust your CSS styling so it will look like the one in the diagram**

**Solution to Bonus:** [**https://codesandbox.io/s/react-floor-plan-p77gf?file=/src/styles.css**](https://codesandbox.io/s/react-floor-plan-p77gf?file=/src/styles.css) ****&#x20;

**🏆CODING TIME COMPLETED**
