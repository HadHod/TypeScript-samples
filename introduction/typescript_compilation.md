### Kompilacja

tsc file.ts

##### opcje:

* -w (watcher)

##### tsconfig.json:

* bla bla

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