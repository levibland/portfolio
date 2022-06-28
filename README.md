# Portfolio
My personal site built with Svelte (converted from React)

## Developing
This project uses Yarn, you will need to install it.

First install all dependencies:
```bash
$ yarn
```

To run a development server: 
```bash
$ yarn dev
```

## Building
To build for deployment:
```bash
$ yarn build
```

```ts
// store.ts
// An extremely simple external store
import { writable } from 'svelte/store'
export default writable(0)
```
