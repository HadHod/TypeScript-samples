### [Moduły](https://www.typescriptlang.org/docs/handbook/modules.html)

Tworząc ```module```, zamykamy wszystkie deklaracje wewnątrz w obrębie stworzonego modułu. Sprawdźmy przykład z importem kodu z innego pliku.

##### user.ts
```ts
export class User {
    
    constructor (private name: string) {]
    
    getName () {
        return this.name;
    }
    
}
```

##### main.ts
```ts
import { User } from './user';

let u: User = new User('Jon');
console.log(u.getName());
```

Możemy zmienić nazwę exportowanego obiektu lub miejsce deklaracji exportu.
```ts
class User {

    constructor (private name: string) {]
    
    getName () {
        return this.name;
    }

}

export { User as Person };
```