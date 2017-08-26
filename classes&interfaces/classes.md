# Klasy

### Przykład prostej klasy
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

### dziedziczenie
```ts
class Dog extends Animal {
    constructor (name: string) { super(name); }
}
```

### wywołanie funkcji z klasy nadrzędnej
```ts
let d = new Dog('Reksio');
d.sayName();
```

### Modyfikatory dostępu pól i funkcji:
* public
* private
* protected

Przykład wykożystania pola z ```protected```
```ts
class Person {
    protected name: string;
    constructor (name: string) {
        this.name = name;
    }
}

class Employee extends Person {
    private department: string;

    constructor (name: string, department: string) {
        super(name);
        this.department = department;
    }

    getElevatorPitch () {
        return `Hello, my name is ${this.name} and I work in ${this.department}.`;
    }
}

let howard = new Employee('Howard', 'Sales');
console.log(howard.getElevatorPitch());
console.log(howard.name); // error
```

```contructor``` także może mieć modyfikator ```protected```. Sprawdźmy to modyfikując przykład z powyżej.

### readonly
Zmienna z modyfikatorem ```readonly``` może mieć przypisaną wartość tylko przy inicjalizacji lub przy wywołaniu ```contructor```.
```ts
class R1 {
    readonly x: number = 1;
}
```

Argumenty w ```constructor``` z modyfikatorem ```readonly``` pozwalają deklarować pola klasy ```inline```.
```ts
class R2 {
    constructor (readonly x: number) {}
}
```

### Accessors (akcesory?)
```ts
class Person {
    private _name: string;
    
    set name (n: string) {
        this._name = n;
    }
    
    get name () {
        return this._name;
    }
}
```

### Static (pola statyczne)
```ts
class Person {
    static height: number = 190;
    
    constructor () {
        alert(Person.height);
    }
}
```

### Klasy abstrakcyjne
```ts
abstract class Animal {
    constructor (public name: string) {}

    abstract makeSound (): void;
    move (): void {
        alert('I am moving!');
    }
    getName () {
        return this.name;
    }
}
```