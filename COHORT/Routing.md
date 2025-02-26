


Routing in React is handled using the **React Router** library, which allows you to navigate between different components or pages in a React application based on the URL path. It helps create single-page applications (SPAs) where the page doesn’t reload but different views (components) are rendered when the URL changes.


- [[Lazy loading]]
- [[Prop drilling]]
- [[Context Api ]]

  

**Key Concepts of Routing in React:**

  

1. **BrowserRouter**: This component wraps your app and enables routing by managing the history stack using the HTML5 history API.

2. **Routes**: Contains multiple Route components that define the different paths in your application.

3. **Route**: Specifies the path and the component to render when the path matches the current URL.

4. **Link**: Used to navigate between routes without reloading the page, similar to an  '<a/a>' tag but optimized for SPAs.

5. Switch (deprecated in v6, replaced by Routes): Renders only the first matching route in earlier versions of React Router.


```
npm install react-router-dom
```



```
import React from 'react';
import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom';

function Home() {
  return <h1>Home Page</h1>;
}

function About() {
  return <h1>About Page</h1>;
}

function App() {
  return (
    <Router>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
      </nav>

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Router>
  );
}

export default App;
```


[[State Management]] using [[Recoil]]
 state management is the cleaner way to store the state of your app ,until now ,the cleanest thing you can do is the use of context API
