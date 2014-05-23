order
=====

order is a visualization system based on structured data processing, without randomization or noise.

[output videos](https://vimeo.com/album/2736128)

see also http://t3kt.net/projects/order

![example output](http://farm4.staticflickr.com/3787/13365828224_95d9d7f556_o.jpg "Example Output")

## system structure
Order is composed of several subsystems:
* input and control systems
* geometry systems
* rendering
* post-processing

## input and control systems
* input handling - routes MIDI and Leap Motion input to system parameters
* control UI - control panel UI for viewing and editing parameters
* audio I/O
* audio analysis and routing
* timing

## geometry systems
* generators
* pre-theshold distortion
* threshold
* post-theshold distortion

also other things...

## rendering
The threshold connector lines use a basic wireframe material with a constant color, but with opacity that increases as the connectors get shorter.
The connection points use a point sprite material with a circular gradient (basically a circle with a fuzzy edge that's slightly darker in the middle).
There is a single camera that never moves.
There is no lighting since there aren't any phong or other such materials.
There is a renderer that renders because it enjoys rendering. It's quite happy.

## post-processing

