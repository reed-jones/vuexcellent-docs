# Vue.js Installation

```sh
npm install @j0nz/vuexcellent
# or
yarn add @j0nz/vuexcellent
```

Now just use `@j0nz/vuexcellent` instead of `vuex` when you are creating your store.

```js
import Vuex, { Store } from '@j0nz/vuexcellent'

const store = new Store({
    //...
```

All vuex options are re-exported from vuexcellent for ease of use. For example:

```js
import { mapState } from '@j0nz/vuexcellent'
```
