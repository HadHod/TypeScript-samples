### [Typy złożone](https://www.typescriptlang.org/docs/handbook/advanced-types.html)

##### Union Types
```ts
let yolo: string | number;
yolo = 'yolo';
yolo = 1;
```

##### Optional parameters
Z parametrem ```--strictNullChecks```, automatycznie dodawane jest ```| undefined```
```ts
function add (x: number, y?: number) {
    return x + (y || 0);
}
```

##### Default parameters
```ts
function add (x: number, y: number = 0) {
    return x + y;
}
```

##### Type aliases

```ts
type Person = {
    name: string;
    age: number;
}

let pair: {
    p1: Person;
    p2: Person;
}
```

##### String Literal Types
```ts
type Welcome = 'Hi' | 'Hello' | 'What\'s up?';
```

##### [Pattern Matching](https://www.typescriptlang.org/docs/handbook/advanced-types.html)
