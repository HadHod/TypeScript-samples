### [Moduły](https://www.typescriptlang.org/docs/handbook/modules.html)

Tworząc ```module```, zamykamy wszystkie deklaracje wewnątrz w obrębie stworzonego modułu.
##### ModuleA
```ts
module ModuleA {
    let x: number = 1;
    
    function funcInModule () {
        console.log('here I am');
    }
    
    export class C {
        constructor () {}
    }
}
```

##### ModuleB
```ts
module ModuleB {
    
}
```