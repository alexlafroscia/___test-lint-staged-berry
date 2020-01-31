# test-lint-staged-berry

Demo repo for incompatibility between Yarn 2 and `lint-staged`

## Reproduction

1. Have any version of `yarn` installed (this repo provides `yarn@berry` for you)
2. Clone this repo
3. Run `yarn lint-staged`
4. Observe error similar to the following:

    ```txt
    /Users/alafroscia/Code/mi/test-lint-staged-berry/.yarn/cache/any-observable-npm-0.3.0-4832f4f3ed-1.zip/node_modules/any-observable/register.js:29
        throw new Error('Cannot find any-observable implementation nor' +
		^

    Error: Cannot find any-observable implementation nor global.Observable. You must install polyfill or call require("any-observable/register") with your preferred implementation, e.g. require("any-observable/register")('rxjs') on application load prior to any require("any-observable").
        at loadImplementation (/Users/alafroscia/Code/mi/test-lint-staged-berry/.yarn/cache/any-observable-npm-0.3.0-4832f4f3ed-1.zip/node_modules/any-observable/register.js:29:9)
        at /Users/alafroscia/Code/mi/test-lint-staged-berry/.yarn/cache/any-observable-npm-0.3.0-4832f4f3ed-1.zip/node_modules/any-observable/loader.js:30:18
        at Object.<anonymous> (/Users/alafroscia/Code/mi/test-lint-staged-berry/.yarn/cache/any-observable-npm-0.3.0-4832f4f3ed-1.zip/node_modules/any-observable/index.js:2:39)
        at Module._compile (internal/modules/cjs/loader.js:778:30)
        at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
        at Module.load (internal/modules/cjs/loader.js:653:32)
        at Function.module_1.Module._load (/Users/alafroscia/Code/mi/test-lint-staged-berry/.pnp.js:15661:14)
        at Module.require (internal/modules/cjs/loader.js:692:17)
        at require (internal/modules/cjs/helpers.js:25:18)
        at Object.<anonymous> (/Users/alafroscia/Code/mi/test-lint-staged-berry/.yarn/cache/@samverschueren-stream-to-observable-npm-0.3.0-3da2ac7de0-1.zip/node_modules/@samverschueren/stream-to-observable/index.js:2:20)
    ```
