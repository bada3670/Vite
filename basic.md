## Concept

As Vite offers many features, it is hard to define what it is. Nevertheless, I would say it is a combination of a bundler and a server. For example, webpack with webpack-dev-server.

## Installation

Please install 'vite' as a dev dependency.

## Example

### settings

|structure|

All of the files are at the root directory.

```
index.html
index.css
export.css
index.js
export.js
```

|index.html|

! Vite starts from [index.html] file. So, please don't change the file name.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <!-- importing css files -->
    <link rel="stylesheet" href="index.css" />
    <!-- importing js files -->
    <!-- If you use ESM, don't forget to write [type="module"]. -->
    <script defer type="module" src="index.js"></script>
  </head>
  <body>
    <h1></h1>
  </body>
</html>
```

|index.css|

```css
@import url(./export.css);
```

|export.css|

```css
h1 {
  color: violet;
}
```

|index.js|

```js
import './export.js';
```

|export.js|

```js
document.querySelector('h1').innerText = 'Hello!';
```

### running a dev server

```sh
$ npx vite
```

After you type it, the terminal will show you the address.

### building & running the built codes

To build, please type this.

```sh
$ npx vite build
```

If you type it, [dist] folder will be made where the codes are stored.

To check how the built codes work, please type this.

```sh
$ npx vite preview
```
