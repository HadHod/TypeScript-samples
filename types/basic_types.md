### [Typy podstawowe](https://www.typescriptlang.org/docs/handbook/basic-types.html)

##### Boolean
```ts
let isDone: boolean = false;
```

##### Number
```ts
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```

##### String
```ts
let color: string = 'pink';
```

##### Array
```ts
let list: number[] = [1, 2, 3]; // podstawowe
let list: Array<number> = [1, 2, 3]; // generyczne
```

##### Tuple
```ts
let x: [string, number];
```

##### Enum
```ts
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

##### Obiekty
```ts
let x: {
    name: string;
    age: number;
}
x.name = 'John';
x.age = 25;

type Person = {
    name: string;
    age: number;
}

let pair: {
    p1: Person;
    p2: Person;
}
```

##### "Dodatkowe"
```ts
let a: any = 'yellow';
let v: void = undefined;
let u: undefined = undefined;
let n: null = null;
function infiniteLoop(): never {
    while (true) {
    }
}
```

```undefined``` i ```null``` są podtypami wszystkich pozostałych typów, chyba, że użyjemy flagi ```--strictNullChecks``` wtedy mogą być przypisane tylko do ```void```