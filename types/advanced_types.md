### [Typy złożone](https://www.typescriptlang.org/docs/handbook/advanced-types.html)

##### Union Types

```ts
let yolo: string | number;
yolo = 'yolo';
yolo = 1;
```

##### Optional parameters

Z parametrem `--strictNullChecks`, automatycznie dodawane jest `| undefined`

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

##### Funkcja jako typ

```ts
let isTrue: () => boolean = () => true
```

##### [Pattern Matching](https://www.typescriptlang.org/docs/handbook/advanced-types.html) / [Github](https://github.com/swissmanu/pattern-matching-with-typescript)

zwykły przykład z `Switch Statement`
```ts
function matchNumber(n: number): string {
    switch (n) {
        case 1:
            return 'one';
        case 2:
            return 'two';
        case 3:
            return 'three';
        default:
            return `${n}`;
    }
}
```

zaczynamy budować Pattern Matching od interfejsu
```ts
interface NumberPattern {
  One: () => string;
  Two: () => string;
  Three: () => string;
  Other: (n: number) => string;
}
```

używamy interfejs
```ts
function matchNumber(p: NumberPattern): (n: number) => string {
  return (n: number): string => {
    switch (n) {
      case 1:
        return p.One();
      case 2:
        return p.Two();
      case 3:
        return p.Three();
      default:
        return p.Other(n);
    }
  };
}
```

Pattern matching
```ts
const match = matchNumber({
  One: () => 'One',
  Two: () => 'Two',
  Three: () => 'Three',
  Other: (n) => `${n}`
});
```

Później pokażemy uniwersalne rozwiązanie z typami generycznymi.

