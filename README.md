- See https://github.com/parcel-bundler/parcel/issues/1931
- `npm install`
- `npm start`
- Open http://localhost:1234/1.html
- Observe that _two_ JS files are loaded
- Modify CSS, observe HMR update
- Open http://localhost:1234/2.html
- Observe that _one_ JS files is loaded
- Modify CSS, observe _no_ HMR update
- Modify CSS again, observe console error:
```
Uncaught Error: Cannot find module 'node_modules/parcel-bundler/src/builtins/css-loader.js'
    at newRequire (main.1f19ae8e.js:39)
    at newRequire (main.1f19ae8e.js:23)
    at localRequire (main.1f19ae8e.js:55)
    at Object.eval (eval at hmrApply (main.1f19ae8e.js:230), <anonymous>:3:17)
    at newRequire (main.1f19ae8e.js:49)
    at hmrAccept (main.1f19ae8e.js:263)
    at main.1f19ae8e.js:148
    at Array.forEach (<anonymous>)
    at WebSocket.ws.onmessage (main.1f19ae8e.js:146)
```
