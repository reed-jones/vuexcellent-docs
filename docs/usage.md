# Usage

The `Vuex` facade has a simple API.

```php
// Creating or adding to the current store instance
Vuex::store(function($store) {

    // To add data to the root state object
    $store->state([
        // Array's and Collections are acceptable
        'count' => 5,
        'numbers' => [
            'even' => [0, 2, 4, 6, 8],
            'odd' => [1, 3, 5, 7, 9]
        ]
    ]);

    // To add or update modules state
    $store->module('moduleName', [
        'data' => 'goes here'
    ]);
});
```

Assuming you have used the `@vuex` directive, and everything is installed properly, your vuex state should already be in place. If not, you will need to set `window.__INITIAL_STATE__` manually. The `Vuex::asArray()` or `Vuex::asJson()` accessors may be of use. Again, this should not be needed if you are using the `@vuex` directive, but is documented here for completeness.

```html
<script>window.__INITIAL_STATE__ = {!! Vuex::asJson() !!}</script>
```
