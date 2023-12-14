# React technical interview

## What is React ?

- ReactJS, commonly known as React, is a JavaScript library for building user interfaces.
- Created by Facebook in 2011.
- It is maintained by Facebook and a community of developers.
- React is primarily used for creating single-page applications where user interfaces need to be interactive and dynamic.
- The library allows developers to build UI components that update efficiently and respond to changes in data.

Key features and concepts of React include:

1. **Declarative Syntax:** React uses a declarative syntax that makes it easy to understand and reason about the structure of a user interface. Developers describe how the UI should look at any given point, and React takes care of updating the DOM to match that description.

2. **Component-Based Architecture:** React applications are built using components. Each component is a self-contained, reusable piece of the user interface that manages its own state and behavior. Components can be composed to build complex UIs.

3. **Virtual DOM:** React uses a virtual representation of the DOM (Virtual DOM) to optimize updates. Instead of directly manipulating the actual DOM for every change, React compares the virtual DOM with the real DOM and updates only the parts that have changed, leading to improved performance.

4. **React Router:** React Router is a library that provides client-side routing for React applications. It enables the creation of single-page applications with multiple views, each corresponding to a different URL.

5. **State Management:** React allows the management of local component state, making it easy to create dynamic and interactive user interfaces. With the introduction of hooks, functional components can now also manage state, providing a more concise syntax.

6. **Reusable Components:** React promotes the concept of reusability. Components can be easily reused across different parts of an application or even in different projects, enhancing maintainability and scalability.

7. **Unidirectional Data Flow:** React follows a unidirectional data flow, meaning that data flows in a single direction, from parent components to child components. This makes it easier to understand how data changes and updates propagate through the application.

8. **React Hooks:** Introduced in React 16.8, hooks allow developers to use state and other React features in functional components, eliminating the need for class components in many cases.

React is widely used in the development of modern web applications, and its popularity has led to the creation of a robust ecosystem of libraries and tools that complement its capabilities. Additionally, React can be integrated with other libraries and frameworks as needed, making it a versatile choice for building user interfaces.

## Basic Concepts

### 1. **Explain the Virtual DOM in React and how it improves performance.**

The Virtual DOM is a lightweight copy of the real DOM. React uses it to minimize direct manipulation of the actual DOM, which is an expensive operation. By updating the Virtual DOM and then efficiently updating the real DOM, React reduces the number of manipulations needed, resulting in improved performance.

### 2. **What is JSX, and how does it differ from HTML? Provide an example of JSX code.**

JSX is a syntax extension for JavaScript recommended by React.

It's XML/HTML with JaveScript.

Babel compile JSX into JS.

Example:

```jsx
const element = <h1>Hello, React!</h1>;
```

### **3. Describe the purpose of React components. What are functional components and class components?**

React components are reusable, self-contained building blocks for UI elements. Functional components are stateless and simply return JSX, while class components can manage state and have lifecycle methods. With the introduction of hooks, functional components can now handle state and lifecycle events.

## Component Lifecycle

### 4. **Explain the lifecycle methods of a React component. Name some of the key lifecycle methods and describe when they are called.**

Key lifecycle methods include `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`. `componentDidMount` is called after the component is rendered, `componentDidUpdate` after an update, and `componentWillUnmount` before a component is removed.

### 5. **What is the significance of `componentDidMount`? How is it different from `componentDidUpdate`?**

`componentDidMount` is called after a component is rendered to the DOM, commonly used for API calls or subscriptions. `componentDidUpdate` is called when the component updates, allowing for actions after a re-render.

### 6. **How would you optimize a React application's performance?**

Optimization strategies include using the Virtual DOM, minimizing unnecessary renders, code splitting, lazy loading, and implementing shouldComponentUpdate or React.memo for pure components.

## State and Props

### 7. **Differentiate between state and props in React. When would you use one over the other?**

State is internal to a component and can be changed by the component itself, while props are external inputs passed to a component. Use state for values that can change, and props for values passed down from parent components.

### 8. **How can you update the state of a component? Provide an example of using `setState`.**

`setState` is used to update a component's state. Example:

```jsx
this.setState({ count: this.state.count + 1 });
```

### 9. **Explain the concept of lifting state up in React. When is it useful?**

Lifting state up involves moving the state from a child component to its parent. This is useful when multiple components need access to the same state, or when state changes need to be synchronized between components.

## Hooks

### 10. **What are React Hooks? Provide examples of at least two built-in hooks and explain their use cases.**

React Hooks are functions that let you use state and other React features in functional components. Examples: `useState` for managing state and `useEffect` for handling side effects.

### 11. **What is the purpose of the `useEffect` hook? How does it differ from `componentDidMount` and `componentDidUpdate`?**

`useEffect` is used for side effects in functional components. It runs after every render and replaces lifecycle methods like `componentDidMount` and `componentDidUpdate`. Dependencies can be specified to control when the effect runs.

## Routing

### 12. **Describe client-side routing in a React application. How can you implement it using React Router?**

Client-side routing involves changing the UI based on the URL without a full page reload. React Router is a popular library for implementing this in React. Components like `BrowserRouter` and `Link` help manage the routing.

### 13. **Explain the significance of the `Link` component in React Router.**

The `Link` component is used for navigation in React Router. It provides a declarative way to create hyperlinks and prevents the browser from doing a full page reload when the link is clicked, leading to a smoother single-page application experience.

## Redux

### 14. **What is Redux, and why might you use it in a React application?**

Redux is a state management library for JavaScript applications. It provides a predictable state container, making it easier to manage and update the state of a React application, especially as it scales.

### 15. **Explain the role of actions, reducers, and the store in Redux.**

Actions describe changes in the application state, reducers specify how the state changes in response to actions, and the store holds the application state. Actions are dispatched to reducers via the store, which updates the state accordingly.

### 16. **How would you connect a React component to the Redux store?**

Use the `connect` function provided by the `react-redux` library. It connects a React component to the Redux store, allowing the component to access the state and dispatch actions.

## Advanced Concepts

### 17. **Describe Higher-Order Components (HOCs) and their use in React. Provide an example.**

HOCs are functions that take a component and return a new component with additional features. They are used for code reuse, logic abstraction, and cross-cutting concerns. Example:

```jsx
const withLogger = (WrappedComponent) => {
  return class extends React.Component {
    // Add logging logic here
    render() {
      return <WrappedComponent {...this.props} />;
    }
  };
};
```

### 18. **Explain React Context and when you might use it instead of props or Redux.**

React Context provides a way to pass data through the component tree without having to pass props down manually at every level. It's useful for sharing global or application-level state when prop drilling becomes cumbersome.

### 19. **What are React Hooks custom and how can they be created?**

Custom Hooks are reusable functions that encapsulate common logic in functional components. They start with the prefix `use` and can be created by extracting and organizing logic into a separate function that follows the rules of Hooks.

### 20. **Discuss the concept of controlled and uncontrolled components in React.**

Controlled components are those whose state is controlled by React, typically through the use of state. Uncontrolled components rely on the DOM to maintain and update their state.

## Testing

### 21. **How would you test a React component? Name some testing libraries for React.**

React components can be tested using tools like Jest and testing libraries like React Testing Library or Enzyme. Unit tests, integration tests, and snapshot tests are common testing strategies.

### 22. **Explain the purpose of snapshot testing in React. When would you use it?**

Snapshot testing captures a snapshot of a component's rendered output and compares it to a stored reference snapshot. It's useful for detecting unintended changes in the UI and ensuring that the UI remains consistent across code changes.

## Security

### 23. **What are some common security considerations in a React application? How can you prevent Cross-Site Scripting (XSS) attacks?**

Common security considerations include validating and sanitizing user inputs, using HTTPS, and implementing proper authentication and authorization mechanisms. To prevent XSS attacks, use libraries like DOMPurify, and avoid rendering user input directly into the DOM.

### 24. **How does React handle security vulnerabilities like Cross-Site Request Forgery (CSRF)?**

React itself does not directly handle CSRF. Prevention typically involves implementing anti-CSRF tokens on the server side and ensuring that they are included in any requests that modify server-side state. Front-end security practices should complement server-side measures.

## Exercice

## How would you build that ?

- 1 API : send crappy data, you only want a part
- Show the data in 2 components

Answer :

API -> Service that call API and clean the data -> send to 2 components

## How would add the token into a header of each API call ?

2 answers :

- a service that override all HTTP call
- an interceptor ?
