# Interfejsy

### Interfejs w argumencie funkcji
Nie musimy oznaczać, że obiekt przekazywany do funkcji implemetuje ```interface```. Wystarczy, że w obiekcie znajdują się wymagane pola. Kolejność pól z implementacją w klasie nie ma znaczenia.
```ts
interface ILabelledValue {
    label: string;
}

function printLabel (labelledObj: ILabelledValue) {
    console.log(labelledObj.label);
}

let myObj = {size: 10, label: 'Size 10 Object'};
printLabel(myObj);
```

### Optional properties
Interfejs może posiadać pola opcjonalne. Poniżej przykład gdzie nie wypełniamy pola ```width```.
```ts
interface ISquareConfig {
    color?: string;
    width?: number;
}

function createSquare (config: ISquareConfig): {color: string; area: number} {
    let newSquare = {color: 'white', area: 100};
    if (config.color) {
        newSquare.color = config.color;
    }
    if (config.width) {
        newSquare.area = config.width * config.width;
    }
    return newSquare;
}

let mySquare = createSquare({color: 'black'});
```

### Readonly properties
Pola oznaczone ```readonly``` mają przypisaną wartość przy tworzeniu obiektu i nie mogą zostać później zmienione.
```ts
interface IPoint {
    readonly x: number;
    readonly y: number;
}
```
Gdy próbujemy nadpisać wartość pola z ```readonly``` dostajemy błąd.
```ts
let p1: IPoint = { x: 10, y: 20 };
p1.x = 5; // error!
```
##### tablice tylko do odczytu
```ts
let a: number[] = [1, 2, 3, 4];
let ro: ReadonlyArray<number> = a;
a = ro as number[];
```

### Function Types
Opis funkcji w interfejsie:
```ts
interface ISearchFunc {
    (source: string, subString: string): boolean;
}
```
Implementacja:
```ts
let mySearch: ISearchFunc;
mySearch = function (src: string, sub: string): boolean {
    let result = src.search(sub);
    return result > -1;
}
```

### Rozszerzanie interfejsów
Interfejsy rozszerzamy przez słówko kluczowe ```extends```.
```ts
interface IShape {
    color: string;
}

interface ISquare extends IShape {
    sideLength: number;
}

let square = <ISquare>{};
square.color = 'blue';
square.sideLength = 10;
```
Możemy rozszerzać wiele interfejsów:
```ts
interface IMain extends I1, I2, I3 {
    // ...
}
```