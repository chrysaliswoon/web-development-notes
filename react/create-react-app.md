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

#### ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FJpjNndxxBqo49X5XzFF1%2Fuploads%2FGEhGOE5cQltBnI7LzIRS%2Fimage.png?alt=media\&token=8657f9ce-71bc-4b50-94b2-249d6a50c981)**CODING TIME**

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
    npx create-react-app cra
    ```
*   If you have _Yarn_ installed, `create-react-app` will use it by default to create new projects. If you would prefer to use npm, you can append `--use-npm` to the creation command. It will look like this:

    ```
    npx create-react-app cra
    ```

Feel free to replace `cra` with whatever name you want like `myfirstreact`, as long as it doesn’t contain capital letters&#x20;

Upon completion, you will get some quick tips on how to use the application:

![createReactAppCommands](https://content.codecademy.com/programs/react/creating-a-react-app/npm\_react\_commands.png)

* Once it has installed. Run the following commands in your terminal:
  * `cd cra`
  * `rm -rf .git` - because we are in the class repository - no git reps inside other git repos!
  * in the other open tab `code .`
* Change directories into the app you just created, and open the app in the text editor of your choice. You should see the following file structure:

```
flowchart
 subgraph folders
  cra --> public
  cra --> src
 end
 subgraph files
  cra --> A[".gitignore"]
  cra --> B["package.json"]
  cra --> C["package-lock.json"]
  cra --> D["README.md"]
 end
```

If we take a look at the folders:

```
flowchart
  cra --> public
  public --> p1["favicon.ico"]
  public --> p2["index.html"]
  public --> p3["manifest.json"]
  cra --> src
  src --> s1["App.css"]
  src --> s2["App.js"]
  src --> s3["App.test.js"]
  src --> s4["index.css"]
  src --> s5["index.js"]
  src --> s6["logo.svg"]
  src --> s7["reportWebVitals.js"]
  src --> s8["setupTests.js"]
```

**What do the different files mean and do?**

* `package.json` - This file outlines all the settings for the React app.
  * `name` is the name of your app
  * `version` is the current version
  * `"private": true` is a failsafe setting to avoid accidentally publishing your app as a public package within the npm ecosystem.
  * `dependencies` contains all the required Node modules and versions required for the application. In the picture above, you’ll see six dependencies. The first three, as you may have guessed, are for the purpose of testing. The next two dependencies allow us to use `react` and `react-dom` in our JavaScript. Finally, `react-scripts` provides a useful set of development scripts for working with React. In the screenshot above, the `react` version specified is `^16.13.1`. This means that npm will install the most recent major version matching 16.x.x. In contrast, you may also see something like `~1.2.3` in **package.json**, which will only install the most recent minor version matching 1.2.x.
  * `scripts` specifies aliases that you can use to access some of the react-scripts commands in a more efficient manner. For example, running `npm test` in your command line will run `react-scripts test --env=jsdom` behind the scenes.
  * You will also see two more attributes, `eslintConfig` and `browserslist`. Both of these are Node modules having their own set of values. `browserslist` provides information about browser compatibility of the app, while `eslintConfig` takes care of the [code linting](https://stackoverflow.com/questions/8503559/what-is-linting).
* `node_modules` - This directory contains dependencies and sub-dependencies of packages used by the current React app, as specified by **package.json**.&#x20;
  *   If you take a look, you may be surprised by how many there are.

      Running `ls -1 | wc -l` within the **node\_modules/** directory will yield more than 800 subfolders. This folder is automatically added to the **.gitignore** for good reason! Don’t worry, even with all these dependencies, the basic app will only be around 50 KB after being [minified](https://techterms.com/definition/minification) and compressed for production.
* `package-lock.json` - This file contains the exact dependency tree installed in **node\_modules/**. This provides a way for teams working on private apps to ensure that they have the same version of dependencies and sub-dependencies. It also contains a history of changes to **package.json**, so you can quickly look back at dependency changes.
* `public` - **** This directory contains assets that will be served directly without additional processing by webpack. **index.html** provides the entry point for the web app. You will also see a favicon (header icon) and&#x20;
* `manifest.json`. - The manifest file configures how your web app will behave if it is added to an Android user’s home screen (Android users can “shortcut” web apps and load them directly from the Android UI). You can read more about it [here](https://developers.google.com/web/fundamentals/engage-and-retain/web-app-manifest/).
*   `src` - **** This contains the JavaScript that will be processed by webpack and is the heart of the React app. Browsing this folder, you see the main App JavaScript component (**App.js**), its associated styles (**App.css**), and test suite (**App.test.js**). **index.js** and its styles (**index.css**) provide an entry into the App and also kick off the **registerServiceWorker.js**. This service worker takes care of caching and updating files for the end-user. It allows for offline capability and faster page loads after the initial visit. More of this methodology is available [here](https://developers.google.com/web/fundamentals/primers/service-workers).



As your React app grows, it is common to add a **components/** directory to organize components and component-related files and a **views/** directory to organize React views and view-related files.

### 3. Starting the React App Development Server

Run the following code in the terminal: `npm start`

As was stated in the success message when you ran `create-react-app`, you just need to run `npm start` in your app directory to begin serving the development server.&#x20;

It should auto-open a tab in your browser that points to `http://localhost:3000/` (if not, manually visit that address). You will find yourself looking at a page resembling the following image:

![](<../.gitbook/assets/image (5).png>)

As stated, any changes to the source code will live-update here. Let’s see that in action:

* Leave the current terminal tab running (it’s busy serving the React app) and open **src/App.js**.&#x20;

You’ll see what looks like a mashup of JavaScript and HTML. This is _JSX_, which is how React adds XML syntax to JavaScript.&#x20;

It provides an intuitive way to build React components and is compiled to JavaScript at runtime. We’ll delve deeper into this in other content, but for now, let’s make a simple edit and see the update in the browser.

*   Remove the text inside the `p` tag and put some of your own words like:&#x20;

    ```
    <p>Pleased to meet you</p>
    ```
*   Save the file and look at the browser again:

    ![](<../.gitbook/assets/image (3).png>)
*   Let's remove all the create react app showcase stuff and rewrite our component to be a function:&#x20;

    ```
    function App() {
      return <h1>Hello World</h1>
    }
    ```

Your final App.js code should look like this:

![](<../.gitbook/assets/Screenshot 2022-01-23 at 10.03.58 PM.png>)

Now your browser should show this:

![](<../.gitbook/assets/Screenshot 2022-01-23 at 10.04.56 PM.png>)

**🏆CODING TIME COMPLETED**
