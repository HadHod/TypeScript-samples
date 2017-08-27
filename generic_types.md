# Typy generyczne

### Funkcje
Prosty przykład z typami generycznymi
```ts
function genericFunction<T> (variable: T): T {
    console.log(variable);
    return variable;
}
```
oraz wywołanie:
```ts
let s = genericFunction<string>('Hello');
let n = genericFunction<number>(1234567);
```
możemy tez użyć więcej niż jeden typ generyczny
```ts
function genericFunction2<T, U> (variable: T, fun: (T) => U): U {
    return fun(variable);
}
```
wywołanie
```ts
let toStr: (number) => string = (n) => n + '';
console.log(genericFunction2(1, toStr));
```

### Klasy
```ts
class GenericCollection<T> {
    private collection: T[] = [];
    
    constructor (...item: T[]) {
        item.forEach(e => this.collection.push(e));
    }
    
    getCollection (): T[] {
        return this.collection;
    }
}

let numCollection: GenericCollection<number> = new GenericCollection<number>(1, 2, 3);
```
Możemy stworzyć bardziej złożony typ danych.
```ts
interface IUser {
    name: string;
    age: number;
}
```
i użyć go z generyczna kolekcją:
```ts
let usersCollection = new GenericCollection<IUser>(
    {name: 'Bob', age: 5},
    {name: 'Jon', age: 7}
);
```
### Rozszerzanie typów generycznych
```ts
class GenericCollection<T extends IUser> {
    (...)
    findUser (name: string) {
        return this.collection.filter(e => e.name === name);
    }
    (...)
}
```
### Upgradujemy przykład z patter matching
```ts
(...)
```