## Concept

You can use a configuration file.

## Example

### settings

|structure|

All of the files are at the root directory.

```
c.js
index.html
indes.js
export.js
```

|c.js|

```js
import { defineConfig } from 'vite';

export default defineConfig({
  server: {
    port: 3000,
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
    <script defer type="module" src="index.js"></script>
  </head>
  <body></body>
</html>
```

|index.js|

```js
import text from './export';

const $element = document.createElement('h1');
$element.innerText = text;

document.body.append($element);
```

|export.js|

```js
export default 'text from export';
```

### running with applying 'c.js' as the configuration file

```sh
$ npx vite --config c.js
```

If you run the command, the port will be '3000', not '5173'.

## vite.config.js

If the name of the configuration file is 'vite.config.js', we can omit '--config'.

```sh
$ npx vite
```

## Using Documentation

I tried to find out in the website how to write configurations in the configuration file, but I failed. However, I found it out by auto-completing features of VSCode.

For example, if it says 'server.port', the configuration looks like this.

```js
import { defineConfig } from 'vite';

export default defineConfig({
  server: {
    port: 3000,
  },
});
```

Properties are separated by '.'.
