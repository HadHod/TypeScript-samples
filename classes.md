# [Klasy](https://www.typescriptlang.org/docs/handbook/classes.html) i Interfejsy

Przykład prostej klasy
```ts
class Animal {
    name: string;  // domyślny modyfikator dostępu: public
    
    constructor (name: string, size: number) {
        this.name = name;
    }
    
    sayName () {
        return name;
    }
}
```

dziedziczenie
```ts
class Dog extends Animal {
    constructor (name: string) { super(name); }
}
```

wywołanie metody z klasy nadrzędnej
```ts
let d = new Dog('Reksio');
d.sayName();
```

Modyfikatory dostępu:
* public
* private
* protected