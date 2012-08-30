# jQuery Columnize
# Column layout for jQuery

## Description

Columnize creates a newspaper-like column layout. The
original HTML code only needs small adaptions. In most
cases, it is not necessary to adapt the HTML code at all.

## Documentation

Using the plugin is easy:

	$("#text").columnize();

sets the contents of the DOM node with the ID `text` in a
two-column layout with balanced column lengths.

## Options

The plugin recognizes several options which are denoted in
curly brackets.

- balance: `true` if the column lengths should be
      balanced. `false` if the columns should grow to the
      height of the containing element. Default: `true`
- cache: The original contents of the container are
      cached. Set this to `false` to disable caching.
      Default: `true`
- column: The CSS class which should be applied to
      columns. Default: `column`
- columns: The desired number of columns if balance
      mode is on. Default: `2`
- continued: The CSS class which should be applied to
      DOM nodes which are continued in the next column.
      Default: `'continued'`
- dontsplit: A comma-separated list of HTML element
      names which should not be split over columns.
      Default: `''` (an empty string)
- height: The maximum height of the columns. This is
      usually read from the max-height CSS value of the
      container, but can be set here explicitely.
      Default: none.
- minHeight: The minimal height of the columns.
      Default: none.

## Tips

If balance mode is off, the element to which the column
layout should be applied has to define a maximum height
via the CSS property `max-height`. The columns will then
grow to at most this height.

If balance mode is on, the maximum height is taken into
account, too. If balancing the column lengths would exceed
the maximum height the plugin automatically disables balance
mode. In this case, the plugin creates more columns than
specified in the columns option.

The column width is derived from the CSS properties of the
columns. You can control the width using the CSS class
specified in the columns option.. Typical properties for a
column are the following:

	float: left;
	width: 200px;
	margin-right: 1em;

For a beautiful layout it is recommended to use the CSS
property `line-height`. By setting the line height explicitly
and calculate all vertical distances as multiples of the line
height you ensure that all baselines are aligned to the same
grid.

If you want to prevent nodes from being split at a column
break, add the CSS class `dontsplit` to them, or add the
element name to the `dontsplit` option (e.g.
`{dontsplit: "h1,p,li"}`).

## Examples

- `$("#text").columnize({columns: 3});`
      Three columns with balanced column lengths.
- `$("#text").columnize({columns: 3, balanced: false});`
      Three columns with balanced column lengths if the
      column lengths do not exceed the maximum height of
      the containing element. In this case, the plugin
      abandons the limitation to three columns and creates
      as many columns as needed for the text.
- `$("#text").columnize({balanced: false});`
      Columns grow until the maximum height of the containing
      element. The number of columns is determined by the
      amount of text.

## License

This plugin is distributed under the terms of the
GNU Lesser General Public license. The license can be
obtained from [http://www.gnu.org/licenses/lgpl.html](http://www.gnu.org/licenses/lgpl.html).

Copyright &copy; 2008–2012 [Systemantics GmbH](http://www.systemantics.net/)

## Changelog

### v0.12:
 
- added optional callback for height setting
- added optional callback for columnClass setting
- renamed column setting to columnClass
- added support for 0 columns (removes columns)
- added unColumnize() as alias to remove columns

### v0.11

- fixed two bugs with IE8
