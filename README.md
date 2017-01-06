# Simple Ruler

![CKEditor logo](docs/img/ckeditor-logo.svg)
![CKEditor logo](docs/img/ruler-logo.svg)

## Description

A ruler plugin for [CKEditor](http://ckeditor.com) displays the horizontal dimension of the page. You can modify it on the ruler using a mouse.

## Demo
You can try it on the [demo page](https://lovata.github.io/ckeditor-ruler/).


## Getting Started

### Manual

Add the Simple Ruller plugin to ckeditor. The easiest way to do this is by adding the following line to CKEditor's `config.js`:

```js
config.extraPlugins = 'ruler';
```
### NPM

Install `ckeditor-ruler` as a development dependency:

```bash
npm install ckeditor-ruler --save-dev
```

Init CKEditor with the plugin:

```js
window.onload = function() {
    CKEDITOR.plugins.addExternal('ruler', '/node_modules/ckeditor-ruler/');
    CKEDITOR.config.extraPlugins = 'ruler';
    CKEDITOR.replace('editor');
};

```
## Options
```javascript
CKEDITOR.config.ruler = {
    values: 21,     // segment number of the ruler
    step: 0.25,     // accuracy of sliders
    sliders: {
        left: 2,    // left slider value
        right: 19   // right slider value (21-19 = 2)
    },
    padding: {
        top: 20,    // top 'canvas' padding (px)
        bottom: 20  // bottom 'canvas' padding (px)
    }
};
```

## API
Plugin dispatches `updateRuler` event as soon as any of slider's values have been changed:

```js
editor.fire('updateRuler', { left: Number, right: Number });
```

Plugin is subscribed to `setRulerPadding` editor's event, so you can fire the event to change ruler's values programmatically:

```js
editor.fire('setRulerPadding', { left: Number, right: Number });
```

## Browser compatibility
Originally this plugin was build for an [Electron](https://github.com/electron/electron) library, therefore it wasn't tested in other browsers.

## License
![LOVATA Group logo](docs/img/lovata-logo.svg)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![GNU GPL v3 logo](docs/img/gplv3-logo.svg)

© 2016, [LOVATA Group, LLC](http://lovata.com) under GNU GPL v3.

Develped by [Aleksandra Shinkevich](https://github.com/neesoglasnaja).
