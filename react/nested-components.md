# Nested Components

In React, we can nest components inside within one another. This helps in creating more complex User Interfaces. The components that are nested inside parent components are called child components. Import and Export keywords facilitate nesting of the components.

* Export - This keyword is used to export a particular module or file and use it in another module.
* Import - This keyword is used to import a particular module or file and use it in the existing module.
  * Importing named values allows the user to import multiple objects from a file.

![](<../.gitbook/assets/image (4) (1).png>)

### Create a Floor Plan Using Nested Components

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

1. [Use `import` to import the React library. Save the library in a variable named `React`.](nested-components.md#step-1-import-react)
2. Create a variable called `Bedroom1` returning a `<h1 classname>`
3. Export the component from it's module

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.41.35 AM.png>)

#### Import Bedroom1 Component into FloorPlan

1. [Use `import` to import the React library. Save the library in a variable named `React`.](nested-components.md#step-1-import-react)
2. Use import to import the `Bedroom1` component
3. Create a variable called `Floorplan` returning a `<div classname>`
4. Export the component from it's module

![](<../.gitbook/assets/Screenshot 2022-01-24 at 11.38.19 AM.png>)

#### Import React and FloorPlan Component into App

1. [Use `import` to import the React library. Save the library in a variable named `React`.](nested-components.md#step-1-import-react)
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
