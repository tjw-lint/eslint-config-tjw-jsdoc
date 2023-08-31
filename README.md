# eslint-config-tjw-jsdoc

The Jared Wilcurt's strict JSDoc ESLint rules for obsessives.


## Using this

1. `npm install --save-dev eslint-plugin-jsdoc eslint-config-tjw-jsdoc`
1. In your `.eslitrc.js` add `tjw-jsdoc` to your `extends` like so:
    ```js
    module.exports = {
      extends: [
        'tjw-jsdoc'
      ]
    };
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
