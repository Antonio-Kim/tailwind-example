# Fast React Pizza

A simple website that you can order some delicious pizzas.

Here are the steps to initialize React using Vite. This will eventually moved to Documentation

- npm i
- npm i eslint vite-plugin-eslint eslint-config-react-app --save-dev
- add ".eslintrc.json" and add the following code:

```json
{
  "extends": "react-app"
}
```

- Inside the vite.config.js, replace the code with the following (only adding eslint to plugins):

```jsx
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import eslint from 'vite-plugin-eslint';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react(), eslint],
});
```

- remove All the css files and remove the line that imports css in main.jsx
- remove all the code in App.jsx and add the following:

```jsx
function App() {
  return <div>Hello World!</div>;
}
export default App;
```
