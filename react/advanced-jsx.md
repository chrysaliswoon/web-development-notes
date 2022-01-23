# Class Names

### class vs className

​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FJpjNndxxBqo49X5XzFF1%2Fuploads%2FGEhGOE5cQltBnI7LzIRS%2Fimage.png?alt=media\&token=8657f9ce-71bc-4b50-94b2-249d6a50c981)**CODING TIME**

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

{% code title="index.js" %}
```
const rootElement = document.getElementById("root");

const element = <h1>Hello World</h1>
console.log(element);

ReactDOM.render(element, document.getElementById("root"));;
```
{% endcode %}

* Add a `div classname="App"` to the body:

{% code title="index.html" %}
```
<div className="App">
    <h1>Hello CodeSandbox</h1>
    <h2>Start editing to see some magic happen!</h2>
 </div>
```
{% endcode %}

* Check the element in Chrome Developer Tools and you should see the following:

![](<../.gitbook/assets/image (5) (1).png>)

* Now let's cut out the whole div class from the HTML file and put it in our js file so it looks like this:

![index.html](<../.gitbook/assets/Screenshot 2022-01-23 at 10.28.59 PM.png>)

![index.js](<../.gitbook/assets/Screenshot 2022-01-23 at 10.29.25 PM.png>)

Take a look at your browser and inspect it. You should see something like this:

![](<../.gitbook/assets/Screenshot 2022-01-23 at 10.26.30 PM.png>)

#### **🏆CODING TIME COMPLETED**

Did you notice that it changed `div classname` to `div class`? Grammar in JSX is mostly the same as HTML with some slight differences.

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
