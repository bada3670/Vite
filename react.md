## Introduction

We can use React with a plugin.

We can easily set up the environment using this command.

```sh
$ npm create vite@latest
```

But in this article, I will manually set up the environment to understand how it works.

## Installation

Please install 'react' and 'react-dom' as dependencies.

Please install '@vitejs/plugin-react' as a dev dependency.

## Example

|structure|

```
vite.config.js
index.html
src
  |-main.jsx
  |-App.jsx
```

|vite.config.js|

```js
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
});
```

|index.html|

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <!-- The extension is 'jsx'. -->
    <script defer type="module" src="src/main.jsx"></script>
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```

|src/main.jsx|

! The extenstion should be 'jsx', not 'js'.

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

import App from './App';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

|src/App.jsx|

```jsx
import React from 'react';

export default function App() {
  return <div>Hello!</div>;
}
```
