# TMX C Loader

---

## About

A portable C library to load [tiled](http://mapeditor.org) maps in your games.

## Dependencies

This project depends on [Zlib](http://zlib.net/), [Jansson](http://www.digip.org/jansson/) and [LibXml2](http://xmlsoft.org).

## Compiling

This project uses [cmake](http://cmake.org) as a *build system* builder.
You can either use cmake, ccmake or cmake-gui.

You can disable XML support by setting `WANT_XML` to *off*, the same way with `WANT_JSON` you can disable JSON support.

### Example :

    mkdir build
    cd build
    cmake ..
    make && make install

## Usage

```c
#include <tmx.h>

int main(void) {
  tmx_map map = tmx_load("path/map.tmx");
  if (!map) {
    tmx_perror("tmx_load");
    return 1;
  }
  /* ... */
  tmx_free(map);
  return 0;
}
```

### Help

See the [Wiki](https://github.com/baylej/tmx/wiki/).
