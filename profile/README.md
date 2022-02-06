# γ Photon Framework

Use modernized retro tech at the speed of light towards the future.

Photon is a web development platform that takes simplicity over complexity. Great for beginners and experts.

This framework is not meant to be used for complex web applications, only for simple pages. The purpose is to improve the general performance and simplify the deployment.

## NPM

#### Runtime

[![NPM version](https://img.shields.io/npm/v/photon-re.svg)](https://npmjs.org/package/photon-re "View this project on NPM")
[![NPM downloads](https://img.shields.io/npm/dm/photon-re.svg)](https://npmjs.org/package/photon-re "View this project on NPM")
![Types included](https://badgen.net/npm/types/tslib)

#### CLI (Compiler)

[![NPM version](https://img.shields.io/npm/v/photon-cli.svg)](https://npmjs.org/package/photon-cli "View this project on NPM")
[![NPM downloads](https://img.shields.io/npm/dm/photon-cli.svg)](https://npmjs.org/package/photon-cli "View this project on NPM")

## Use Cases

- Portfolios
- Info pages
- Online documentations
- Blogs
- ...

## Keep it simple

You don't need JavaScript to get Photon working.

## Speed and performance

Most frameworks add too much overhead to simple websites.
Photon does the opposite, it is designed for simple websites.

## It stays in the Browser

The complete code is executed client-side in the browser.
Basic features are available without client-side JavaScript.

## SEO

- Prerendered pages at compile time (with subpages and components)
- Automaticly generated robots.txt and sitemap.xml (if nothing specified)

## Quick Start

### Use npm or yarn to import the library.

```bash
yarn add photon-re
yarn add -D photon-cli
```

### Create your index.html boilerplate (nothing special here)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Photon</title>
  </head>
  <body></body>
</html>
```

### Add a router to the body

```html
<main
  id="root"
  photon-router
  data-content="/content"
  data-default="/en/home"
  data-fallback="/404"
></main>
```

- `photon-router` activates the router functionality for this element (only one allowed!).
- `data-content` is the location of the subpages that should get injected into the router.
- `data-default` is loaded if no path (for a subpage) is given in the url.
- `data-fallback` is loaded if the the subpage specified by the url was not found. Server Setup is needed.

### Add anchors for navigation to the body

```html
<nav>
  <a data-route="info">Info</a>
  <a data-route="portfolio">Portfolio</a>
  <a data-route="links">Links</a>
</nav>
```

- `data-route` specifies the name of the subpage that should be loaded on click.

### Combined

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Photon</title>
  </head>
  <body>
    <nav>
      <a data-route="info">Info</a>
      <a data-route="portfolio">Portfolio</a>
      <a data-route="links">Links</a>
    </nav>
    <main
      id="root"
      photon-router
      data-content="/content"
      data-default="/en/home"
      data-fallback="/404"
    ></main>
  </body>
</html>
```

### For special functionalities import from the runtime

```typescript
addRoutingEventListener(
  "routed",
  (ev) => {
    console.debug(ev.detail.route); // print out the new route after a routing event
  },
  {
    passive: true,
  }
);
```
