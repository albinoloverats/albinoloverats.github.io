---
layout: page
title: hide
nav: true
permalink: /projects/hide
---

hide is an steganographic image tool. It is very similar to [encrypt][]-simple and (eventually) cross-platform. It has, in fact, been designed and written to work alongside encrypt to provide a way to hide your encrypted data.

Your (encrypted) data is hidden in the least significant pixel values of the image of your choice. We prototyped with various bytes per pixel values and have come to the conclusion that storing one byte per pixel provided the best trade-off of data capacity versus image quality; 3 bits per red and blue channels, 2 bits per green.

It's worth mentioning here (as well as in the README) that hide neither compresses nor encrypts data, for that we recommend [encrypt][] ;-) It's also worth pointing out that at the moment only three lossless image formats are supported: [PNG][], [TIFF][], and [WebP][], and that the outputed image file size _will_ differ from the original (it might even be smaller), especially if the original was a lossy Webp image.

For now there is only a CLI and hide has only been compiled and tested on [Arch Linux][], but a GUI has been created and is just in need of hooking everything up. Hopefully once the GUI is working we'll be ready for the first release (which will likely be GNU/Linux only; Windows, OS X, and Android will take a little longer). The intented roadmap looks something like this:

 Available for users of GNU/Linux systems _(this is where we're at now)_
* GNU/Linux GUI release
* Provide a Windows binary
* Provide an OS X binary
* Start work on an Android app

At the moment, hide uses shared object libraries to provide the reading and writing of the images, and obviously this isn't very cross-platform so might change.

[encrypt]: /projects/encrypt
[Arch Linux]: http://www.archlinux.org

[PNG]: http://www.libpng.org/pub/png/
[TIFF]: http://partners.adobe.com/public/developer/tiff/index.html
[WebP]: https://developers.google.com/speed/webp/?csw=1

*[PNG]: Portable Network Graphics
*[TIFF]: Tagged Image File Format
*[CLI]: Command Line Interface
*[GUI]: Graphical User Interface
