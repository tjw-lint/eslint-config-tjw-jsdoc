# eslint-config-tjw-jsdoc

The Jared Wilcurt's premium JSDoc ESLint rules.


## Using this

This assumes you have ESLint 9+ already set up, if not, refer to [this guide](https://github.com/tjw-lint/eslint-config-tjw-base).


1. `npm install --save-dev eslint-plugin-jsdoc eslint-config-tjw-jsdoc`
1. In your `eslint.config.js`:
    ```js
    import tjwJsdoc from 'eslint-config-tjw-jsdoc';

    export default [
      ...tjwJsdoc,
      {
        // Your project specific settings
      }
    ];
    ```


* * *


## What does it look like?

The linter will enforce the formatting and types for functions arguments/returns.

Below is an example function and what the formatting looks like for its comment block.

* A description is required (and must end in a period). Followed by a return. This explains what the function does, and why it exists.
* All arguments and return require a type, but can be an imported interface if complex/reusable. (see: [ESM Example](https://thejaredwilcurt.com/vue-snapshot-serializer/#types) or [CJS example](https://github.com/nwutils/create-desktop-shortcuts/blob/main/api-type-definitions.js))
* All argument names must match the code (to ensure the comment isn't outdated).
* All arguments and return must have description text explaining what they are/why they exist.
* If the function returns a value, then the `@return` and a description will be required.
* If the function has no `return`, then the JSDoc comment must remove the `@return` line.
* You can optionally include an `@example` after the main description and it will be formatted.
* Almost all formatting can be applied automatically with ESLint's `--fix`. Including the vertically aligned columns for @token/{type}/name/description.

```js
/** @typedef {import('../types.js').OPTIONS} OPTIONS */

/**
 * Generic validation method to ensure a specific key on the options
 * object is either a string, or removed.
 *
 * @example
 * options = validateOptionalString(options, 'name');
 *
 * @param  {OPTIONS} options  User's options
 * @param  {string}  key      The key on the user's options object to be validated as an optional string
 * @return {OPTIONS}          Validated or mutated user options
 */
function validateOptionalString (options, key) {
  if (
    typeof(options) === 'object' &&
    Object(options).hasOwnProperty(key) &&
    typeof(options[key]) !== 'string'
  ) {
    console.warn(options, 'Optional ' + key + ' must be a string');
    delete options[key];
  }
  return options;
}
```


* * *


Pairs really well with:

* Sublime Text plugin - [DocBlockr](https://packagecontrol.io/packages/DocBlockr) - Best in class
* VS Codium plugin - [VS DocBlockr](https://github.com/jeremyvii/vs-docblockr) - Not as good as the SublimeText one, but not bad
* IntelliJ based editors (WebStorm, etc) have a [built in plugin you can enable](https://www.jetbrains.com/help/idea/creating-jsdoc-comments.html#ws_js_preview_jsdoc_comments_rendered_in_the_editor), but it's not open source, it's handled by Jet Brains, and it's almost completely useless. But you can still enable it and try it out. If enough people turn it on, maybe they'll prioritize making it better.

But the point of using ESLint to enforce this is so that you don't have to do editor-specific things. Any team can adopt this approach and each dev can make ESLint work with whatever tools they use.


* * *


**See also:**

* [eslint-config-tjw-base](https://github.com/tjw-lint/eslint-config-tjw-base) - Basic JavaScript Linting
* [eslint-config-tjw-import](https://github.com/tjw-lint/eslint-config-tjw-import) - Lint import/require statements
* [eslint-config-tjw-jest](https://github.com/tjw-lint/eslint-config-tjw-jest) - Lint Jest/Vitest Unit Tests
* [eslint-config-tjw-jsdoc](https://github.com/tjw-lint/eslint-config-tjw-jsdoc) - Enforce JSDoc comment blocks
* [eslint-config-tjw-vue](https://github.com/tjw-lint/eslint-config-tjw-vue) - Lint Vue files
