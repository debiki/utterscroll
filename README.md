Utterscroll
===========

Enables dragscroll on your website. It automatically detects when you
want to select text, rather than scroll.

Please find a [DEMO, here][demo], together with more information on
Utterscroll. 

You could ask questions or make suggestions by clicking *Leave a
comment* at the bottom of that page (i.e. the demo page). (Or via
GitHub.)


Instructions
---------

Requires jQuery, tested with jQuery 1.7.2.

Use like so: (for example)

    <script src='jquery-scrollable.js'></script>
    <script src='debiki-utterscroll.js'></script>

    if (!Modernizr.touch)  // if not a smartphone
      debiki.Utterscroll.enable({
          scrollstoppers: '.CodeMirror, .ui-resizable-handle' });

Utterscroll is disabled inside the `scrollstoppers`. (It automatically
understands to disable itself when you click buttons or select text,
so you probably don't need to configure many special scrollstoppers.)

Please find in `utterscroll-example.html` a complete example HTML file, live here:
http://rawgithub.com/debiki/utterscroll/master/utterscroll-example.html.
Please have a look in that file — there are some things to think about:
you currently need to load Utterscroll at the bottom of the HTML page,
and you cannot use Utterscroll before the jQuery onload event has happened.


Nested Scrollbars Issue with Firefox
---------

Utterscroll works in nested scrollbars, however, if the wrapping element
doesn't have `position: relative` or `absolute`, the nested scrollbars
seems to be broken in Firefox. Have a look at the demo (link above, to
utterscroll-example.html) — in the demo, I've set `position: relative`
on the wrapping element, so it should work in Firefox.


Details
---------

Utterscroll scrolls the closest scrollable element, or the window.
However, scrolling anything but the window, depends on a jQuery
selector, ':scrollable', being available. Otherwise, the window is
always scrolled.  So you should also include the file
`jquery.scrollable.js` on your web page (it defines the ':scrollable'
selector).  That file is an excerpt from
[jquery-scrollintoview](https://github.com/litera/jquery-scrollintoview/blob/master/jquery.scrollintoview.js)
by Robert Koritnik.


As of 2012-05-23, tested with jQuery 1.7.2 and recent versions of
Chrome, FF, IE and Opera.

As of 2012-02-29, tested with jQuery 1.6.4 and recent versions of
Google Chrome, Firefox and Opera, and IE 6, 7, 8 and 9.  (Scrolling
the window has been tested; scrolling other elems has not been very
thoroughly tested.)


License and Copyright
----------

Copyright (c) 2012 Kaj Magnus Lindberg

Licensed under the GNU Lesser General Public License version 2.1, or
(at your option) any later version.  See the top of debiki-utterscroll.js
and lgpl-2.1.txt and lgpl-3.0.txt and http://www.gnu.org/licenses/.

[demo]: http://www.debiki.com/dev/-31nc3-utterscroll

