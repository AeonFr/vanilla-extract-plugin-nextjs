# vanilla-extract-plugin-nextjs

A plugin to use `vanilla-extract` in a Next.js project.

Usage: wrap your `next.config.js` export in a function.

```js
# next.config.js
const withVanillaExtract = require("vanilla-extract-plugin-nextjs");

module.exports = withVanillaExtract({});
```

This plugin can be used in conjunction with others and with a custom config, example:

```js
const withMDX = require("@next/mdx")({ extension: /\.mdx$/ });
const withVanillaExtract = require("vanilla-extract-plugin-next");

module.exports = withMDX(
  withVanillaExtract({
    pageExtensions: ["js", "jsx", "ts", "tsx", "md"],
  })
);
```
