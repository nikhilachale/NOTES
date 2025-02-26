[[Routing]]

it help to get rid of [[Prop drilling]]
The **Context API** in React is used to manage global state across a React application, allowing you to pass data down through the component tree without having to pass props manually at each level. This helps avoid “prop drilling,” where props are passed down multiple levels unnecessarily.

  

**Steps to use useContext and the Context API:**

  

1. **Create the Context**: Using React.createContext().

2. **Provide the Context**: Using Context.Provider to wrap components that need access to the context.

3. **Consume the Context**: Using useContext to access the context values inside any component.

  

**Example:**

  

Let’s build a simple example that shares a user object across components using the Context API.

  

**Step 1: Create the Context**
```

import React, { createContext, useState } from 'react';

// Create a context
const UserContext = createContext();
```

**Step 2: Provide the Context**

  

Wrap the components that need access to the context inside a UserContext.Provider:
```

function App() {
  const [user, setUser] = useState('John Doe');

  return (
    <UserContext.Provider value={user}>
      <Parent />
    </UserContext.Provider>
  );
}

function Parent() {
  return <Child />;
}
```

Here, the App component provides the user state to all child components wrapped in the UserContext.Provider. The value prop of the provider holds the data you want to share (in this case, the user state).

  

**Step 3: Consume the Context with useContext**

  

Now, any component in the tree can access the user value using the useContext hook:
```

import React, { useContext } from 'react';

function Child() {
  return <GrandChild />;
}

function GrandChild() {
  const user = useContext(UserContext);
  return <h1>Hello, {user}!</h1>;
}

export default App;
```

**Explanation:**

  

1. UserContext: Created with createContext(). This context will hold the user state.

2. UserContext.Provider: Wraps the components that need access to the user value and provides it via the value prop.

3. useContext(UserContext): Inside the GrandChild component, useContext is used to access the value from UserContext.

  

**Updating Context:**

  

If you want to update the context, you can pass both the state and the function that updates it (like setUser) as the value of the Provider:
```

function App() {
  const [user, setUser] = useState('John Doe');

  return (
    <UserContext.Provider value={{ user, setUser }}>
      <Parent />
    </UserContext.Provider>
  );
}

function GrandChild() {
  const { user, setUser } = useContext(UserContext);

  const changeUser = () => setUser('Jane Doe');

  return (
    <div>
      <h1>Hello, {user}!</h1>
      <button onClick={changeUser}>Change User</button>
    </div>
  );
}
```

In this updated example:

• setUser is provided via the value prop of UserContext.Provider.

• The GrandChild component can now both display and update the user state using useContext.


**Conclusion:**
 
• **Context API** allows you to avoid prop drilling and easily share global data across deeply nested components.

• useContext hook is the easiest way to access context values inside functional components.

• Use the **Context API** when you need to pass data to multiple components or when many components need to access the same data.