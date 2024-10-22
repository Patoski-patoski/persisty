# persisty 💾

Simple Browser Local storage (and Session Storage) Abstraction.

Helps you work with browser localStorage (and sessionStorage) as a regular JavaScript object. It does this by allowing you use regular javascript object syntax.

## Installation

To use it just install from npm with the following command:

```bash
npm install persisty
```

## Usage

## Working with `localStorage`

When working with `localStorage`, you should import it as default like below:

### import `persisty`

```javascript
// import persisty
import persisty from 'persisty';
```

or as a named import:

### import `persistLocal`

```javascript
import { persistLocal } from 'persisty';
```

> **Note**: You have the flexibility to use either the import of `persisty` or
> `persistLocal`, as they refer to the same functionality.
>
> In rare cases where you encounter a TypeError or ReferenceError due to
> imports, you may need to import the package directly from npm using the
> following syntax:
>
> ```javascript
> import { persistLocal } from 'https://www.unpkg.com/persisty@2.0.0/src/index.js';
> ```

### store data in localStorage

```javascript
const orders = [
  { id: 1, quantity: 2 },
  { id: 2, quantity: 1 },
];

persisty.orders = orders // Also saved in you browser localStorage

// or use persistLocal from named import:
persistLocal.orders = orders
```

### get data in localStorage

```javascript
console.log(persisty.orders);
// Output:
// [
//   { id: 1, quantity: 2 },
//   { id: 2, quantity: 1 },
// ];

```

### delete data in localStorage

```javascript
delete persisty.orders

console.log(persisty.orders); // null
```

## Working with `sessionStorage`

Import `persistSession` to interact with  `sessionStorage`.

### import persistSession

```javascript
// import persisty
import { persistSession } from 'persisty';
```

### store data in sessionStorage

```javascript
const orders = [
  { id: 1, quantity: 2 },
  { id: 2, quantity: 1 },
];

persistSession.orders = orders // Also saved in you browser sessionStorage
```

### get data in sessionStorage

```javascript
console.log(persistSession.orders);
// Output:
// [
//   { id: 1, quantity: 2 },
//   { id: 2, quantity: 1 },
// ];

```

### delete data in sessionStorage

```javascript
delete persistSession.orders

console.log(persisty.orders); // null
```

----

> [!NOTE]
> persisty does not support deep mutation (yet).

For example:

```javascript
console.log(persisty.orders[0]) // { id: 1, quantity: 2 }
persisty.orders[0].id = 123
console.log(persisty.orders[0]) // { id: 1, quantity: 2 }
```

Won't work.

## Contribute

Issues/Feature request and PRs are welcome.

## License

[MIT](./LICENSE) License
