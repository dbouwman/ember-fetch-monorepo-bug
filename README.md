# Ember-Fetch + Monorepo Bug

This is a repro example showing that Ember 3.5 + Ember Fetch 6.1.0 will throw errors during the build, when using a Monorepo.

We suspect this is related to the use of Rollup within Ember-Fetch.

## Repro Steps
- clone this repo
- ensure you have `lerna` installed globally (`npm i -g lerna`)
- ensure you have `yarn`
- in the root, run `yarn bootstrap` to install all the deps

### State 1: No Ember-Fetch - Build is Fine...
- `cd packages/ember-app`
- `ember b` - this should succeed with the following:

```
➜  ember-app git:(master) ✗ ember b
Environment: development
cleaning up...
Built project successfully. Stored in "dist/".
```

### State 2: Ember-Fetch ^6.1.0
- either `ember install ember-fetch` or switch to the `ember-fetch-installed` branch
- run a build with `ember b`

This will fail with a message like:

```
➜  ember-app git:(ember-fetch-installed) ✗ ember b
Environment: development
(node:76156) UnhandledPromiseRejectionWarning: Unhandled promise rejection (rejection id: 1): Error: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
(node:76156) [DEP0018] DeprecationWarning: Unhandled promise rejections are deprecated. In the future, promise rejections that are not handled will terminate the Node.js process with a non-zero exit code.
(node:76156) PromiseRejectionHandledWarning: Promise rejection was handled asynchronously (rejection id: 1)
cleaning up...
Build Error (Rollup)

Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"


Stack Trace and Error Report: /var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/error.dump.a7d6df92295e51ce96d01a261577f0ce.log
```

[View the Stack Trace](stacktrace.md)

## Other Info
- we do not get this build error when using Ember-Fetch 5.1.1, which does not use Rollup.
- In one of our apps, we use `ember-impagination`, which also installs `ember-browserify`. What is interesting is that when we install `ember-browserify` in this demo app, along with `ember-fetch@6.1.0`, we get build warnings, but the build *works*. The warning is below, but I *suspect* the reason the build works is that it's falling back to the `broccoli-builder`.

```
➜  ember-app git:(ember-fetch-installed) ✗ ember b
WARNING: Invalid Broccoli2 node detected, falling back to broccoli-builder. Broccoli error:
---------------
ember-browserify: The .read/.rebuild API is no longer supported as of Broccoli 1.0. Plugins must now derive from broccoli-plugin. https://github.com/broccolijs/broccoli/blob/master/docs/broccoli-1-0-plugin-api.md
used as input node to BroccoliMergeTrees
-~- created here: -~-
    at BroccoliMergeTrees.Plugin (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/broccoli-plugin/index.js:7:31)
    at new BroccoliMergeTrees (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-browserify/node_modules/broccoli-merge-trees/index.js:42:10)
    at Class.postprocessTree (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-browserify/lib/index.js:79:14)
    at projectOrAddon.addons.reduce (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/utilities/addon-process-tree.js:6:25)
    at Array.reduce (<anonymous>)
    at addonProcessTree (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/utilities/addon-process-tree.js:4:32)
    at callAddonsPostprocessTreeHook (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/default-packager.js:43:10)
    at DefaultPackager.processJavascript (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/default-packager.js:530:41)
    at DefaultPackager.processAppAndDependencies (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/default-packager.js:254:35)
    at DefaultPackager.packageJavascript (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/default-packager.js:1296:32)
-~- (end) -~----------------

Environment: development
[API] Warning: The .read and .rebuild APIs will stop working in the next Broccoli version
[API] Warning: Use broccoli-plugin instead: https://github.com/broccolijs/broccoli-plugin
[API] Warning: Plugin uses .read/.rebuild API: ember-browserify
[API] Warning: Plugin uses .read/.rebuild API: ember-browserify
cleaning up...
Built project successfully. Stored in "dist/".
```
