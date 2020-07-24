# dmn-to-image

Based on nikku's [BPMN to image](https://github.com/bpmn-io/bpmn-to-image)

Convert [DMN diagrams](https://www.omg.org/spec/DMN) to PDF documents, SVG or PNG files.


## Usage

This package exposes the `dmn-to-image` command line utility that allows you to convert DMN diagrams to PNG and PDF documents:

```bash
$ dmn-to-image --help

  Convert a DMN diagrams to PDF or PNG images

  Usage

    $ dmn-to-image <diagramFile>:<outputConfig> ...

  Options

    diagramFile                    Path to DMN diagram
    outputConfig                   List of extension or output file paths

    --min-dimensions=<dimensions>  Minimum size in pixels (<width>x<height>)

    --title=<title>                Add explicit <title> to exported image
    --no-title                     Don't display title on exported image

    --no-footer                    Strip title and logo from image

    --scale                        Scale factor for images (1)

  Examples

    # export to diagram.png
    $ dmn-to-image diagram.dmn:diagram.png

    # export diagram.png, diagram.svg and /tmp/diagram.pdf
    $ dmn-to-image diagram.dmn:diagram.png,diagram.svg,/tmp/diagram.pdf

    # export with minimum size of 500x300 pixels
    $ dmn-to-image --min-dimensions=500x300 diagram.dmn:png
```


## Embedding

You may embed [dmn-to-image](https://github.com/pulilab/dmn-to-image) and use it as parts of your application:

```javascript
const {
  convertAll
} = require('dmn-to-image');

await convertAll([
  {
    input: 'diagram.dmn',
    outputs: [
      'diagram.pdf',
      'diagram.png',
      'diagram.svg'
    ]
  }
]);
```

This renders the DMN diagram using [dmn-js](https://github.com/pulilab/dmn-to-image) and exports it to the specified output files using [Puppeteer](https://github.com/GoogleChrome/puppeteer).


## Install

```bash
npm install dmn-to-image
```


## License

MIT