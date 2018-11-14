# Ember-Cli 3.5 + Ember-Fetch 6.1.0 + Monorepo Bug

This is a repro example showing that Ember 3.5 + Ember Fetch 6.1.0 will throw errors during the build, when using a Monorepo.

We suspect this is related to the use of Rollup within Ember-Fetch as the same error happens w Ember Fetch 5.1.2+ which is where the Rollup integration was added.

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
- either `ember install ember-fetch` or switch to the `ember-fetch-installed` branch and run `yarn bootstrap` in the root again.
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

### State 3: Use old Build Pipeline
- with ember-fetch installed, run a build using the old build system - and it works.

```
➜  ember-app git:(ember-fetch-installed) ✗ EMBER_CLI_BROCCOLI_2=false ember b
Environment: development
cleaning up...
Built project successfully. Stored in "dist/".
```
