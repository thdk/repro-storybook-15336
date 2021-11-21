# reproduction of issue https://github.com/storybookjs/storybook/issues/15336

## project setup

node 16 with npm workspaces

```
root
 -- package.json
 -- packages
       storybook
       -- package.json
```

## steps to reproduce
```shell
 npm i
 npm run build-storybook --workspaces   
```

console output
```
➜  storybook-workspaces git:(main) npm run build-storybook -w storybook

> storybook@0.1.0 build-storybook
> build-storybook -s public

info @storybook/react v6.3.12
info 
info => Cleaning outputDir: /home/thdk/repos/storybook-workspaces/packages/storybook/storybook-static
info => Copying static files: ./public => ./
info => Loading presets
info => Compiling preview..
info => Loading Webpack configuration from `../../node_modules/react-scripts`
info => Removing existing JavaScript and TypeScript rules.
info => Modifying Create React App rules.
info => Using default Webpack5 setup
9% setup compilation DocGenPlugin(node:15160) [DEP0148] DeprecationWarning: Use of deprecated folder mapping "./" in the "exports" field module resolution of the package at /home/thdk/repos/storybook-workspaces/node_modules/postcss-safe-parser/node_modules/postcss/package.json.
Update this package.json to use a subpath pattern like "./*".
(Use `node --trace-deprecation ...` to show where the warning was created)
(node:15160) [DEP_WEBPACK_MAIN_TEMPLATE_RENDER_MANIFEST] DeprecationWarning: MainTemplate.hooks.renderManifest is deprecated (use Compilation.hooks.renderManifest instead)
(node:15160) [DEP_WEBPACK_CHUNK_TEMPLATE_RENDER_MANIFEST] DeprecationWarning: ChunkTemplate.hooks.renderManifest is deprecated (use Compilation.hooks.renderManifest instead)
(node:15160) [DEP_WEBPACK_MAIN_TEMPLATE_HASH_FOR_CHUNK] DeprecationWarning: MainTemplate.hooks.hashForChunk is deprecated (use JavascriptModulesPlugin.getCompilationHooks().chunkHash instead)
node:internal/modules/cjs/loader:933
  const err = new Error(message);
              ^

Error: Cannot find module 'webpack/lib/util/makeSerializable.js'
Require stack:
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/dependency.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/plugin.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/index.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/dist/cjs/server/framework-preset-react-docgen.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/core-common/dist/cjs/presets.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/core-common/dist/cjs/index.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/node_modules/@storybook/core-server/dist/cjs/index.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/dist/cjs/server.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/server.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/dist/cjs/server/build.js
- /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/bin/build.js
    at Function.Module._resolveFilename (node:internal/modules/cjs/loader:933:15)
    at Function.Module._load (node:internal/modules/cjs/loader:778:27)
    at Module.require (node:internal/modules/cjs/loader:1005:19)
    at require (node:internal/modules/cjs/helpers:102:18)
    at Object.<anonymous> (/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/dependency.js:6:55)
    at Module._compile (node:internal/modules/cjs/loader:1101:14)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at Module.require (node:internal/modules/cjs/loader:1005:19)
    at require (node:internal/modules/cjs/helpers:102:18)
    at /home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/plugin.js:108:42
    at Hook.eval [as call] (eval at create (/home/thdk/repos/storybook-workspaces/packages/storybook/node_modules/webpack/node_modules/tapable/lib/HookCodeFactory.js:19:10), <anonymous>:305:1)
    at Hook.CALL_DELEGATE [as _call] (/home/thdk/repos/storybook-workspaces/packages/storybook/node_modules/webpack/node_modules/tapable/lib/Hook.js:14:14)
    at Compiler.newCompilation (/home/thdk/repos/storybook-workspaces/packages/storybook/node_modules/webpack/lib/Compiler.js:1055:26)
    at /home/thdk/repos/storybook-workspaces/packages/storybook/node_modules/webpack/lib/Compiler.js:1099:29 {
  code: 'MODULE_NOT_FOUND',
  requireStack: [
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/dependency.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/plugin.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react-docgen-typescript-plugin/dist/index.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/dist/cjs/server/framework-preset-react-docgen.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/core-common/dist/cjs/presets.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/core-common/dist/cjs/index.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/node_modules/@storybook/core-server/dist/cjs/index.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/dist/cjs/server.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/core/server.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/dist/cjs/server/build.js',
    '/home/thdk/repos/storybook-workspaces/node_modules/@storybook/react/bin/build.js'
  ]
}
```
