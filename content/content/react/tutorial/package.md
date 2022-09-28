# react componnet package

Funciona

- iniciar un nuevo packete en npm

- instalar dependencias
  
  ```json
  npm i --save-dev react react-dom
  ```

- dentro del packaje.json agregaremos, creo que esto se hace para no tener coliciones de verciones de react.
  
  ```json
  "peerDependencies": {
          "react": "^17.0.2",
      "react-dom": "^17.0.2"
  }
  ```

- Para testiar los componentes vamos a intarlar storybook(NO SIRVE): Si lo tratas de iniciar dara error.

```json
npx sb init
```

- Para empezar a testiar tu componente en storybook, vamos a crear un archivo que se llame componenet-name.stories.js (NO SIRVE):

- Para poder copilar todo el package se va a usar rollup.js.

```json
npm i --save-dev rollup rollup-plugin-babel @rollup/plugin-node-resolve rollup-plugin-peer-deps-external @babel/preset-react rollup-plugin-postcss rollup-plugin-terser
```

> **[rollup-plugin-babel](https://github.com/rollup/rollup-plugin-babel) esta decaprecaited pero funciona , ahora se puede usar @rollup/plugin-babel**

Usando **@rollup/plugin-babe**Usando **@rollup/plugin-babe**

```json
npm i --save-dev rollup **@rollup/plugin-babel**  @rollup/plugin-node-resolve rollup-plugin-peer-deps-external @babel/preset-react rollup-plugin-postcss rollup-plugin-terser
```

- Archivo de configuracion rollup.config.js

```jsx
import babel from 'rollup-plugin-babel';
import resolve from '@rollup/plugin-node-resolve';
import external from 'rollup-plugin-peer-deps-external';
import postcss from 'rollup-plugin-postcss';
import {terser} from 'rollup-plugin-terser';
export default [
    {
        input: './src/index.js',
        output: [
            {
                file: './dist/index.js',
                format: 'cjs'
            },
            {
                file: './dist/index.es.js',
                format: 'es',
                exports: 'named' 
            }
        ],
        plugins: [
            postcss({
                plugins: [],
                minimize: true
                }),
            babel({
                exclude: 'node_modules/**',
                presets: ['@babel/preset-react']
            }),
            external(),
            resolve(),
            terser()
        ]
    }
];
```

Usando **@rollup/plugin-babe**Usando **@rollup/plugin-babe**

```jsx
import { babel } from '@rollup/plugin-babel';
import resolve from '@rollup/plugin-node-resolve';
import external from 'rollup-plugin-peer-deps-external';
import postcss from 'rollup-plugin-postcss';
import {terser} from 'rollup-plugin-terser';
export default [
    {
        input: './src/index.js',
        output: [
            {
                file: './dist/index.js',
                format: 'cjs'
            },
            {
                file: 'dist/index.es.js',
                format: 'es',
                exports: 'named' 
            }
        ],
        plugins: [
            postcss({
                plugins: [],
                minimize: true
                }),
            babel({
                exclude: 'node_modules/**',
                presets: ['@babel/preset-react'],
                babelHelpers: 'bundled'
            }),
            external(),
            resolve(),
            terser()
        ]
    }
];
```

- en tu package.json crea un nuevo script, para inciar rollup

```json
"build": "rollup -c"
```

- Por ultimo tenemos que agregar esto al package.json

```json
"main": "dist/index.js",
"module": "dist/index.es.js",
```
