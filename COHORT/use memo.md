In React, useMemo is a hook that helps improve performance by memoizing the result of an expensive computation, only recalculating when its dependencies change. This can prevent unnecessary recalculations on each render.
**Basic Syntax:**
```
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```
`import { useMemo, useState } from 'react';`

`function MyComponent() {`
  `const [count, setCount] = useState(0);`
  `const [otherCount, setOtherCount] = useState(0);`

  `// Memoizing an expensive computation`
  `const expensiveCalculation = useMemo(() => {`
    `console.log('Running expensive calculation...');`
    `return count * 100;`
  `}, [count]); // Only recalculates if `count` changes`

  `return (`
    `<div>`
      `<p>Expensive Calculation Result: {expensiveCalculation}</p>`
      `<button onClick={() => setCount(count + 1)}>Increment Count</button>`
      `<button onClick={() => setOtherCount(otherCount + 1)}>Increment Other Count</button>`
    `</div>`
  `);`
`}`


1. **Performance optimization**: useMemo helps avoid re-executing expensive calculations on every render.

2. **Dependency array**: It will only recompute the memoized value when the specified dependencies change.

3. **Use wisely**: Use it for computationally heavy operations; avoid using it for everything, as it can add unnecessary complexity.