# template

[![styled with prettier][prettier.icon]][prettier.url]

Template for **experimental** Firefox [WebExtensions][] that use [libdweb][] APIs.

### Expriments

As of this writing [libdweb][] is an **experiment** to enable dweb community and Mozilla to prototype dweb explorations as Firefox experimental [WebExtensions][].

[WebExtensions][] that include [experimental APIs][webextension experiments] like [libdweb][] are meant for experimentation and come with set of restrictions:

1.  They can not be hosted on http://addons.mozilla.org/
2.  They can be only be installed on Firefox [Developer Edition][] and [Nightly][] builds.
3.  To try such an extension some preferences in [about:config](about:config) need to be changed.

There are many ways how such experiments can be built and distributed but this template provides opinionated configuration that can customized for more advanced use cases.

## Usage

To get started fork or clone this template and install all the necessary toolchain via [npm][] or [yarn][].

```sh
git clone git@github.com:libdweb/template.git
cd temlpate
npm install # or yarn
```

Template is setup such that it includes `run`, `test` and `build` your experiment.

### Run

You can run web-extension by running

```
npm start
```

You can also run with some dev tooling by running

```
npm run dev
```

### Test

You can write test WebExtensions like one in the `test` directory, which will run headless Firefox [Nightly][]

```
npm test
```

### Build

You can build WebExtension by running following command

```
npm run build
```

> **Note**: Will produce zip file in `web-ext-artifacts` directory                                                        

## Distribute

You can share your experiment with others, by sending a build artifact with your audience. They will be able to try it on Firefox [Nightly][] and [Developer Edition][] after performing several steps:

### 1. Configure 

First they will need to set following preferences by navigating to `about:config`

```
xpinstall.signatures.required: false
extensions.legacy.enabled: true
```

### 2. Install

Then they will need to navigate to `about:addons` and install build artifact via "Install Add-On From File..." menu item.

![install preview][]


[webextension experiments]: https://webextensions-experiments.readthedocs.io/en/latest/index.html
[web-ext]: https://www.npmjs.com/package/web-ext
[libdweb]: https://github.com/mozilla/libdweb
[developer edition]: https://www.mozilla.org/en-US/firefox/channel/desktop/#developer
[nightly]: https://www.mozilla.org/en-US/firefox/channel/desktop/#nightly
[npm]: http://npmjs.com/
[yarn]: http://yarnpkg.com/
[prettier.icon]: https://img.shields.io/badge/styled_with-prettier-ff69b4.svg
[prettier.url]: https://github.com/prettier/prettier
[webextensions]: https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions
[install preview]:install.png