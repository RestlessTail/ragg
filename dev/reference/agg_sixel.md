# Draw to the standard output using Sixel graphics

This function creates a graphics device that renders plots to the
standard output using the Sixel bitmap graphics protocol. The device
outputs Sixel data upon termination with
[`dev.off()`](https://rdrr.io/r/grDevices/dev.html). This requires a
terminal emulator that supports Sixel graphics.

## Usage

``` r
agg_sixel(
  width = 480,
  height = 480,
  units = "px",
  pointsize = 12,
  background = "white",
  res = 72,
  scaling = 1,
  snap_rect = TRUE,
  bg
)
```

## Arguments

- width, height:

  The dimensions of the device

- units:

  The unit `width` and `height` is measured in, in either pixels
  (`'px'`), inches (`'in'`), millimeters (`'mm'`), or centimeter
  (`'cm'`).

- pointsize:

  The default pointsize of the device in pt. This will in general not
  have any effect on grid graphics (including ggplot2) as text size is
  always set explicitly there.

- background:

  The background colour of the device

- res:

  The resolution of the device. This setting will govern how device
  dimensions given in inches, centimeters, or millimeters will be
  converted to pixels. Further, it will be used to scale text sizes and
  linewidths

- scaling:

  A scaling factor to apply to the rendered line width and text size.
  Useful for getting the right dimensions at the resolution that you
  need. If e.g. you need to render a plot at 4000x3000 pixels for it to
  fit into a layout, but you find that the result appears to small, you
  can increase the `scaling` argument to make everything appear bigger
  at the same resolution.

- snap_rect:

  Should axis-aligned rectangles drawn with only fill snap to the pixel
  grid. This will prevent anti-aliasing artifacts when two rectangles
  are touching at their border.

- bg:

  Same as `background` for compatibility with old graphic device APIs

## Examples

``` r
if (FALSE) { # \dontrun{
agg_sixel()
plot(sin, -pi, 2*pi)
dev.off()
} # }
```
