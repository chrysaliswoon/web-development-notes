# Alternatives to CRA & Node Package

### Alternatives to CRA

As CRA bundles a lot of `npm` modules it takes a lot of space. A slimmer alternative is using [Vite](https://vitejs.dev)

```
# npm 6.x
npm init vite@latest my-react-app --template react

# npm 7+, extra double-dash is needed:
npm init vite@latest my-react-app -- --template react
```

Just some notes about using Vite:

* You need `import * as React from "react"` as Vite is not using the latest Babel compiler
* Your files need to end with `.jsx` extension if you're using JSX inside

### Node Packages

![](<../.gitbook/assets/image (2).png>)

* JavaScript was used mainly for client-side scripting inside `<script>` tags executing in web browsers. This limitation meant that developers were often working in many different languages and frameworks between the front-end (client-side) and backend (server-side) aspects of a web application.
* Node allows developers to write JavaScript code that runs directly in a computer process itself instead of in a browser. Node can, therefore, be used to write server-side applications with access to the operating system, file system, and everything else required to build fully-functional applications.
* Node.js is written in C, C++, and JavaScript, and it is built on the open-source [V8](https://developers.google.com/v8/) JavaScript engine which also powers JS in browsers such as Google Chrome. As V8 supports new features in JavaScript, they are incorporated into Node.
* Node.js is an application that lets us run JavaScript outside of the browser and in the terminal. We'll use node.js to build a Single Page Application using React.
* Built into Node.js is something called `npm`-`Node Package Manager`: Manage Node Packages
  * Node packages are libraries (or frameworks - see below) of code that provide useful functionality. Much like jQuery for the browser, node packages help us write sophisticated programs with a lot of useful functionality right out of the box. These packages are published at [www.npmjs.com](https://www.npmjs.com)



These chunks of code fall into one of two categories

* Libraries
  * A collection of functions, objects, and even other libraries that you call
  * It has no idea what you're going to build
* Frameworks
  * Is essentially just a library
  * Is also a pre-conceived skeleton for an application
  * It knows what you're going to build and is somewhat opinionated about how you should do it

### Download our First npm Package

#### ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FJpjNndxxBqo49X5XzFF1%2Fuploads%2FGEhGOE5cQltBnI7LzIRS%2Fimage.png?alt=media\&token=8657f9ce-71bc-4b50-94b2-249d6a50c981)**CODING TIME**

To install (download) a package, first you must know its name (each name is unique in `npm`). Then run:&#x20;

```
npm i eslint
```

In this case, we are installing the library `eslint`.

**🏆CODING TIME COMPLETED**

We can see that we've successfully added because or `package.json` file will have updated (under dependencies)

```
"dependencies": {
  "@testing-library/jest-dom": "^5.14.1",
  "@testing-library/react": "^11.2.7",
  "@testing-library/user-event": "^12.8.3",
  "eslint": "^7.32.0",
  "react": "^17.0.2",
  "react-dom": "^17.0.2",
  "react-scripts": "4.0.3",
  "web-vitals": "^1.1.2"
},
```

Additionally, we see that we now have a directory called `node_modules` and a file called `package-lock.json`

```
flowchart
 subgraph folders
  cra --> node_modules
 end
 subgraph files
  cra --> B["package.json"]
  cra --> C["package-lock.json"]
 end
```

We're not going to edit our `package-lock.json` file, it's just a helper file for `npm` that helps `npm` do some under the hood stuff.

Inside `node_modules` is all the code that was downloaded so we could use `react`, the code is tucked into folders that are managed by npm. Like jQuery, we don't ever have to look at the source code or modify it in any way, it can just sit there and we'll bring in the code and use it in our own files.
