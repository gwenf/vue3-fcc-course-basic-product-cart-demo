# Product and Cart Static Code Demo

This is one of the companion repos to the Vue.js course on the freeCodeCamp YouTube channel.
You can see the different stages of development by checking out the other branches.

**Other Repos from this Tutorial Series**

- [Static files from initial lessons](https://github.com/gwenf/vue3-fcc-course-static-code)
- [Vue CLI Product Cart Demo](https://github.com/gwenf/vue3-fcc-course-vue-cli-product-cart-demo)

Special thanks to [TheJaredWilcurt](https://github.com/TheJaredWilcurt) for helping out with the initial static code and doing pretty much all of the styling.

## Building

As with most repos with a package.json, try running `npm ci` from the root of the repository.
However, because node-sass is compiled from C++ and depends on node's API structures, sass's version is pretty tightly coupled to nodes's version.
You'll need to tweak the version of see errors like this in the results of `npm ci`:
```
... zillions of lines ...
npm ERR! gyp ERR! build error 
npm ERR! gyp ERR! stack Error: `make` failed with exit code: 2
npm ERR! gyp ERR! stack     at ChildProcess.onExit (.../node_modules/node-gyp/lib/build.js:194:23)
npm ERR! gyp ERR! stack     at ChildProcess.emit (node:events:513:28)
npm ERR! gyp ERR! stack     at ChildProcess._handle.onexit (node:internal/child_process:291:12)
npm ERR! gyp ERR! System Linux 5.15.0-72-generic
npm ERR! gyp ERR! command "/usr/local/bin/node" ".../node_modules/node-gyp/bin/node-gyp.js" "rebuild" "--verbose" "--libsass_ext=" "--libsass_cflags=" "--libsass_ldflags=" "--libsass_library="
npm ERR! gyp ERR! cwd .../node_modules/node-sass
npm ERR! gyp ERR! node -v v18.8.0
npm ERR! gyp ERR! node-gyp -v v7.1.2
npm ERR! gyp ERR! not ok 
npm ERR! Build failed with error code: 1

npm ERR! A complete log of this run can be found in:
npm ERR!     .../_logs/2023-05-31T13_39_03_164Z-debug-0.log
```

As of node v18.8.0, `node-sass@^9.0.0` gave a clean install. Try `npm i -D node-sass@latest` or specify a version à la `npm i -D node-sass@^9.0.0`.
To pick a version, type `node --version` and look in [node-sass's README](https://github.com/sass/node-sass#node-version-support-policy) for the corresponding version of node-sass.
