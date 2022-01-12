# Advanced JSX

## class vs className

Grammar in JSX is mostly the same as HTML with some slight differences.&#x20;

In HTML, we use class as an attribute name:

```
<h1 class="big">Hello</h1>
```

In JSX, we use className instead:

```
<h1 className="big">Hello</h1>
```

This is because JSX is translated into JS and class is a reserved word in JS. When JSX is rendered, JSX `className` attributes are rendered as `class` attributes.\


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

Any code in between tags of a JSX element will be read as JSX, not regular JS. JSX doesn't add numbers - it reads them as text (like HTML).&#x20;

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
