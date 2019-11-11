# webpack-5-expose-loader-bug
https://github.com/webpack/webpack/issues/9802#issuecomment-552418745
## Steps
1. Run `npm install` or `yarn`
2. Run `npm run build` or `yarn build`
```
Hash: 33325f57a00df5d4ea94
Version: webpack 5.0.0-beta.3
Time: 71ms
Built at: 2019-11-11 14:59:54
  Asset      Size
main.js  4.85 KiB  [emitted]  [name: main]
Entrypoint main = main.js
./src/index.js 35 bytes [built]
./node_modules/expose-loader?lib!./src/lib.js-exposed 56 bytes [built]
    + 4 hidden modules

ERROR in ./src/lib.js-exposed (./node_modules/expose-loader?lib!./src/lib.js-exposed) 1:33-55
Module not found: Error: Can't resolve '.\lib.js' in 'D:\Projects\webpack-5-expose-loader-bug\src'
 @ ./src/index.js 1:0-33
```
3. Switch to the `webpack-4` branch
4. Run `npm run build` or `yarn build`
```
Hash: 76b8ad894093c7cef5c6
Version: webpack 4.41.2
Time: 79ms
Built at: 2019-11-11 15:00:13
  Asset      Size  Chunks             Chunk Names
main.js  6.22 KiB    main  [emitted]  main
Entrypoint main = main.js
[./node_modules/expose-loader/index.js?lib!./src/lib.js-exposed] ./node_modules/expose-loader?lib!./src/lib.js-exposed 56 bytes {main} [built]
[./node_modules/webpack/buildin/global.js] (webpack)/buildin/global.js 472 bytes {main} [built]
[./src/index.js] 35 bytes {main} [built]
[./src/lib.js] 34 bytes {main} [built]
```
