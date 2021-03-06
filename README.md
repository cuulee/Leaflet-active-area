Leaflet-active-area [![Build Status](https://travis-ci.org/Mappy/Leaflet-active-area.svg?branch=master)](https://travis-ci.org/Mappy/Leaflet-active-area)
===============

That [Leaflet](http://leafletjs.com) plugin allows you to use a DIV as the active area.
All positionning methods (setView, fitBounds, setZoom) will be applyed on this DIV instead of the all map.
A typical use case is to set a map as background (like that [example](http://mappy.github.io/Leaflet-active-area/examples/index.html)) and center it on the top of the screen for example.
Defining media queries on that DIV make it easy to adapt the active area according client resolution.

Supports leaflet 1.0.1

## Demo

Try the [example page](http://mappy.github.io/Leaflet-active-area/examples/index.html) !

## Versions

The "master" branch supports the last stable version of leaflet (0.7.7)

## Installation

(For leaflet 0.7.7)
npm install --save-dev leaflet-active-area@0.1.1

The latest version (1.0.1) of leaflet-active-area was meant to support leaflet-1.x but has not been updated since leaflet 1.0-beta1. We will work on it as soon as a stable version of leaflet is released.

## Usage

Include the javascript file :

    <script src="L.activearea.js"></script>

Add a CSS class (".activeArea" in that example) with absolute position

    .activeArea { position: absolute; top: 50px; left: 50px; right: 50px; height: 200px; }

And instanciate your map like that :

    var map = new L.Map(document.createElement('div')).setActiveArea('activeArea');

You can also give an object with HTML style properties:

    var map = new L.Map(document.createElement('div')).setActiveArea({
        position: 'absolute',
        top: '50px',
        left: '50px',
        right: '50px',
        height: '200px'
    });

Then, the map will center itself in the center of that DIV when calling setView, setZoom, fitBounds, etc.

If your need to re-center the map automatically, pass 'true' as second argument :

    map.setActiveArea('activeArea', true, true);

Pass true as 3rd argument to animate the pan (default = false)


## Contribute

To run tests, you’ll need to install npm and bower libraries :

`npm install && bower install`

then :

`npm test`

## Contributors

- Samuel Piquet ([sa3m](https://github.com/sa3m), Mappy), creator of this plugin
- Grégory Paul ([paulgreg](https://github.com/paulgreg), Mappy)
- Michael Cellier ([mcellier](https://github.com/mcellier), Mappy)
- Frederic Le Menach ([flemenach](https://github.com/flemenach), Mappy)
- Vivien Ripoche ([vripoche](https://github.com/vripoche), Mappy)
- Eric Brelsford ([ebrelsford](https://github.com/ebrelsford))
- Dag Jomar Mersland ([dagjomar](https://github.com/dagjomar))
- Miroslav Petrik ([11th](https://github.com/11th))

## License

This code is provided under the Apache 2.0 license.
