Design Notes
============

These are high level design notes for the Water Tricorder project, an easy-to-use water quality instrument. 

Why
---

Existing water quality devices either measure only a subset of possible toxins, are designed for industrial use and are too expensive and unusable by laypersons, or require consumables such as test strips that render testing impossible once if the supply runs out.

This device is intended for use by outdoor enthusiasts, people in rural communities, in disaster zones where water quality is unknown, and many other places. A simple yes/no to water potability can serve immediate needs, and detailed data output can help with adhoc water treatment planning.

Design Team
-----------

TBD

Advisors
--------

TBD

Design Principles
-----------------

**Opensource** - a public project for all. 

**Simplicity** - simple enough that all components can be taken apart, examined, understood, and
repaired by people with high school educations.

**Affordability** - it shouldn't cost more than $100.

**Usability** - it should be simple enough that children and seniors can reliably use the instrument.

**Responsiveness** - it should not take more than 10 seconds to provide a reading.

**Reliability** - it has one job: to answer the question, "can I drink this water?" If the reliability 
of the system degrades over time, then some reliable warning sensor should be built-in and maintenance 
should be easy for anyone with basic literacy.

**Attractiveness** - it should look cool.

Primary Systems
---------------

**Optical Sensor** - a simple low cost digital microscope to capture optical data of microorganisms from water samples.

**Spectrometer** - a small and simple spectrometer that captures inorganic data.

**CPU** - a small system for for processing sensor data and displaying user interface output.

**Software** - machine learning systems that can classify sensor inputs and classify the type and density of toxic
components in the water and answer the simple potability yes/no question.

**Power** - it should be as low power as possible, and operate only briefly to take a reading, display results, and transfer data.

**Enclosure** - self contained, waterproof, minimal parts, small, accessible, repairable with simple tools.

Background
----------

* [Conventional water quality measurement approaches](https://publiclab.org/notes/anngneal/12-08-2017/7-ways-to-measure-monitor-and-evaluate-water-quality)

Optical Sensor
--------------

The optical sensor should be a portable microscope of just enough quality that
it can feed a machine learning system sufficiently good images for the ML to
recognize bacteriological pathogens (are these the right terms?). Low power
microscopes can even use a cellphone camera and a fitted lens, while middle 
or high power would require more sophisticated optics. Both system may require
backlighting. Should have a low-maintenance lens, meaning that it should 
not require frequent cleaning and the cleaning process should be easy and 
simple. Ideally the ML system should compensate well for lens damage.

Since most bacteria range in size from about 0.2 to 2 micrometers (µm), a lens 
of 1000x or more would be required. The use of some additional technique such as
[Darkfield Microscopy](https://en.wikipedia.org/wiki/Dark-field_microscopy) 
would enhance the visibility of bacteria and, in combination with machine
learning, may allow for good operation with reduced magnification.

Spectrometer
------------

A spectrometer design that could follow [Public Lab's DIY spectrometer](https://publiclab.org/wiki/spectrometry) design,
perhaps miniaturized.

CPU
---

Consider [Arduino Nano 33 BLE](https://store.arduino.cc/products/arduino-nano-33-ble-sense).

Software
--------

Probably [Tensorflow Lite](https://www.tensorflow.org/lite/microcontrollers).

Power
-----

Ideally solar with no need for battery charging, or a mechanical thumb button that uses a small dynamo to produce momentary charge.

Enclosure
---------

Consider the tricorder design. Play up the utopic Star Trek connection, either
as a superstructure over a cellphone or a wireless tricorder scanner puck. It
should have some superfluous led awesomeness so people who see this 
will ask "what is that?"

![image](https://trekcentral-net.cdn.ampproject.org/i/s/trekcentral.net/wp-content/uploads/2022/11/915416-1501x1536.png)

Consider inviting participation from indigenous communities in co-designing this. 
