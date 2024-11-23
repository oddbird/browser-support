# browser-support

A web component for showing browser-support data
from the Web Features project.

This is inspired by the official
[`baseline-status` component](https://github.com/web-platform-dx/baseline-status)
from Google and the Web Platform DX community group.
It currently uses their `https://api.webstatus.dev/v1/features/` API.

## Features

- Stand-alone component, without Lit or other frameworks
- Responsive to font sizes, available space, and light/dark schemes
- Allows customization of the title markup (`h2` by default)
- 'Newly supported' web features show a timeline towards broad support
- Allows for simple light-dom fallback & progressive enhancement

**[Demo](https://oddbird.github.io/browser-support/index.html)**

## Examples

General usage example:

```html
<script type="module" src="browser-support.js"></script>

<browser-support data-feature="container-queries"></browser-support>

<!-- With a light-dom fallback… -->
<browser-support>
  <h3 slot="title">Container Style Queries</h3>
  <a href="https://web-platform-dx.github.io/web-features-explorer/features/container-style-queries/">
    Browser support data
  </a>
</browser-support>
```

## Installation

You have a few options (choose one):

1. Install via
   [npm](https://www.npmjs.com/package/@oddbird/browser-support):
   `npm install @oddbird/browser-support`
2. [Download the source manually from GitHub](https://github.com/oddbird/browser-support/releases)
   into your project.
3. Skip this step
   and use the script directly
   via a 3rd party CDN
   (not recommended for production use)

## Usage

Make sure you include the `<script>` in your project
(choose one, and update the version number as needed):

```html
<!-- Host yourself -->
<script type="module" src="browser-support.js"></script>
```

```html
<!-- 3rd party CDN, not recommended for production use -->
<script
  type="module"
  src="https://www.unpkg.com/@oddbird/browser-support@0.1.0/browser-support.js"
></script>
```

```html
<!-- 3rd party CDN, not recommended for production use -->
<script
  type="module"
  src="https://esm.sh/@oddbird/browser-support@0.1.0"
></script>
```

Or use the built-in
[WebC](https://www.11ty.dev/docs/languages/webc/) component
with [Eleventy](https://www.11ty.dev/docs/),
by adding `"npm:@oddbird/browser-support/*.webc"`
to the Eleventy WebC Plugin `components` registry:

```js
// Only one module.exports per configuration file, please!
module.exports = function (eleventyConfig) {
  eleventyConfig.addPlugin(eleventyWebcPlugin, {
    components: [
      // Add as a global WebC component
      "npm:@oddbird/browser-support/*.webc",
    ],
  });
}
```

### Slots

The `title` slot allows providing a fallback title,
and also the desired markup.
When the component is defined,
the actual title text will be replaced
with the name of the feature.

## ToDo

- [ ] Provide more clarity around the progress bar?
- [ ] Improve and document styling options
- [ ] List mobile browser support data
- [ ] Show browser versions (or how many versions back?)
- [ ] Allow changing title markup with an attribute?

## Support

At [OddBird](https://oddbird.net/),
we enjoy collaborating and contributing
as part of an open web community.
But those contributions take time and effort.
If you're interested in supporting our
open-source work,
consider becoming a
[GitHub sponsor](https://github.com/sponsors/oddbird),
or contributing to our
[Open Collective](https://opencollective.com/oddbird-open-source).

❤️ Thanks!

## Credit

With thanks to the following people:

- [David Darnes](https://darn.es/) for the
  [Web Component repo template](https://github.com/daviddarnes/component-template)
  that this one is based on.
