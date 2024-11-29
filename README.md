# showing-terminal-output

Noodling around with choices for displaying terminal output on GitHub.

So let's say we have three examples of Linux terminal output that makes use of
ANSI color sequences and emoji. How to best to showcase these on GitHub, from
a Markdown document?

The obvious choices seem to be:

- PNG image file
- SVG document
- Link out to HTML

Which ends up looking best for you?

## PNG image file

A screenshot to an image is going to be great for exactly replicating how
these things look for me on my screen, but I have concern that my display is
going to be of a very different resolution to the reader's. If they need to
zoom in to see it better it's not going to scale well.

My other major concern is that it's not accessible to those using screen
readers. I mean I _can_ include a gigantic alt text but that's quite
difficult.

Just adding these as `<img src="/ptrcheck-typical.png" />` seems to result in
an embedded image with the width of the browser.

### Typical run

<img src="/ptrcheck-typical.png" />

### Verbose run

<img src="/ptrcheck-verbose.png" />

### Another verbose run

<img src="/ptrcheck-verbose2.png" />

## SVG document

It's possible to do a screenshot to SVG that directly uses the actual text
from the terminal so in theory it's friendly to copy and paste and screen
readers. In practice I have no idea if that is the case. It should also zoom
in and out nicely.

Beyond the basics of monospace font rendering I'm unsure if there will be
problems with missing font glyphs for emojis. The examples on this page use:

- :fire: `:fire:`
- :sparkles: `:sparkles:`
- :trophy: `:trophy:`

These SVGs were generated with
[freeze](https://github.com/charmbracelet/freeze). My immediate observation is
that since I just had to set `font-family: monospace` in there then this is
very unlikely to show up exactly like screenshots of my terminal (where I use
CommitMono). It's possible to tell `freeze` to embed a font into the SVG but
that will make the SVG literally megabytes in size. I'm not sure these
examples really need it.

All the SVGs seem to start off more zoomes out that my PNG screenshots, but
it's actually pleasing that they look more uniform. If you do "open image in
new tab/window" in your browser then you can zoom them in and out and they
retain the crispness. For me it is also possible then to copy/paste the actual
text.

So my experience with this is quite positive. I think I like it better than
the PNGs.

### Typical run

<img src="/ptrcheck-typical.svg" />

### Verbose run

<img src="/ptrcheck-verbose.svg" />

### Another verbose run

<img src="/ptrcheck-verbose2.svg" />

## Link out to HTML

HTML is problematic here as GitHub is quite limited in what it allows to be
embedded in Markdown, and for good reason: allowing all manner of styling
would lead to GitHub looking like Geocities. It may be possible to link out to
a HTML file hosted in the repository, or to a GitHub pages site, but I'm most
interested in this being workable from the repository view of GitHub.

I'm not going to pursue this option for now.
