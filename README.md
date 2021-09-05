> **This plugin is deprecated and will no longer be mantained**. It's recommended to use the official plugin, currently being developed ([see PR status](https://github.com/seek-oss/vanilla-extract/pull/336#pullrequestreview-746644897)) but very soon availabe at: `@vanilla-extract/next-plugin`.
>
> This package will be kept published until we're 100% sure the official plugin works for Next 10 and 11 and until consumers have time to migrate.
>
> **Eventually, though, this package will stop being mantained and eventually unpublished and archived. Be advised!**

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

# Caveats

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
