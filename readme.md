Statamix supports Laravel Mix's `mix.version()` cache busting API, as well as hot reloading.

If you're familiar with Mix within Laravel, this should feel similar.

## Installation

As a git submodule, from your project root:

```bash
git submodule add git@github.com:sagalbot/statamix.git site/addons/Mix
```

## Configuration

Statamix makes a few assumptions about your setup:

- You're running [Statamic above webroot](https://docs.statamic.com/knowledge-base/running-above-webroot) with `public/index.php` 
- Mix will compile to `public/dist`
- `package.json` lives in the root directory

Why? This setup is pretty consistent with a plain Laravel project. 

- Keeping site files out of the site root is a good idea for security. 
- Placing your `package.json` file in the root folder means you don't 
have to `cd` into your theme to add a dependency, or start the build 

## Usage

Available Tags:

- `mix:css` 
- `mix:js`

##### `{{ mix:css }}`

```handlebars
  <link rel="stylesheet" href="{{ mix:css }}">
  
  <!-- will render -->
  <link rel="/dist/sagalbot.css?id=5db0aa442df0520ca63d">
```

##### `{{ mix:js }}`

```handlebars
  <script src="{{ mix:js }}"></script>
  
  <!-- will render -->
  <script src="/dist/sagalbot.js?id=5db0aa442df0520ca63d"></script>
```
