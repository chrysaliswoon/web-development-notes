# Advanced JSX

### class vs className

Grammar in JSX is mostly the same as HTML with some slight differences.

In HTML, we use class as an attribute name:

```
<h1 class="big">Hello</h1>
```

In JSX, we use className instead:

```
<h1 className="big">Hello</h1>
```

This is because JSX is translated into JS and class is a reserved word in JS. When JSX is rendered, JSX `className` attributes are rendered as `class` attributes.

Example of a code which uses className:

```
import React from 'react';
import ReactDOM from 'react-dom';

const myDiv = (
  <div className="big">
    I AM A BIG DIV
  </div>
);

ReactDOM.render(myDiv, document.getElementById('app'))
```

#### ​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FJpjNndxxBqo49X5XzFF1%2Fuploads%2FGEhGOE5cQltBnI7LzIRS%2Fimage.png?alt=media\&token=8657f9ce-71bc-4b50-94b2-249d6a50c981)**CODING TIME**

* Create an index.html and index.js file

{% code title="index.html" %}
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>First React</title>
  
  <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  <script defer src="index.js"></script>
</head>

<body>
  <h1>First React</h1>
  <div id="root"></div>
</body>
</html>
```
{% endcode %}

```
const rootElement = document.getElementById("root");

const element = <h1>Hello World</h1>
console.log(element);

ReactDOM.render(element, document.getElementById("root"));;
```

* Add a `div classname="App"` to the body:

```
<div className="App">
    <h1>Hello CodeSandbox</h1>
    <h2>Start editing to see some magic happen!</h2>
 </div>
```

* Check the element in Chrome Developer Tools and you should see the following:

![](<../.gitbook/assets/image (5).png>)

#### **🏆CODING TIME COMPLETED**

### Self-Closing Tags

Most HTML elements use two tags: an opening tag (`<div>`) and a closing tag (`</div>`). But some HTML elements don't require a closing tag like (`<img>`) and (`<br>`).

In JSX, you **NEED** to include the slash in the closing tag. Otherwise, it will raise an error.

```
Fine in JSX:
 
  <br />
 
NOT FINE AT ALL in JSX:
 
  <br>
```

### Curly Braces

Any code in between tags of a JSX element will be read as JSX, not regular JS. JSX doesn't add numbers - it reads them as text (like HTML).

To get the program to treat it like ordinary JS, we can wrap the code in curly braces like this:

```
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>{2 + 3}</h1>,
  document.getElementById('app')
);
```

This way, it will compute {2 + 3} and output the number "5" instead of giving you the text "2 + 3".

### Variables

You can access variables while inside of a JSX expression event if those variables are declared outside:

```
// Declare a variable:
const name = 'Gerdo';
 
// Access your variable 
// from inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;
```

### Variable Attributes

We use variables when we want to set attributes. For example:

```
// Use a variable to set the `height` and `width` attributes:
 
const sideLength = "200px";
 
const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);
```

Object properties are also used to set attributes like this:

```
const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 
 
const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);
 
const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);
 
const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
); 
```

### Event Listeners

You can create an event listener by giving a JSX element a special attribute:

```
<img onClick={myFunc} />
```

An event listener attribute's name should be something like `onClick`/`onMouseOver`.

An event listener attribute's value should be a function. For example:

```
function myFunc() {
  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}
 
<img onClick={myFunc} />
```

Note: Event listener names are all written in LOWERCASE.
