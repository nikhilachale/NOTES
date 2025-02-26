Custom hooks are a powerful feature in React that allow you to extract reusable logic from your functional components. They enable developers to encapsulate complex logic and share it across components without duplicating code. Custom hooks are simply JavaScript functions that util

ize React’s built-in hooks (like useState, useEffect, useContext, etc.) to implement specific functionality.


**Creating a Custom Hook**


A custom hook is a JavaScript function that:

1. Has a name prefixed with use (e.g., useFetch, useForm).

2. May call other hooks inside it.

3. Returns state, handlers, or computed values.

###### **Benefits of Custom Hooks**

1. **Code Reusability**: Encapsulates logic, making it reusable across multiple components.

2. **Improved Readability**: Keeps component code clean and focused on UI logic.

3. **Testability**: Easier to test isolated logic in hooks.

4. **Separation of Concerns**: Promotes better organization of application logic.


data fetching hooks useFetch()
browser Functionality hooks  useIsOnline()
