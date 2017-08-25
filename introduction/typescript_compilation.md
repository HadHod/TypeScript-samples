### Kompilacja

tsc file.ts

##### [opcje](https://www.typescriptlang.org/docs/handbook/compiler-options.html):

* -w (watcher)
* --init (generuje tsconfig.json)

##### tsconfig.json:

```json
{
  "compilerOptions": {
    "target": "es5",
    "strict": true
  },
  "files": [
    "./main.ts"
  ]
}
```

##### pierwsze demo:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>TypeScript demo 1</title>
    <meta charset="UTF-8">
</head>

<body>
    <p id="foo">Hello World!</p>
    <script src="main.js"></script>
</body>

</html>
```

```ts
window.onload = (event: Event) => {
    document.getElementById('foo').innerHTML = 'Hello TypeScript!';
};
```