# Introduction

A Vuex preloader for Laravel.

![Excellent](./excellent.gif)

Vuexcellent is a set of libraries to help load data from your laravel backend to your Vue app during the initial page load. The general idea is to set your desired vuex state from within Controllers or Models, and have it instantly available without needing to juggle passing the data in through props, or make extra api calls to load the initial data. Once installed, usage is designed to be quite straight forward.

```php
// PostController.php

public function index() {
    // Set the initial vue state
    Vuex::store(function($store) {
        $store->state([
            'posts' => Posts::paginate(15)
        ]);
    });

    // Navigate to the view as
    // you normally would
    return view('blogPosts');
}
```

```html
<template>
    <div v-for="post in $store.state.posts" :key="post.id">
        <a :href="`/posts/${post.slug}`">{{ post.title }}</a>
    </div>
</template>
```

And thats it! ...sort of.
