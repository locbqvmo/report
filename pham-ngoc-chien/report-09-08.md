# === DAILY REPORT 09/08 ===

## Pham Ngoc Chien 09/08

**Today**

- ReactJS: is a JavaScript library for building user interfaces.

  - React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
  - Build encapsulated components that manage their own state, then compose them to make complex UIs.
  - React can also render on the server using Node and power mobile apps using React Native.

- JSX: A syntax extension of JavaScript, allows us to write html in React

- Props and Components

  - Component: help to divide UIs into small component
  - Function Components

  ```
      function Welcome(props) {
          return <h1>Hello, {props.name}</h1>;
      }

  ```

  - Class Components

  ```
    class Welcome extends React {
        render() {
            return <h1>Hello, {this.props.name}</h1>;
    }
  }

  ```

  - Props: pass data between components

- State and Lifecycle

  - State: storage data or status of component and just within the scope of component, when the state change then component will return again.
  - Lifecycle: with component, life cycle have three stages (Mounting, updating, Unmounting)

- Hooks: a new addition in React 16.8. They let you use state and other React features without writing a class.

  ```
      import React, { useState } from 'react';
      function Example() {
      // Declare a new state variable, which we'll call "count"
      const [count, setCount] = useState(0);

      return (
          <div>
          <p>You clicked {count} times</p>
          <button onClick={() => setCount(count + 1)}>
              Click me
          </button>
          </div>
      );
      }
  ```

- useState(): a hook allow you add React state in function components

  ```
      const [state, setState] = useState(initialStateValue
  ```

  ```
      () => {
      const [count, setCount] = useState(0)
      const handleClick = () => setCount(age + 1)

      return (
          <div>
          Current count {count}.
          <div>
              <button onClick={handleClick}>Increment Count!</button>
          </div>
          </div>
      )
      }
  ```

- useEffect(): a hook allow you practice side effect in function components

  ```
      import React, {useEffect, useState} from 'react';

      export const EffectDemo = () => {
          //State
          const [fullName, setFullName] = useState({name: 'name', familyName: 'family'});
          const [title,setTitle] = useState('useEffect() in Hooks');

          //useEffect
          useEffect(() => {
              setFullName({name:'TrungHC',familyName: 'HCT'});
          });

          return(
              <div>
                  <h1>Title: {title}</h1>
                  <h3>Name: {fullName.name}</h3>
                  <h3>Family Name: {fullName.familyName}</h3>
              </div>
          );
      };
  ```

**Issues**

- None
