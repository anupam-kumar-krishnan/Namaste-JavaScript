# What Causes a React Component to Re-render?

In React, a component re-renders whenever React needs to update the UI based on changes in data or application state.

Understanding what triggers re-renders is important for optimizing performance and writing efficient React applications.

---

# 1. State Changes

The most common cause of a re-render is a change in component state.

When `setState` (or `useState` setter) is called, React schedules a re-render for that component.

Example:

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
  Increase
</button>
```

When `setCount()` runs:

```
State changes
     ↓
Component re-renders
     ↓
Virtual DOM updates
```

---

# 2. Props Changes

A component re-renders when it receives new props from its parent.

Example:

```jsx
function Parent() {
  const [count, setCount] = useState(0);

  return <Child value={count} />;
}
```

If `count` changes, the `Child` component receives new props and re-renders.

---

# 3. Parent Component Re-render

When a parent component re-renders, its child components may also re-render.

Example:

```jsx
function Parent() {
  const [count, setCount] = useState(0);

  return (
    <>
      <Child />
      <button onClick={() => setCount(count + 1)} />
    </>
  );
}
```

Even if `Child` receives no props, it may still re-render when the parent re-renders.

This can be optimized using `React.memo`.

---

# 4. Context Value Changes

When a context value changes, all components that consume that context will re-render.

Example:

```jsx
const ThemeContext = React.createContext();

function App() {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={theme}>
      <Child />
    </ThemeContext.Provider>
  );
}
```

If `theme` changes, every component using `ThemeContext` re-renders.

---

# 5. Hooks That Trigger Updates

Some hooks trigger component re-renders when their internal state changes.

Common hooks that cause updates:

- `useState`
- `useReducer`
- `useContext`

Example using `useReducer`:

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

Calling `dispatch()` updates state and causes a re-render.

---

# 6. Key Changes

Changing a component's `key` forces React to treat it as a completely new component.

Example:

```jsx
<Component key={id} />
```

If `id` changes, React will:

```
Unmount old component
     ↓
Mount new component
```

This results in a full re-render.

---

# Summary

Main causes of React component re-renders:

1. State changes
2. Props changes
3. Parent component re-render
4. Context value changes
5. Hook updates (useState, useReducer, useContext)
6. Key changes

---

# Interview Answer (Short Version)

A React component re-renders when its state changes, when it receives new props, when its parent component re-renders, when a consumed context value updates, or when hooks like `useState` or `useReducer` trigger state updates. Changing a component's `key` can also force React to recreate and re-render it.

