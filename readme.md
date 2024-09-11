# Adze

![Adze Logo](docs/assets/logo_small.png)

[![build workflow](https://github.com/AJStacy/adze/actions/workflows/build.yml/badge.svg)](https://github.com/AJStacy/adze/actions/workflows/build.yml)
![npm](https://img.shields.io/npm/v/adze) [![Rate this package](https://badges.openbase.com/js/rating/adze.svg?token=2JRA+eWqLSPTPaqboGXMHy1EnX0DY98eE9VidXDvPLg=)](https://openbase.com/js/adze?utm_source=embedded&amp;utm_medium=badge&amp;utm_campaign=rate-badge) ![node-lts](https://img.shields.io/node/v-lts/adze) [![size](https://badgen.net/bundlephobia/minzip/adze)](https://bundlephobia.com/result?p=adze) [![dependency count](https://badgen.net/bundlephobia/dependency-count/adze)](https://bundlephobia.com/result?p=adze) [![apache 2.0](https://badgen.net/npm/license/adze)](/LICENSE.md)

**Please visit our official docs at [adzejs.com](http://www.adzejs.com/).**

## Why is this named Adze?

![A drawing of a man using an adze to shape a log](./docs/guide/assets/adze.png)

_Photo from [Wikipedia](https://en.wikipedia.org/wiki/Adze)_

> Adze - [a cutting tool that ... is used chiefly for shaping wood](https://www.merriam-webster.com/dictionary/adze).

(Pronounced ["Ads"](https://dictionary.cambridge.org/us/pronunciation/english/adze)) Adze was chosen as a name for this library to maintain solidarity with the logging puns and to emphasize that this library is a tool for shaping the logs of your application.

## Why should I use Adze?

As you may already be aware there are a number of other good JS libraries out there to assist with logging. The focus of Adze is to provide a convenient and clean API, provide first-class TypeScript support, and to empower you to take command of your logs rather than pigeon-hole you into a specific way of handling them.

Here is a list of the features that Adze provides:

- First-class TypeScript support
- Multi-environment support for the Browser and Node
- Wraps and extends the entire standard API
- A fluent, chainable API
- Log Listeners for capturing log data
- Log annotation namespaces, labels, and other meta data
- Attractive styling (EMOJI'S INCLUDED and consistent across major browsers)
- Everything is configurable
- Enables completely custom log levels
- A global log store for recalling logs and overriding configuration (supports micro-frontends and modules)
- Support for Mapped Diagnostic Context
- Convenient unit testing environment controls
- Advanced Log Filtering
- and much more...

Beyond the new features that Adze provides you, it also wraps the entire console web standard.
Read more about the standard here: [MDN Console Docs](https://developer.mozilla.org/en-US/docs/Web/API/console)

### Here is a simple preview:

![Preview of Adze logs](./docs/guide/assets/demo.png)

> This preview was generated from the same code executed in both the browser (left) and the node (right) environments.

## What does the API look like?

As stated above, Adze offers an easy to use, chainable API. To create a log you simply chain together an Adze log instance with a series of modifiers and then end with a terminator. Here's an example of creating a log with emoji's and a namespace:

```typescript
import adze, { createShed } from 'adze';

// Create our global log in-memory cache
const shed = createShed();

// Listen to logs that are generated and operate on them
shed.addListener('*', (data, render, printed) => {
  // if my log printed to the console
  if (printed) {
    // do stuff with my log data like sending to an API or localStorage
  }
});

adze({ useEmoji: true }).ns('tix-456').log('Example log');
```

The output of this would look like the following:

![Preview of Adze logs](./docs/guide/examples/api_example_output.png)

## Install the Package

You can install Adze from NPM using the following command:

```bash
# NPM
npm install --save adze

# Yarn
yarn add adze
```

## Version Requirements

| Dependency | Supported Versions | Notes                                    |
| ---------- | ------------------ | ---------------------------------------- |
| node       | >= 10.x            | When running Adze in a Node environment. |
| typescript | >= 4.1             | When using Adze with TypeScript          |

## TypeScript Configuration

Adze is built to be used with TypeScript and we highly encourage using it in this way.

When building your project with TypeScript, you need to make sure you use the `"DOM"` lib because Adze supports both the web browser and Node. Also, to support the dependencies of Adze, you'll need to add `"esModuleInterop": true` to your tsconfig as well.

For more information about configuring TypeScript, go to [https://www.typescriptlang.org/docs/handbook/tsconfig-json.html](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

### Example

```json
{
  "compilerOptions": {
    // ...your other options
    "lib": ["DOM"],
    "esModuleInterop": true
  }
}
```

## Importing Adze

Adze comes bundled with a few different ways of accessing it. Here are some examples:

### CDN

You can import the library directly into your HTML from the [jsDelivr](https://www.jsdelivr.com/package/npm/adze) CDN.

_**NOTE:** In the script tag in the example below, replace `<version>` with the version of Adze you would like to use._

```html
<!-- In the head of your html -->
<head>
  <!-- To use v1.3.0 you would write https://cdn.jsdelivr.net/npm/adze@1.3.0/dist/adze.min.js -->
  <script src="https://cdn.jsdelivr.net/npm/adze@<version>/dist/adze.min.js"></script>
</head>

<!-- Using adze elsewhere in JS -->
<script>
  // Adze is registered globally in your browser as AdzeLib
  const { adze } = AdzeLib;

  adze().log('Hello World!');
</script>
```

### Node JS (CommonJS)

```javascript
const { adze } = require('adze'); // Or alternatively `const adze = require('adze').adze;`

adze().log('Hello World!');
```

### ES6 / TypeScript

```typescript
import adze from 'adze';

adze().log('Hello World!');
```

## Documentation

**Please visit our official docs at [adzejs.com](http://www.adzejs.com/).**
