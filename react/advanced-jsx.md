# Advanced JSX

## class vs className

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

​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FJpjNndxxBqo49X5XzFF1%2Fuploads%2FGEhGOE5cQltBnI7LzIRS%2Fimage.png?alt=media\&token=8657f9ce-71bc-4b50-94b2-249d6a50c981)**CODING TIME**

\


## Self-Closing Tags

Most HTML elements use two tags: an opening tag (`<div>`) and a closing tag (`</div>`). But some HTML elements don't require a closing tag like (`<img>`) and (`<br>`).

In JSX, you **NEED** to include the slash in the closing tag. Otherwise, it will raise an error.

```
Fine in JSX:
 
  <br />
 
NOT FINE AT ALL in JSX:
 
  <br>
```

## Curly Braces

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

## Variables

You can access variables while inside of a JSX expression event if those variables are declared outside:

```
// Declare a variable:
const name = 'Gerdo';
 
// Access your variable 
// from inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;
```

#### Variable Attributes

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

## Event Listeners

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
