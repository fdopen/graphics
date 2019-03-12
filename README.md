Graphics
========

The graphics library provides a set of portable drawing
primitives. Drawing takes place in a separate window that is created
when Graphics.open_graph is called. It used to be distributed with
OCaml up to OCaml 4.08.

On Unix
-------

On Unix graphics uses the X11 windows system.

Here are the graphics mode specifications supported by
`Graphics.open_graph` on the X11 implementation of this library: the
argument to `Graphics.open_graph` has the format `"display-name
geometry"`, where display-name is the name of the X-windows display to
connect to, and geometry is a standard X-windows geometry
specification. The two components are separated by a space. Either can
be omitted, or both. Examples:

- `Graphics.open_graph "foo:0"`: connects to the display foo:0 and
  creates a window with the default geometry
- `Graphics.open_graph "foo:0 300x100+50-0"` connects to the display
  foo:0 and creates a window 300 pixels wide by 100 pixels tall, at
  location (50,0)
- `Graphics.open_graph " 300x100+50-0"` connects to the default
  display and creates a window 300 pixels wide by 100 pixels tall, at
  location (50,0)
- `Graphics.open_graph ""` connects to the default display and creates
  a window with the default geometry.

On Windows
----------

On Windows graphics uses the native Win32 API.
