# multinote-tuner
Guitar tuner project that will give feedback on multiple strings at once.


## Overview

I've been playing the guitar for several months now, and I like to switch between tunings to play different songs. The tuner that I have is a simple clip-on tuner, so you play one string at a time, adjust it, and move onto the next string. However, I was thinking that you should be able to tune multiple strings at once.

I want to create a guitar tuner device that is capable of tuning multiple strings at once. So, the user could attach this tuner, then strum the 6 guitar strings, and receive feedback on each of the 6 different strings at the same time.

## Research

A guitar has six strings. Typically, these are tuned to EADGBe.
Each string would have the following base frequency:

| String    | Frequency |
| -------- | ------- |
| E | 82 Hz  |
| A | 110 Hz |
| D | 147 Hz |
| G | 196 Hz |
| B | 247 Hz |
| e | 330 Hz |

I would also want to support alternative tunings, like DGDGBD, for example, which have different frequencies. Regardless, we can see that the tuner should be capable of detecting frequencies from ~50 to 400 Hz.

Along with the base frequency of the note, guitar strings also have overtones. See the image below for a measurement of the overtones.

Source: https://www.researchgate.net/publication/331620271_Real-time_quasi-distributed_fiber_optic_sensor_based_on_resonance_frequency_mapping
