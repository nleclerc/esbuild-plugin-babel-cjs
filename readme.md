<div></div>

# esbuild-plugin-babel-cjs

[Babel](https://github.com/babel/babel) plugin for [esbuild](https://github.com/evanw/esbuild).

<br>

First, check if [esbuild supports](https://esbuild.github.io/content-types/) the transform you need _(it's faster)_.  
If not, you can add the Babel plugin you need with this plugin.

<br>

### Install

```zsh
npm install esbuild-plugin-babel-cjs -D
```

<br>

### Use

`esbuild.config.js`

```js
const esbuild = require('esbuild');
const babel = require('esbuild-plugin-babel');

esbuild
    .build({
        entryPoints: ['index.js'],
        bundle: true,
        outfile: 'main.js',
        plugins: [babel()],
        // target: ['es5'] // if you target es5 with babel, add this option
    })
    .catch(() => process.exit(1));
```

`package.json`

```json
{
    "scripts": {
        "start": "node esbuild.config.js"
    }
}
```

<br>

### Configure

`esbuild.config.js`

```js
babel({
    filter: /.*/,
    namespace: '',
    config: {} // babel config here or in babel.config.json
});
```

[`babel.config.json`](https://babeljs.io/docs/en/configuration)

```json
{
    "sourceMaps": "inline",
    "presets": [...],
    "plugins": [...]
}
```

<br>

### Check

[esbuild-serve](https://github.com/nativew/esbuild-serve) &nbsp; → &nbsp; Serve with live reload for esbuild.

[esbuild-plugin-pipe](https://github.com/nativew/esbuild-plugin-pipe) &nbsp; → &nbsp; Pipe esbuild plugins output.

[esbuild-plugin-svg](https://github.com/nativew/esbuild-plugin-svg) &nbsp; → &nbsp; Svg files import plugin for esbuild.

[esbuild-plugin-postcss-literal](https://github.com/nativew/esbuild-plugin-postcss-literal) &nbsp; → &nbsp; PostCSS tagged template literals plugin for esbuild.

<br>
