# REACT.JS

### React is a JavaScript library for building user interfaces.

#### Add React to a Website


You can add React to an HTML page in one minute. You can then either gradually expand its presence, or keep it contained to a few dynamic widgets.

#### Create a New React App
When starting a React project, a simple HTML page with script tags might still be the best option. It only takes a minute to set up!


As your application grows, you might want to consider a more integrated setup. There are several JavaScript toolchains we recommend for larger applications. Each of them can work with little to no configuration and lets you take full advantage of the rich React ecosystem.

#### The smallest React example looks like this:


<img width="560" alt="Screenshot 2024-03-26 162422" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/d1ac596f-aac2-4035-9e3d-98714d292922">


#### What is JSX?


<img width="547" alt="Screenshot 2024-03-26 162649" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/a4a91c16-db7a-4cce-981e-69e851646a36">

This funny tag syntax is neither a string nor HTML.

It is called JSX, and it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

JSX produces React “elements”.

#### why JSX?

React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both. We will come back to components in a further section, but if you’re not yet comfortable putting markup in JS, this talk might convince you otherwise.

React doesn’t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.


#### JSX is an Expression Too


After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.


This means that you can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments, and return it from functions.


#### JSX Represents Objects


Babel compiles JSX down to React.createElement() calls.


These two examples are identical:


<img width="568" alt="Screenshot 2024-03-26 163158" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/adc78507-4819-4af2-bf6c-d9d6abca408a">



<img width="560" alt="Screenshot 2024-03-26 163222" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/b9a133db-9624-4034-b5ed-772dabb8bc45">


React.createElement() performs a few checks to help you write bug-free code but essentially it creates an object like this:


<img width="563" alt="Screenshot 2024-03-26 163402" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/b3fa02af-98ae-4b26-b09a-bed634cb3b3e">


These objects are called “React elements”. You can think of them as descriptions of what you want to see on the screen. React reads these objects and uses them to construct the DOM and keep it up to date.


### Rendering Elements

Elements are the smallest building blocks of React apps.

An element describes what you want to see on the screen.


Unlike browser DOM elements, React elements are plain objects, and are cheap to create. React DOM takes care of updating the DOM to match the React elements.

#### Rendering an Element into the DOM


Let’s say there is a <div> somewhere in your HTML file:

<img width="559" alt="Screenshot 2024-03-26 163700" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/610224d7-012a-46c2-8062-69efdb7e807e">


We call this a “root” DOM node because everything inside it will be managed by React DOM.


Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.


To render a React element, first pass the DOM element to ReactDOM.createRoot(), then pass the React element to root.render():


<img width="563" alt="Screenshot 2024-03-26 163402" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/efe30859-7397-4da4-a00a-7a6291e90f18">

It displays “Hello, world” on the page.


#### Updating the Rendered Element:


React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.


With our knowledge so far, the only way to update the UI is to create a new element, and pass it to root.render().


Consider this ticking clock example:


<img width="578" alt="Screenshot 2024-03-26 164019" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/f1c32df6-617d-4855-92a7-df2331f91ff3">

#### React Only Updates What’s Necessary:


React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.

![granular-dom-updates](https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/7b9022d0-4239-4320-8b88-06cac95dfc52)


Even though we create an element describing the whole UI tree on every tick, only the text node whose contents have changed gets updated by React DOM.

In our experience, thinking about how the UI should look at any given moment, rather than how to change it over time, eliminates a whole class of bugs.


### Function and Class Components:

The simplest way to define a component is to write a JavaScript function:
<img width="519" alt="Screenshot 2024-03-29 150052" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/7820f11b-43ec-4c20-8bc2-e9989cf3b9ec">




This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.

