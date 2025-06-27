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
![guitar_fft](https://github.com/user-attachments/assets/266737d4-b064-4a65-8211-d8823fa5be0a)

Source: https://www.researchgate.net/publication/331620271_Real-time_quasi-distributed_fiber_optic_sensor_based_on_resonance_frequency_mapping

It's important to note that the sensor for the tuner will be much more noisy, and so the frequency transform will probably have a lot more noise than the one displayed in the image.
One big potential issue when moving from a single string tuner to multiple strings will be the interference between harmonic frequencies of a note.

For example, the low E string has a base frequency of 82 Hz, and so it has harmonics at frequencies x2, x3, x4 and so on of the base frequency. So, these harmonics are at 164 Hz, 246 Hz, and 328 Hz. 
It's immediately obvious that these could interfere with the B string at 247 Hz or the e string at 330 Hz.

I have a couple ideas for how to resolve this harmonic interference issue, but I won't know what works well until I try it out with the actual hardware.

## Initial Project Requirements

I want a base set of requirements to add some constraints to the project.
A good tuner will have a high degree of accuracy and it will have low latency so you can quickly adjust the string to the right value.

To measure accuracy, I'll use the idea of semitones and cents. A semitone is a jump from a given note to the next note. A cent is 1/100 of a semitone.

So, for the low E string, the base frequency is 82.41 Hz and the next closest notes are E-flat, at 77.78 Hz, and F, at 87.31 Hz. A cent in terms of frequency is roughly (87.31-77.78)/200 => 0.05 Hz.
Wikipedia suggests that it takes a couple cents for the ear to distinguish tones. https://en.wikipedia.org/wiki/Cent_(music)

So, that leads me to requirements for the project:

Tuning:
1. The tuner shall measure the frequency of a string played on the guitar.
2. The tuner shall inform the user of the closest note to the string played, and if the guitar string is sharp or flat.
3. The tuner shall have an accuracy of within +/- 2 cents.

Latency:
1. The tuner shall have a latency of less than 200 ms, measured from when the string is played to when the tonal information is displayed.

## Component Selection

I don't want to design a PCB for this project (yet), so all the components selected must be available in some sort of evaluation or breadboard fashion.

I recently have used a click-E evaluation board for work, and so I figured this would be a good starting place to find different boards to use. The click-E is basically a standardized connector format with many different eval board attachments.
https://www.mikroe.com/click

Because I want to have some flexibility with using this part in the future, and I want to learn on something representative of what is used in industry, I decided to go with a STM32 ARM MCU. I also want 4 click-E expansion slots. 

This leaves me with the following MCU options:
1. STM32F745VG
2. STM32F302VC
3. STM32F407VG

Since all the evaluation boards are the same price, and I don't plan on building this into a consumer product, I'll just go with the MCU that is fastest and has the most memory: STM32F745VG

I notice that the STM32 also has two integrated ADCs. I may be able to use these instead of getting a separate click-E ADC board.

This is an example of the click-E evaluation board with random click-E modules filled in.
![image](https://github.com/user-attachments/assets/d0bb7c63-20f8-4b41-9a21-9d137f9eef9b)









