# Api Reference

Namespace:
```php
use ReedJones\Vuexcellent\Facades\Vuex;
```

## Static Methods


```php
Vuex::store(Closure $closure);
```

Passing a Closure function to the static `store` method, will receive an injected Vuex instance that can be used to update the end result vuex state.

Example:
```php
Vuex::store(function($store) {
    // update $store
});
```

---

```php
$data = Vuex::asArray();
```
Formats all currently supplied data into an array matching Vuex hierarchy, for easy merging.

---
```php
$json = Vuex::asJson();
```
Same as the above `asArray` however Json encoded.

---

## Instance Methods

```php
$store->state($data);
```
`state` accepts a single argument which can be either an `array`, or a Laravel Collection (`\Illuminate\Support\Collection`);

---

```php
$store->module($namespace, $data);
```
`module` accepts two arguments. The first is a string, and will be used as the vuex module name. The second is an `array` or `\Illuminate\Support\Collection` which will be used as the state for the module.

---

## Blade Directives
```
@vuex
```

Behind the scenes `@vuex` expands into

```php
<script id='initial-state'>
    window.__INITIAL_STATE__ = <?php echo ReedJones\Vuexcellent\Facades\Vuex::asJson(); ?>
</script>
```
---

```
@app
```

`@app` is just a shorthand for `<div id="app"></div>`
