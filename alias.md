## prerequisites

'typescript.md' should be read.

## Concept

I think these names can be used as well.

> absolute paths, absolute imports, custom paths

They can be set by a configuration file.

## Example

|structure|

```
vite.config.js
index.html
src
  |-index.js
  |-export1.js
  |-export2.js
```

|vite.config.js|

```js
import { defineConfig } from 'vite';
import * as path from 'path';

export default defineConfig({
  resolve: {
    alias: {
      '/': path.resolve(__dirname),
      '@src': path.resolve(__dirname, 'src'),
    },
  },
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
    <script defer type="module" src="src/index.js"></script>
  </head>
  <body></body>
</html>
```

|src/index.js|

```js
// using aliases
import export1 from '/src/export1.js';
import export2 from '@src/export2.js';

const $element1 = document.createElement('h1');
$element1.innerText = export1;

const $element2 = document.createElement('h1');
$element2.innerText = export2;

document.body.append($element1);
document.body.append($element2);
```

|src/export1.js|

```js
export default 'text from export1';
```

|src/export2.js|

```js
export default 'text from export2';
```

## TypeScript

Even if you change the js files into ts files in the above example, it still works fine.

However, red lines will be shown if there is no mentioning about TypeScript.

So, please set these in 'tsconfig.json'.

|tsconfig.json|

```json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "/*": ["./*"],
      "@src/*": ["./src/*"]
    }
  }
}
```
