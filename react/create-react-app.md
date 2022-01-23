# Create React App

### What is CRA?

**Create React App (CRA)** is built buy facebook and it is meant for:

* Learning React in a comfortable and feature-rich development environment (good errors! warnings, notes about best practices, hot reloading, zero configuration)
* Starting new single page applications
* Creating Examples with react for your libraries and components

CRA isn't the best choice for:

* a sandbox where you just want to try some samples out&#x20;
* A mostly static site (portfolio, blog) - try Gatsby!
* Server side rendering (yes! With a front-end framework! What is next? Cats and dogs being friends?!) - look into Next.js

### Creating a React App

### Getting Ready

We will be using the _Node package manager (npm)_, so you will need to have _Node_ installed on your computer. To check if you have Node installed, run this command in your terminal:

```
node -v
```

If you have Node installed, this command will return a version number, like `v12.18.1`.

If it’s not already installed, follow the steps in [Setting Up Node Locally](https://www.codecademy.com/content-items/c4fe3060dbc61fc82d810c4ea06c29a8) before moving on.

When you install Node, you automatically get npm installed on your computer as well. However, npm is a separate project from Node.js, and tends to update more frequently. As a result, even if you’ve just installed Node (and therefore npm), it’s a good idea to update your npm. Luckily, npm knows how to update itself!

To upgrade to the latest version of npm on \*nix (OSX, Linux, etc.), you can run this command in your terminal:

```
sudo npm install -g npm@latest
```

To upgrade on Windows, follow the steps found [in the npm documentation](https://docs.npmjs.com/try-the-latest-stable-version-of-npm).

### 1. Setting Up the Boilerplate Application

It is possible to manually create a React app, but Facebook has created a Node package [_create-react-app_](https://create-react-app.dev) to generate a boilerplate version of a React application.

Besides providing something that works out-of-the-box, this has the added benefit of providing a consistent structure for React apps that you will recognize as you move between React projects. It also provides an out-of-the-box build script and development server.

We will use _npx_, a package runner tool that comes with npm 5.2+ and higher, to install and run `create-react-app`. This will ensure that the latest version of create-react-app is used.

Open up your terminal.

*   If you’ve previously installed `create-react-app` globally via `npm install -g create-react-app`, it is recommended that you uninstall the package first. In your terminal run these commands:

    ```
    npm uninstall -g create-react-app
    npx create-react-app myfirstreactapp
    ```
*   If you’ve never installed `create-react-app` before, you can simply run this command:

    ```
    npx create-react-app myfirstreactapp
    ```
*   If you have _Yarn_ installed, `create-react-app` will use it by default to create new projects. If you would prefer to use npm, you can append `--use-npm` to the creation command. It will look like this:

    ```
    npx create-react-app myfirstreactapp --use-npm
    ```

(Feel free to replace `myfirstreactapp` with whatever name you want, as long as it doesn’t contain capital letters :-))

Upon completion, you will get some quick tips on how to use the application:

![createReactAppCommands](https://content.codecademy.com/programs/react/creating-a-react-app/npm\_react\_commands.png)

Before we run the app, let’s take a look around the app structure and see what it contains.
