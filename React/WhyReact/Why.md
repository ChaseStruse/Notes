# Why React?

This is a question I ask regarding all languages and this will help answer that question.

Sections:
[StartOfReact](#start)
[Concepts](#concepts)

## Start of React (Birth of React)
<a name="start"></a>
Release Year: 2013

Prior to react, we had HTML, CSS, and JS. This allowed for basic static sites. Problems arose because each browser reacted differently based on the JS and this was an issue because you would have to use different devs for different browser.

jQuery was born to help alleviate this issue. jQuery allows devs to easily interact with the DOM. Allowed for a unified and easy API and not have to worry about different browsers. 

Once websites began getting bigger, for example Facebook, JS files continued to grow. This started creating issues on how to keep all of these files straight. This is why BackboneJs came out. This was created to help developers not get such a headache when looking at such complex JS. 

Birth of Single Page Application (SPA), this is the start of focusing on JS rather than HTML. Instead of having tons of HTML files for each page you would use JS to update a single HTML file. This allowed for easier development.

2010 Birth of Angular JS

AngularJS allowed developers to create SPA using containers, this was created by Google which helped Angular gain traction and started the trend of MVC (Model View Controller), this was intended to help with organizing code.

Once the websites began getting bigger and greater complexity frameworks like Angular did not allow for easy debugging mostly in part due to the amount of data flowing everywhere, for example on Facebook, you could have over 25 buttons or icons that you could click and based on where you click could change what data flows where and for a developer to debug issues that were bound to arise seemed nearly impossible (I feel like it would be nearly impossible at least).

In 2013 Facebook came out with React. This would allow developers to more efficiently build applications and improve on this issues found with AngularJS. 

## React Concepts
<a name="concepts"></a>
1. React will handle the DOM, no need to worry Chase 
2. Build websites like Lego blocks (AKA Components)
3. One way data flow
4. UI Library, you can figure the rest out

## Keywords

State - Current JSX that is being displayed. Contains things such as loggedIn: true

Props - Variables passed from the state to the component. loggedIn would be a prop.

Components - Where the magic happens, creates the JSX that will be rendered. Just JS functions that are rendered and displayed.

Declarative - Declare what you want to happen.

JSX - Mix between JS and HTML, how the components are rendered to be displayed.

VirtualDOM - Used by React to generate a blueprint to later be used on the real DOM

## Things good React Developers focus on

1. Decide on Components
2. Decide the State and where it lives
3. What changes when state changes

### React will handle the DOM

Prior to React, developers would have to directly interact with the DOM by using commands like GetElementById and etc (didnt want to type all those out, you get the point). 

This was called imperative programming, meaning you interact with individual parts of your app, key word INDIVIDUAL. For example you would have a scenario such as:

Display Friends -> Once Completed -> Display Chat -> Once Completed -> Display Ads

While intuitive it created issues with debugging big projects.

That is why React takes a declarative approach. Allowing for just two major functions rather than doing a bunch of individual interactions. You just need to create the "state" and react will take care of implementing the state on the page. This is why it is declarative, we Declare what we want it to do and React does it. Making it easy to debug because all of the states are within one section. 

### Build websites like Lego blocks

You would create small components, such as you would have a Chat Component, an Ad Component, Story Component, etc. Not only are these a lot better to organize and debug, they also allow for reusability, one of the best terms in programming to hear about your code! I can reuse that ad component across the website with no issue and even if I am on a seperate page I will still only have to debug that one component. 

Component is just JS function or class that takes in props or different data from the state to create JSX. 

### One way data flow

State Change -> State -> Component -> JSX (From Component) -> Virtual DOM

Virtual DOM gives React a blueprint on how to interact with the actual DOM and then React uses that blueprint to create DOM. 

For the page to change, state must change. State changing could be clicking a button or modifying text. 

With the restriction of data only being able to move one way, it makes it easier for developers to trace data and trace bugs. 

### UI Library

AngularJS comes with everything, UI manager, context manager, and all of the backend stuff. 

React only comes with things to control the UI and has you use other libraries to take care of the rest. This is great because it is a lot smaller and is easier to adopt. You can integrate React with almost all JS libraries. React is only there to focus on controlling your UI and ensuring the correct blueprint is being displayed. This is why things like React Native, Redux, etc are there. This is also how you can create react apps on desktop or to interact with the terminal and not just with websites. The epitomy of cross-platform. 