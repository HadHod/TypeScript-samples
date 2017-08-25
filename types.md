# Typy

* Typy w TypeScript są opcjonalne
* domyslnym typem jest ```Any```
* typy jako sugestia

```ts
export interface IUserRaw {
    name: string;
    isAdmin: boolean
}

export class User {
    name: string;
    isAdmin: boolean
    
    constructor (u: IUserRaw) {
        this.name = u.name;
        this.isAdmin = u.isAdmin;
    }
}
```