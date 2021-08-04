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
const withVanillaExtract = require("vanilla-extract-plugin-nextjs");

module.exports = withMDX(
  withVanillaExtract({
    pageExtensions: ["js", "jsx", "ts", "tsx", "md"],
  })
);
```

# Versions

For NextJs version 10, `npm install vanilla-extract-plugin-nextjs@version10`

For version 11, `npm install vanilla-extract-plugin-nextjs@latest`

# Cavebeats

This plugin emits warnings to the console:

```
...
Warning: Built-in CSS support is being disabled due to custom CSS configuration being detected.
See here for more info: https://nextjs.org/docs/messages/built-in-css-disabled
```

During development, it also emits this warnings repetitively. (This plugin uses a different setting to NOT emit assets in development, but DO emit them in production. This is necessary to make webpack's hot reload server to work.)

```
...
You did not set any plugins, parser, or stringifier. Right now, PostCSS does nothing. Pick plugins for your case on https://www.postcss.parts/ and use them in postcss.config.js.
```

# Inspiration

Thanks to @Mokshit06 to figure how to make it work in this [github issue](https://github.com/seek-oss/vanilla-extract/issues/4#issuecomment-810842869)
