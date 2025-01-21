# CASA

Computer-assisted sperm analyzer

## Introduction

CASA is a sperm analysis program that processes videos of swimming sperm to
calculate swimming velocity and other measures. CASA is a plugin to ImageJ and
is written in Java. This repository, CASA2, contains updates to improve CASA's
ability to discriminate between true sperm and debris, and to make CASA's
output better suited to further computer analysis.

## Original version

This is a fork of the original CASA which is aviailable here:

[https://imagej.net/ij/plugins/casa.html](https://imagej.net/ij/plugins/casa.html)

Documentation:

[https://imagej.net/ij/plugins/docs/CASAinstructions.pdf](https://imagej.net/ij/plugins/docs/CASAinstructions.pdf)

## Installation

## Changes

- Added minimum net distance traveled in pixels
- Added minimum net velocity in pixels per frame
- Added track ID numbers when printing xy co-ordinates

## Documentation

### Minimum net distance traveled (pixels)

Option "h" in the CASA options menu. Default zero pixels. If this option is
set, CASA will ignore any sperm tracks whose start and end points are closer
than this minimum by euclidean distance.

### Minimum net distance traveled (pixels per frame)

Option "i" in the CASA options menu. Default zero pixels per frame. If this
option is set, CASA calculates the euclidean distance between the start and end
of each track, then divides this distance by the number of frames for which the 
track was followed. If this number is below the minimum, the track is ignored.

### Print track ID number when printing xy co-ordinates for all tracked sperm

Option "v" in the CASA options menu. Default 0. If this is set to 1, CASA will
assign a serial number to each track sperm. If the option to print raw XY
coordinates (option "u") is selected, option "v" adds an extra field at the
beginning of each line containing this serial number.
This number allows the raw sperm tracks to be output and then analyzed by another
program post-hoc. Option "v" changes the XY coordinate output from this format:

```
 X_raw Y_raw X_VAP, Y_VAP, X_first_VAP, Y_first_VAP
```

to this:

```
 track_ID X_raw Y_raw X_VAP, Y_VAP, X_first_VAP, Y_first_VAP
```

Note the leading space in all output.
