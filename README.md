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
The input and control systems handle various inputs, timing, etc. The ultimate output of these systems is a set of parameter values each ranging from 0..1 (though occasionally slightly outside that range).

* input handling - routes MIDI and Leap Motion input to system parameters
* control UI - control panel UI for viewing and editing parameters
* audio I/O
* audio analysis and routing
* timing

## geometry systems
The geometry systems start with patterns of overlapping simple shapes, and go through several layers of transformation to ultimately generate a set of line segments (and a set of their endpoints), which then is passed to the renderer. The entire geometry system is 2D (it's actually 3D but everything's Z coordinate is always 0).
* generators
* pre-theshold distortion
* threshold
* post-theshold distortion

## rendering
The threshold connector lines use a basic wireframe material with a constant color, but with opacity that increases as the connectors get shorter.

The connection points use a point sprite material with a circular gradient (basically a circle with a fuzzy edge that's slightly darker in the middle).

There is a single camera that never moves, and no lighting since there aren't any phong or other such materials.

There is a renderer that renders because it enjoys rendering. It's quite happy.

## post-processing
After the renderer produces a stream of images, that stream is fed through a series of post-processing effects.
* color adjustment
* echo
* bloom
* stutter
* feedback!

### feedback
The feedback effect is a loop where a frame is mixed with the previous frame and the output of that is fed back into it as the next "previous frame". When the opacity of the previous/feedback frames is low, this results in small trails behind anything that moves, which fade the further they get away from the original line. When the opacity is much higher (almost 100%), it would normally just end up eventually making everything white. To deal with this, the feedback image is processed with an edging effect, which effectively makes portions of it transparent, allowing it to mix without overwhelming the resulting image.


