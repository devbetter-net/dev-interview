### Difference Between State and Props in React

In React, `state` and `props` are two important concepts used for managing data and rendering components. Here are the key differences:

#### Props

1. **Definition**: Props (short for properties) are read-only attributes passed from a parent component to a child component.
2. **Mutability**: Props are immutable, meaning they cannot be changed by the child component that receives them.
3. **Usage**: Used to pass data and event handlers down to child components.
4. **Access**: Accessed via `this.props` in class components or directly in function components.
5. **Lifecycle**: Props are set by the parent component and remain constant throughout the lifecycle of the child component unless the parent component re-renders with new props.

#### State

1. **Definition**: State is a mutable data structure that holds information about the component's current situation.
2. **Mutability**: State is mutable and can be changed using the `setState` method in class components or the `useState` hook in function components.
3. **Usage**: Used to manage data that can change over time and affect the rendering of the component.
4. **Access**: Accessed via `this.state` in class components or directly in function components using the `useState` hook.
5. **Lifecycle**: State is managed within the component and can change over time, triggering re-renders when updated.

#### Example

```jsx
import React, { useState } from 'react';

// Function Component using props and state
function ExampleComponent(props) {
  // Using useState hook to manage state
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{props.title}</h1> {/* Accessing props */}
      <p>Count: {count}</p> {/* Accessing state */}
      <button onClick={() => setCount(count + 1)}>Increment</button> {/* Updating state */}
    </div>
  );
}

// Usage of ExampleComponent with props
function App() {
  return <ExampleComponent title="Hello, World!" />;
}

export default App;