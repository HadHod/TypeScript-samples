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