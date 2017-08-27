# Dekoratory

Aby używać dekoratorów musimy odpowiednio poinformować kompilator, ponieważ dekoratory są jeszcze w fazie ekperymentów (w przyszłości mogą nastąpić zmiany w implementacji):
```ts
{
    "compilerOptions": {
        "target": "ES5",
        "experimentalDecorators": true
    }
}
```

Dekoratory mogą być "przyczepione" do:
* klas
* funkcji
* zmiennych
* akcesorów
* parametrów

```ts
function Component(options) {
    console.log('options:', options);
    return (target) => console.log('@:', target);
}

@Component({})
class User {
    constructor() { }
}
```
Zmienne options może być dowolnego typu np. ```boolean```
Rozbudujmy przykład z powyżej:
```ts
function Component(options: { name: string }) {
    return (target) => {
        target.n = options.name
    }
}

@Component({
    name: 'Stasiek'
})
class User {
    static n: string;

    constructor() {
        console.log(User.n);
    }
}

new User();
```
