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



You can also use an ES6 class to define a component:


<img width="560" alt="Screenshot 2024-03-31 124319" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/759e518c-4dbe-4439-9fe8-fcb7e41659d3">


#### The above two components are equivalent from React’s point of view.


### Rendering a Component

Previously, we only encountered React elements that represent DOM tags:

<img width="556" alt="Screenshot 2024-03-31 124548" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/8f65da4b-1c1c-476c-95ef-50b13404e907">

However, elements can also represent user-defined components:


<img width="557" alt="Screenshot 2024-03-31 124617" 
src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/d32cfb1a-0fcf-4623-b920-e325760860cc">


When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object. We call this object “props”.


<img width="566" alt="Screenshot 2024-03-31 124801" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/f7f5579a-e26e-439a-b287-b9d4568bde22">


### Composing Components:

Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.

For example, we can create an App component that renders Welcome many times:


<img width="560" alt="Screenshot 2024-03-31 124912" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/e95c8890-34b4-488d-be30-e165cb0e64bf">


### Extracting Components:

Don’t be afraid to split components into smaller components.


<img width="278" alt="Screenshot 2024-03-31 125145" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/040cccd2-af87-485a-b808-c547c6861449">


It accepts author (an object), text (a string), and date (a date) as props, and describes a comment on a social media website.

This component can be tricky to change because of all the nesting, and it is also hard to reuse individual parts of it. Let’s extract a few components from it.

First, we will extract Avatar:

<img width="565" alt="Screenshot 2024-03-31 125254" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/53b4c719-3782-4112-aa76-0c53f0ae8fc4">


The Avatar doesn’t need to know that it is being rendered inside a Comment. This is why we have given its prop a more generic name: user rather than author.

We recommend naming props from the component’s own point of view rather than the context in which it is being used.

We can now simplify Comment a tiny bit:


<img width="574" alt="Screenshot 2024-03-31 125424" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/4e391578-9165-4b3a-969b-72cf27ddf336">

Next, we will extract a UserInfo component that renders an Avatar next to the user’s name:


<img width="557" alt="Screenshot 2024-03-31 125555" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/a294085f-fa80-424a-91a4-275da8e8e3b3">

This lets us simplify Comment even further:

<img width="554" alt="Screenshot 2024-03-31 125641" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/a1440fa6-61b7-4c03-9204-92897e3d9070">



### Props are Read-Only:

Whether you declare a component as a function or a class, it must never modify its own props. Consider this sum function:

<img width="564" alt="Screenshot 2024-03-31 125809" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/37782c19-e5e4-429b-a762-c27059f1a92c">

Such functions are called “pure” because they do not attempt to change their inputs, and always return the same result for the same inputs.

In contrast, this function is impure because it changes its own input:


<img width="566" alt="Screenshot 2024-03-31 125904" src="https://github.com/iamganeshsalunkhe/REACT.JS/assets/143490640/806fb5a3-1a26-43d2-8248-a2612cb7a460">



React is pretty flexible but it has a single strict rule:

#### All React components must act like pure functions with respect to their props.

Of course, application UIs are dynamic and change over time. In the next section, we will introduce a new concept of “state”. State allows React components to change their output over time in response to user actions, network responses, and anything else, without violating this rule.



### Hooks in REACT