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

- Adding tailwindcss and prettier

```bash
npm install -D tailwindcss postcss autoprefixer prettier prettier-plugin-tailwindcss
```

- Initialize tailwind.config.js to look for all JavaScript and TypeScript files, and add prettier-plugin-tailwindcss

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: ['prettier-plugin-tailwindcss'],
};
```

and then add the required headers in index.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- Add .prettierrc.json and set the following rules:

```json
{
	"semi": true,
	"trailingComma": "all",
	"singleQuote": true,
	"printWidth": 100,
	"tabWidth": 2,
	"endOfLine": "auto",
	"plugins": ["prettier-plugin-tailwindcss"]
}
```

- Replace .eslintrc.cjs with .eslintrc.json and simply add the following:

```json

```

## Requirement Documentation

- Very simple application, where users can order one or more pizzas from a menu
- Requires no user accounts and no login: users just input their names before using the app
- [x] The pizza menu can change, so it should be **loaded from an API**
- Users can add multiple pizzas to a cart before ordering
- Ordering requires just the user's name, phone number, and address
- If possible, GPS locaiton should also be provided, to make delivery easier
- User's can mark their order as "priority" for an additional 20% of the cart price
- Orders are made by sending POST request with the order data to the API
- Payments are made on delivery, so no payment processing is necessary in the app
- Each order will get a unique ID that should be displayed, so the user can later look up their order based on the ID
- Users should be able to mark their order as "priority" order even after it has been placed

Based on the requirements, there are four major features

1. User (/)
2. Menu (/menu)
3. Cart (/cart)
4. Order (/order/new, /order/:orderID)

Each of the features will have one or more pages dedicated to the features above.
