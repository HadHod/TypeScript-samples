# Typy

* Typy w TypeScript są opcjonalne
* domyslnym typem jest ```Any```

```ts
let x;
x = 1;
x = 'test';
```

Przykład z życia:
```ts
export interface IUserRaw {
    name: string;
    is_admin: boolean;
}

export class User {
    name: string;
    isAdmin: boolean;
    
    constructor (u: IUserRaw) {
        this.name = u.name;
        this.isAdmin = u.is_admin;
    }
}
```