# applicationinsightsfornuxt

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![Circle CI][circle-ci-src]][circle-ci-href]
[![Codecov][codecov-src]][codecov-href]
[![Dependencies][david-dm-src]][david-dm-href]
[![Standard JS][standard-js-src]][standard-js-href]

> ApplicationInsights module for Nuxt.js

## Features

The module enables event logging through [Application Insights](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview).

## Setup
- Add `applicationinsightsfornuxt` dependency using npm to your project
- Add `applicationinsightsfornuxt` to `modules` section of `nuxt.config.js`

```js
{
  modules: [
    'applicationinsightsfornuxt',
  ],

  appInsights: {
    instrumentationKey: '' //  your project's Instrumentation Key here
  }
}
```

### Nuxt compatibility
Versions of NuxtJS before v2.4.0 are **not** supported by this package.

## Usage

Enter your Instrumentation Key in the NuxtJS config file. Additional config settings can be found [server](https://github.com/Microsoft/ApplicationInsights-node.js#advanced-configuration-options) and [client](https://github.com/microsoft/ApplicationInsights-JS#configuration).

### Usage in Vue component

In a Vue component, `Application Insights` is available as `this.$appInsights`, so we can call functions like

```
this.$appInsights.trackTrace({message: 'This message will use a telemetry initializer'})
```

where `this` is a Vue instance.

## Options

Options can be passed using either environment variables or `appInsights` section in `nuxt.config.js`.
Normally setting required Instrumentation Key information would be enough.

### instrumentationKey
- Type: `String`
  - Default: `process.env.APPINSIGHTS_INSTRUMENTATION_KEY || false`
  - If no `instrumentationKey` is provided module wont work

### disabled
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_DISABLED || false`
  - ApplicationInsights will not be initialised if set to `true`.

### disableClientSide
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_DISABLE_CLIENT_SIDE || false`

### disableServerSide
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_DISABLE_SERVER_SIDE || false`

### initialize
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_INITIALIZE || true`

### trackPageView
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_TRACK_PAGE_VIEW || true`

### sendLiveMetrics
- Type: `Boolean`
  - Default: `process.env.APPINSIGHTS_SEND_LIVE_METRICS || false`

### serverConfig
- Type: `Object`
  - Default: `{
  }`
  - If specified, values will override config values for server Application Insights plugin

### clientConfig
- Type: `Object`
  - Default: `{
  }`
  - If specified, values will override config values for client Application Insights plugin


## License
[MIT License](./LICENSE)

Copyright (c) Jesús Verduzco

This module is based on: https://github.com/nuxt-community/applicationinsights-module

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/dt/applicationinsightsfornuxt.svg?style=flat-square
[npm-version-href]: https://npmjs.com/package/applicationinsightsfornuxt
[npm-downloads-src]: https://img.shields.io/npm/v/applicationinsightsfornuxt/latest.svg?style=flat-square
[npm-downloads-href]: https://npmjs.com/package/applicationinsightsfornuxt
[circle-ci-src]: https://img.shields.io/circleci/project/github/nuxt-community/applicationinsights-module.svg?style=flat-square
[circle-ci-href]: https://circleci.com/gh/nuxt-community/applicationinsights-module
[codecov-src]: https://img.shields.io/codecov/c/github/nuxt-community/applicationinsights-module.svg?style=flat-square
[codecov-href]: https://codecov.io/gh/nuxt-community/applicationinsights-module
[david-dm-src]: https://david-dm.org/nuxt-community/applicationinsights-module/status.svg?style=flat-square
[david-dm-href]: https://david-dm.org/nuxt-community/applicationinsights-module
[standard-js-src]: https://img.shields.io/badge/code_style-standard-brightgreen.svg?style=flat-square
[standard-js-href]: https://standardjs.com
