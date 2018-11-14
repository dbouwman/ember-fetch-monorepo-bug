# Stack Trace

```
=================================================================================

ENV Summary:

  TIME: Wed Nov 14 2018 07:37:22 GMT-0700 (MST)
  TITLE: ember
  ARGV:
  - /Users/dbouwman/.nvm/versions/node/v8.9.4/bin/node
  - /Users/dbouwman/.nvm/versions/node/v8.9.4/bin/ember
  - b
  EXEC_PATH: /Users/dbouwman/.nvm/versions/node/v8.9.4/bin/node
  TMPDIR: /var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T
  SHELL: /bin/zsh
  PATH:
  - /Users/dbouwman/.nvm/versions/node/v8.9.4/bin
  - /usr/local/bin
  - /Users/dbouwman/.rvm/bin
  - /usr/bin
  - /bin
  - /usr/sbin
  - /sbin
  - /usr/local/bin
  - /opt/X11/bin
  - /Users/dbouwman/.rvm/bin
  PLATFORM: darwin x64
  FREEMEM: 200560640
  TOTALMEM: 17179869184
  UPTIME: 244435
  LOADAVG: 5.814453125,4.04052734375,3.48388671875
  CPUS:
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  - Intel(R) Core(TM) i7-3720QM CPU @ 2.60GHz - 2600
  ENDIANNESS: LE
  VERSIONS:
  - ares: 1.10.1-DEV
  - cldr: 31.0.1
  - http_parser: 2.7.0
  - icu: 59.1
  - modules: 57
  - nghttp2: 1.25.0
  - node: 8.9.4
  - openssl: 1.0.2n
  - tz: 2017b
  - unicode: 9.0
  - uv: 1.15.0
  - v8: 6.1.534.50
  - zlib: 1.2.11

ERROR Summary:

  - broccoliBuilderErrorStack: Error: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
    at error (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:224:15)
    at Object.error (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:17174:21)
    at /Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:17183:29
    at <anonymous>
    at process._tickCallback (internal/process/next_tick.js:188:7)
  - codeFrame: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
  - errorMessage: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
        at Rollup
-~- created here: -~-
    at new Plugin (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/broccoli-plugin/index.js:7:31)
    at new Rollup (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/broccoli-rollup/dist/index.js:39:9)
    at treeForBrowserFetch (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-fetch/index.js:136:31)
    at Class.treeForVendor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-fetch/index.js:112:23)
    at Class._treeFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/models/addon.js:616:33)
    at Class.treeFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/models/addon.js:576:21)
    at project.addons.reduce (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:699:26)
    at Array.reduce (<anonymous>)
    at EmberApp._addonTreesFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:697:32)
    at EmberApp.addonTreesFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:721:17)
-~- (end) -~-
  - errorType: Build Error
  - location:
    - column: [undefined]
    - file: [undefined]
    - line: [undefined]
    - treeDir: [undefined]
  - message: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
        at Rollup
-~- created here: -~-
    at new Plugin (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/broccoli-plugin/index.js:7:31)
    at new Rollup (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/broccoli-rollup/dist/index.js:39:9)
    at treeForBrowserFetch (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-fetch/index.js:136:31)
    at Class.treeForVendor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-fetch/index.js:112:23)
    at Class._treeFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/models/addon.js:616:33)
    at Class.treeFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/models/addon.js:576:21)
    at project.addons.reduce (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:699:26)
    at Array.reduce (<anonymous>)
    at EmberApp._addonTreesFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:697:32)
    at EmberApp.addonTreesFor (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/ember-cli/lib/broccoli/ember-app.js:721:17)
-~- (end) -~-
  - name: BuildError
  - nodeAnnotation: [undefined]
  - nodeName: Rollup
  - originalErrorMessage: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
  - stack: Error: Couldn't find preset "env" relative to directory "/var/folders/d8/rshjcmrd3_dcshnzs8f0hw7h0000gp/T/broccoli-76156VKmrFUG5tIdB/cache-037-rollup/build/src"
    at error (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:224:15)
    at Object.error (/Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:17174:21)
    at /Users/dbouwman/dev/temp/env-bug/ember-fetch-monorepo-bug/node_modules/rollup/dist/rollup.js:17183:29
    at <anonymous>
    at process._tickCallback (internal/process/next_tick.js:188:7)

=================================================================================
```
