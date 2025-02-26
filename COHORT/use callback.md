In React, useCallback is a hook used to memoize functions. It helps in optimizing performance by preventing a function from being recreated on every render, especially when the function is passed as a prop to child components.
**Basic Syntax:**
```
const memoizedCallback = useCallback(() => {
  // Your function logic here
}, [dependencies]);
```

**Callback function**: The function you want to memoize.

• **Dependencies**: An array of dependencies. The function will only be recreated if one of these dependencies changes.


**When to Use useCallback?**

You typically use useCallback when you pass a function as a prop to a child component. Without useCallback, the function would be redefined on every render, potentially causing unnecessary re-renders of the child component.


use callback is not about minimising the code it is about not renderning the child component if the function doesn't needs  to change across the renders 


**Example Usage:**
```

import { useCallback, useState } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  // Memoizing the function
  const handleClick = useCallback(() => {
    console.log('Button clicked, count:', count);
  }, [count]); // Recreated only if `count` changes

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleClick}>Log Count</button>
      <button onClick={() => setCount(count + 1)}>Increment Count</button>
    </div>
  );
}
```

**Key Points:**

1. **Prevents re-creation of functions**: useCallback memoizes the function so that it’s not recreated unless dependencies change.

2. **Optimization in child components**: Passing memoized functions as props to child components can prevent unnecessary re-renders.

3. **Dependency array**: Just like useMemo, the function is only recreated if one of the dependencies changes.


**useCallback vs useMemo:**
  
• useCallback memoizes a **function**, while useMemo memoizes a **value** (the result of a computation).

• Both are used for performance optimization by avoiding unnecessary recalculations or function recreations on every render.
