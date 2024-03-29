# nimrod

This project was generated with [ngX-Rocket](https://github.com/ngx-rocket/generator-ngx-rocket/)
version 7.1.0

# Getting started

```
>ngx new
          __   __
 _ _  __ _\ \./ / ____ ____ ____ _  _ ____ ___
| ' \/ _` |>   <  |--< [__] |___ |-:_ |===  |
|_||_\__, /_/°\_\ ENTERPRISE APP STARTER -~*=>
     |___/ v7.1.0

? What is the name of your app? nimrod
? What kind of app do you want to create? Web app, Desktop app (using Electron)
? Do you want a progressive web app? (with manifest and service worker) Yes
? Which desktop platform do you want to support? (Press <space> to select, <a> to toggle all, <i> to invert selection)Windows, macOS, Linux
? Which UI framework do you want? Ionic (more mobile-oriented)
? Which kind of layout do you want? Side menu with split panels (more app-oriented)
? Do you want authentication? Yes
? Do you want lazy loading? Yes
? Do you want analytics support (with Angulartics2)? Yes
? What analytics provider are you using? Other
? Do you want additional tools? Prettier (automatic code formatting), Hads (markdown-based doc system), Compodoc (Angular doc generator)
? Do you want additional libraries? Lodash (collection & general utilities), Moment.js (date management)
```

Had the following issue on generateion:

```
> electron@5.0.11 postinstall C:\Users\timof\repos\temp\web-electron-rocket\node_modules\electron
> node install.js

Downloading tmp-27892-1-SHASUMS256.txt-5.0.11
Error: getaddrinfo ENOTFOUND github-production-release-asset-2e65be.s3.amazonaws.com
C:\Users\timof\repos\temp\web-electron-rocket\node_modules\electron\install.js:49
  throw err
  ^

Error: getaddrinfo ENOTFOUND github-production-release-asset-2e65be.s3.amazonaws.com
    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:60:26)
npm WARN dagre-d3-renderer@0.5.8 requires a peer of d3@^4.13.0 but none is installed. You must install peer dependencies yourself.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\webpack-dev-server\node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\watchpack\node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\live-server\node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\@angular\compiler-cli\node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.1.1 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.1.1: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})

npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! electron@5.0.11 postinstall: `node install.js`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the electron@5.0.11 postinstall script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
```

1. Go to project folder and install dependencies:

```sh
npm install
```

2. Launch development server, and open `localhost:4200` in your browser:

```sh
npm start
```

# Project structure

```
dist/                        web app production build
docs/                        project docs and coding guides
e2e/                         end-to-end tests
src/                         project source code
|- app/                      app components
|  |- core/                  core module (singleton services and single-use components)
|  |- shared/                shared module  (common components, directives and pipes)
|  |- app.component.*        app root component (shell)
|  |- app.module.ts          app root module definition
|  |- app-routing.module.ts  app routes
|  +- ...                    additional modules and components
|- assets/                   app assets (images, fonts, sounds...)
|- environments/             values for various build environments
|- theme/                    app global scss variables and theme
|- translations/             translations files
|- index.html                html entry point
|- main.scss                 global style entry point
|- main.ts                   app entry point
|- polyfills.ts              polyfills needed by Angular
+- test.ts                   unit tests entry point
reports/                     test and coverage reports
proxy.conf.js                backend proxy configuration
```

# Main tasks

Task automation is based on [NPM scripts](https://docs.npmjs.com/misc/scripts).

| Task                                            | Description                                                                                                      |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `npm start`                                     | Run development server on `http://localhost:4200/`                                                               |
| `npm run serve:sw`                              | Run test server on `http://localhost:4200/` with service worker enabled                                          |
| `npm run build [-- --configuration=production]` | Lint code and build web app for production (with [AOT](https://angular.io/guide/aot-compiler)) in `dist/` folder |
| `npm run electron:build`                        | Build desktop app                                                                                                |
| `npm run electron:run`                          | Run app on electron                                                                                              |
| `npm run electron:package`                      | Package app for all supported platforms                                                                          |
| `npm test`                                      | Run unit tests via [Karma](https://karma-runner.github.io) in watch mode                                         |
| `npm run test:ci`                               | Lint code and run unit tests once for continuous integration                                                     |
| `npm run e2e`                                   | Run e2e tests using [Protractor](http://www.protractortest.org)                                                  |
| `npm run lint`                                  | Lint code                                                                                                        |
| `npm run translations:extract`                  | Extract strings from code and templates to `src/app/translations/template.json`                                  |
| `npm run docs`                                  | Display project documentation and coding guides                                                                  |
| `npm run compodoc`                              | Generates and display generates documentation from code                                                          |
| `npm run prettier`                              | Automatically format all `.ts`, `.js` & `.scss` files                                                            |

When building the application, you can specify the target configuration using the additional flag
`--configuration <name>` (do not forget to prepend `--` to pass arguments to npm scripts).

The default build configuration is `prod`.

## Development server

Run `npm start` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change
any of the source files.
You should not use `ng serve` directly, as it does not use the backend proxy configuration by default.

## Code scaffolding

Run `npm run generate -- component <name>` to generate a new component. You can also use
`npm run generate -- directive|pipe|service|class|module`.

If you have installed [angular-cli](https://github.com/angular/angular-cli) globally with `npm install -g @angular/cli`,
you can also use the command `ng generate` directly.

## Additional tools

Tasks are mostly based on the `angular-cli` tool. Use `ng help` to get more help or go check out the
[Angular-CLI README](https://github.com/angular/angular-cli).

## Code formatting

All `.ts`, `.js` & `.scss` files in this project are formatted automatically using [Prettier](https://prettier.io),
and enforced via the `test:ci` script.

A pre-commit git hook has been configured on this project to automatically format staged files, using
(pretty-quick)[https://github.com/azz/pretty-quick], so you don't have to care for it.

You can also force code formatting by running the command `npm run prettier`.

# What's in the box

The app template is based on [HTML5](http://whatwg.org/html), [TypeScript](http://www.typescriptlang.org) and
[Sass](http://sass-lang.com). The translation files use the common [JSON](http://www.json.org) format.

#### Tools

Development, build and quality processes are based on [angular-cli](https://github.com/angular/angular-cli) and
[NPM scripts](https://docs.npmjs.com/misc/scripts), which includes:

- Optimized build and bundling process with [Webpack](https://webpack.github.io)
- [Development server](https://webpack.github.io/docs/webpack-dev-server.html) with backend proxy and live reload
- Cross-browser CSS with [autoprefixer](https://github.com/postcss/autoprefixer) and
  [browserslist](https://github.com/ai/browserslist)
- Asset revisioning for [better cache management](https://webpack.github.io/docs/long-term-caching.html)
- Unit tests using [Jasmine](http://jasmine.github.io) and [Karma](https://karma-runner.github.io)
- End-to-end tests using [Protractor](https://github.com/angular/protractor)
- Static code analysis: [TSLint](https://github.com/palantir/tslint), [Codelyzer](https://github.com/mgechev/codelyzer),
  [Stylelint](http://stylelint.io) and [HTMLHint](http://htmlhint.com/)
- Local knowledgebase server using [Hads](https://github.com/sinedied/hads)
- Automatic Angular documentation generation using [Compodoc](https://compodoc.app)
- Automatic code formatting with [Prettier](https://prettier.io)

#### Libraries

- [Angular](https://angular.io)
- [Ionic](http://ionicframework.com)
- [Ionic Native](https://ionicframework.com/docs/native/)
- [RxJS](http://reactivex.io/rxjs)
- [ngx-translate](https://github.com/ngx-translate/core)
- [Lodash](https://lodash.com)
- [Moment.js](https://momentjs.com)

#### Coding guides

- [Angular](docs/coding-guides/angular.md)
- [TypeScript](docs/coding-guides/typescript.md)
- [Sass](docs/coding-guides/sass.md)
- [HTML](docs/coding-guides/html.md)
- [Unit tests](docs/coding-guides/unit-tests.md)
- [End-to-end tests](docs/coding-guides/e2e-tests.md)

#### Other documentation

- [I18n guide](docs/i18n.md)
- [Working behind a corporate proxy](docs/corporate-proxy.md)
- [Updating dependencies and tools](docs/updating.md)
- [Using a backend proxy for development](docs/backend-proxy.md)
- [Browser routing](docs/routing.md)
