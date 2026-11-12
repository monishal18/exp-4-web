# EXP 04 – React Lab Exercise: Event Handling in React

## NAME: Monisha L

## REG NO: 2305001019

---

## Aim

To create React applications that demonstrate event handling using `onClick`, `onChange`, and `onSubmit` events to handle user interactions, update data, and perform form submissions.

## Objectives

- To understand event handling in React.
- To implement button click events using `onClick`.
- To create interactive applications using `useState()`.
- To show and hide messages using conditional rendering.
- To handle input field changes using `onChange`.
- To handle form submissions using `onSubmit`.
- To retrieve user input using `event.target.value`.
- To prevent page refresh using `event.preventDefault()`.

## Program

### Exercise 1 – Counter

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  function increase() {
    setCount(count + 1);
  }

  function decrease() {
    setCount(count - 1);
  }

  return (
    <div>
      <h1>Counter</h1>

      <button onClick={increase}>+</button>

      <h2>Count: {count}</h2>

      <button onClick={decrease}>-</button>
    </div>
  );
}

export default App;
```

### Exercise 2 – Show / Hide Message

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [show, setShow] = useState(false);

  function handleClick() {
    setShow(!show);
  }

  return (
    <div>
      <h1>Show / Hide Message</h1>

      <button onClick={handleClick}>
        {show ? "Hide Message" : "Show Message"}
      </button>

      {show && (
        <h2>Welcome to React!</h2>
      )}
    </div>
  );
}

export default App;
```

### Exercise 3 – Student Registration Form

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [name, setName] = useState("Monisha");
  const [regNo, setRegNo] = useState("2305001019");
  const [department, setDepartment] = useState("CSE");
  const [submitted, setSubmitted] = useState(false);

  function handleSubmit(event) {
    event.preventDefault();
    setSubmitted(true);
  }

  return (
    <div>
      <h1>Student Registration</h1>

      <form onSubmit={handleSubmit}>
        <input
          type="text"
          placeholder="Student Name"
          value={name}
          onChange={(event) => setName(event.target.value)}
          required
        />

        <br /><br />

        <input
          type="text"
          placeholder="Register Number"
          value={regNo}
          onChange={(event) => setRegNo(event.target.value)}
          required
        />

        <br /><br />

        <input
          type="text"
          placeholder="Department"
          value={department}
          onChange={(event) => setDepartment(event.target.value)}
          required
        />

        <br /><br />

        <button type="submit">Register</button>
      </form>

      {submitted && (
        <div>
          <h2>Student Details</h2>
          <p>Name: {name}</p>
          <p>Register No: {regNo}</p>
          <p>Department: {department}</p>
        </div>
      )}
    </div>
  );
}

export default App;
```

## Output

### Exercise 1 – Counter
<img width="311" height="226" alt="image" src="https://github.com/user-attachments/assets/34f3e8e9-fc93-40eb-b929-59cf40302ac7" />



### Exercise 2 – Show / hide message

<img width="462" height="262" alt="image" src="https://github.com/user-attachments/assets/b0b2a43c-2fcc-4547-8492-9509131ea765" />



<img width="462" height="185" alt="image" src="https://github.com/user-attachments/assets/ac53e606-1bdf-4b42-add8-ed71c2d29078" />


### Exercise 3 – Student Registration Form

<img width="627" height="592" alt="image" src="https://github.com/user-attachments/assets/84eacb09-6917-44c5-bbfe-93a33ad19c8f" />


## Result

Thus, React event handling was successfully implemented through three exercises: Counter using `onClick`, Show / Hide Message using `onClick` and conditional rendering, and Student Registration Form using `onChange` and `onSubmit` events. The applications demonstrated handling user interactions and dynamically updating the user interface.
