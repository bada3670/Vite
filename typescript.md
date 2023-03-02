## Concept

TypeScript can be used without installing anything.

## Example

|structure|

All of the files are at the root directory.

```
index.html
index.ts
export.ts
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
    <!-- The extension is 'ts'. -->
    <script defer type="module" src="index.ts"></script>
  </head>
  <body></body>
</html>
```

|index.ts|

```ts
import text from './export';

const $element = document.createElement('h1');
$element.innerText = text;

document.body.append($element);
```

|export.ts|

```ts
export default 'text from export';
```
