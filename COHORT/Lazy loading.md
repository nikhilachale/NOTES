**Lazy loading** in React is a performance optimization technique where components or resources (such as images or other large files) are loaded only when they are needed, rather than all at once when the app initially loads. This can significantly reduce the initial load time of an application, especially if it contains many routes or large components that are not always immediately visible to the user.

  

React provides a built-in way to implement lazy loading using the React.lazy() function and Suspense component.

  

**How Lazy Loading Works in React:**

  

• React.lazy(): This function is used to dynamically import a component only when it’s required. It returns a component that React can use like any other.

• Suspense: While a lazy-loaded component is being fetched, Suspense allows you to display a fallback UI (like a loading spinner).
```

import React, { Suspense } from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

const Home = React.lazy(() => import('./Home'));
const About = React.lazy(() => import('./About'));

function App() {
  return (
    <Router>
      <Suspense fallback={<div>Loading...</div>}>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
        </Routes>
      </Suspense>
    </Router>
  );
}

export default App;
```

  

  

Lazy loading in React improves the performance of an application by reducing the initial load time and downloading components or resources only when they are needed. React’s React.lazy() and Suspense make it easy to implement lazy loading for components, and it’s especially useful in routing to load page-specific components dynamically.