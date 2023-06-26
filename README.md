# Tailwind Starter CLI

## L025 Create An Environment With Tailwind CLI

Initialize `package.json`

```bash
npm init -y
```

Note: You can follow the instruction on installing Tailwind CLI [here](https://tailwindcss.com/docs/installation).

Install tailwind css

```bash
npm install -D tailwindcss
```

Initialize tailwind config

```bash
npx tailwindcss init
```

Configure your template paths

```javascript
// tailwind.config.js

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./*.html'],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Add the Tailwind directives to your CSS

```css
/* input.css */

@tailwind base;
@tailwind components;
@tailwind utilities;
```

Create NPM script to run tailwind css

```json
// package.json

{
  // ...

  "scripts": {
    "build": "tailwind -i ./input.css -o ./css/style.css",
    "watch": "tailwind -i ./input.css -o ./css/style.css --watch"
  }

  // ...
}
```

Run the build. This will create the `css/style.css` file

```bash
npm run build
```

Create `index.html` template

```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./css/style.css" />
    <title>Simple Tailwind CSS</title>
  </head>
  <body>
    <h1 class="text-3xl">Simple Tailwind CSS</h1>
  </body>
</html>
```

Run the npm watch to render css changes

```bash
npm run watch
```
