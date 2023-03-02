## Concept

CSS modules can be used.

## Example

### settings

|structure|

All of the files are at the root directory.

```
index.html
index.js
export.module.css
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
import style from './export.module.css';

console.log(style); // (1)

const $title = document.createElement('h1');
$title.innerText = 'Hello!';
$title.classList.add(style.title);
document.body.append($title);
```

|export.module.css|

```css
.title {
  color: violet;
}
```

### result

(1) in index.js prints this.

```js
{
  title: '_title_1rozn_1';
}
```

If you check Elements in a browser dev tool, you can find the element's class is '\_title_1rozn_1'.

### building results

This part covers the result of 'npx vite build'.

In the css file, there is the class and its property.

|the-css-file|

```css
._title_1rozn_1 {
  color: violet;
}
```

In the js file, the class is made and assigned to the element.

|the-js-file|

```js
// I skipped the above part.

const l = '_title_1rozn_1',
  s = { title: l };
console.log(s);
const i = document.createElement('h1');
i.innerText = 'Hello!';
i.classList.add(s.title);
document.body.append(i);
```
