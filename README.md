deck.lazyload.js
================

Load deck.js slides lazily using ajax.

## Requirements

[deck.js](https://github.com/imakewebthings/deck.js)

[deck.events.js](https://github.com/mikeharris100/deck.events.js)

## Example:

Place the repository on a webserver and load the index.html page.

Due to cross-origin restrictions, most browsers will not let you
run ajax from file:// urls so it needs to be on a webserver.
(even calling `python -m SimpleHTTPServer` from the example directory
in a terminal window should work)

## How to Use:

Instead of putting content in the slide itself, mark it with the class
`lazyload`. When a marked slide is "next", "current", or "previous" in
the deck, its content will be loaded based on the ID attribute of the
slide.

If you only want to load a subset of the content in a slide, the
selection can be filtered using a jQuery selector stored in a
configurable attribute in the slide (`data-filter` by default)

## Features:

* Slides aren't loaded until they are needed.
* Path is configurable, so you can keep slides in a subdirectory.
* Configurable filename prefix and suffix.
* Content is filterable using a jQuery selector.
* Deck is reinitialized after loading, so you can have subslides
  inside the slides that are loaded.

## Todo:

* Create a mechanism to let extensions know that the content has
  been loaded, if needed (`deck.load` event?).
* Don't clobber existing elements in a slide when loading (eg. in
  case an extension adds its own elements to a slide).
* Find a smarter selective initialization method so that we don't
  re-initialize already initialized slides.