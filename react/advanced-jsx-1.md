# Advanced JSX

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
