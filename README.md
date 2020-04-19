# Docdash for Thingy Pool

[![license](https://img.shields.io/npm/l/docdash.svg)](LICENSE.md)

A clean, responsive documentation template theme for JSDoc 3.

## Example

See https://iampatbrown.github.io/thingy-pool/ for a sample demo. :rocket:

## Changes

The main changes:

- Changed colors in css. Not all of them, only the ones that I needed for Thingy Pool
- Removed Home navigation link creation from publish.js and added it to layout.tmpl so it could be above the search box
- Home navigation title can be set in jsdoc.json with `{ "docdash": { "title": "Thingy Pool" } }`
- Removed nested tables for subParams - instead hide the parent and display parent.subParam in same table
- Removed attributes column from from params table - instead append _<sub>opt</sub>_ to indicate optional params. I didn't add anything to indicate nullable or variable params because I wasn't using them.
- Fixed some styling issues with the code blocks to make it work better on my phone
- Made tables scroll instead of stretch the screen size.

This hasn't really been tested, so I'm not sure if the changes break stuff that I'm not using. Eg. I might have changed some colors that look strange somewhere or the subParam change was a bad idea. If anyone ends up using this and wants something fixed, just let me know. Have fun :)

![screenshot-web-01](/screenshots/screenshot-web-01.png?raw=true)

![screenshot-web-02](/screenshots/screenshot-web-02.png?raw=true)

![screenshot-mob-01](/screenshots/screenshot-mob-01.png?raw=true) ![screenshot-mob-02](/screenshots/screenshot-mob-02.png?raw=true) ![screenshot-mob-03](/screenshots/screenshot-mob-03.png?raw=true)

## Install

```bash
$ npm install iampatbrown/docdash
```

## Usage

Clone repository to your designated `jsdoc` template directory, then:

```bash
$ jsdoc entry-file.js -t path/to/docdash
```

## Usage (npm)

In your projects `package.json` file add a new script:

```json
"script": {
  "generate-docs": "node_modules/.bin/jsdoc -c jsdoc.json"
}
```

In your `jsdoc.json` file, add a template option.

```json
"opts": {
  "template": "node_modules/docdash"
}
```

## Sample `jsdoc.json`

See the config file for the [fixtures](fixtures/fixtures.conf.json) or the sample below.

```json
{
  "tags": {
    "allowUnknownTags": false
  },
  "source": {
    "include": "../js",
    "includePattern": "\\.js$",
    "excludePattern": "(node_modules/|docs)"
  },
  "plugins": ["plugins/markdown"],
  "opts": {
    "template": "assets/template/docdash/",
    "encoding": "utf8",
    "destination": "docs/",
    "recurse": true,
    "verbose": true
  },
  "templates": {
    "cleverLinks": false,
    "monospaceLinks": false
  }
}
```

## Options

Docdash supports the following options:

```json5
{
  docdash: {
    title: '' // Used to customize the Home navigation link. Defaults to 'Home'
    static: [false | true], // Display the static members inside the navbar
    sort: [false | true], // Sort the methods in the navbar
    sectionOrder: [
      // Order the main section in the navbar (default order shown here)
      'Classes',
      'Modules',
      'Externals',
      'Events',
      'Namespaces',
      'Mixins',
      'Tutorials',
      'Interfaces',
    ],
    disqus: '', // Shortname for your disqus (subdomain during site creation)
    openGraph: {
      // Open Graph options (mostly for Facebook and other sites to easily extract meta information)
      title: '', // Title of the website
      type: 'website', // Type of the website
      image: '', // Main image/logo
      site_name: '', // Site name
      url: '', // Main canonical URL for the main page of the site
    },
    meta: {
      // Meta information options (mostly for search engines that have not indexed your site yet)
      title: '', // Also will be used as postfix to actualy page title, prefixed with object/document name
      description: '', // Description of overal contents of your website
      keyword: '', // Keywords for search engines
    },
    search: [false | true], // Display seach box above navigation which allows to search/filter navigation items
    collapse: [false | true], // Collapse navigation by default except current object's navigation of the current page
    wrap: [false | true], // Wrap long navigation names instead of trimming them
    typedefs: [false | true], // Include typedefs in menu
    navLevel: [integer], // depth level to show in navbar, starting at 0 (false or -1 to disable)
    private: [false | true], // set to false to not show @private in navbar
    removeQuotes: [none | all | trim], // Remove single and double quotes, trim removes only surrounding ones
    scripts: [], // Array of external (or relative local copied using templates.default.staticFiles.include) js or css files to inject into HTML,
    menu: {
      // Adding additional menu items after Home
      'Project Website': {
        // Menu item name
        href: 'https://myproject.com', //the rest of HTML properties to add to manu item
        target: '_blank',
        class: 'menu-item',
        id: 'website_link',
      },
      Forum: {
        href: 'https://myproject.com.forum',
        target: '_blank',
        class: 'menu-item',
        id: 'forum_link',
      },
    },
    scopeInOutputPath: [false | true], // Add scope from package file (if present) to the output path, true by default.
    nameInOutputPath: [false | true], // Add name from package file to the output path, true by default.
    versionInOutputPath: [false | true], // Add package version to the output path, true by default.
  },
}
```

Place them anywhere inside your `jsdoc.json` file.

## Original Docdash Contributors

[![0](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/0)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/0)
[![1](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/1)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/1)
[![2](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/2)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/2)
[![3](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/3)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/3)
[![4](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/4)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/4)
[![5](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/5)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/5)
[![6](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/6)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/6)
[![7](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/images/7)](https://sourcerer.io/fame/ar2rsawseen/clenemt/docdash/links/7)

## Thanks

Thanks to [docdash](https://github.com/clenemt/docdash), [lodash](https://lodash.com) and [minami](https://github.com/nijikokun/minami).

## License

Licensed under the Apache License, version 2.0. (see [Apache-2.0](LICENSE.md)).
