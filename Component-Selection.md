## Component Selection

I don't want to design a PCB for this project (yet), so all the components selected must be available in some sort of evaluation or breadboard fashion.

Click-E evaluation board:

One option is the click-E 4 evaluation board. This has an STM32 microcontroller with 6 buttons, 6 LEDs, and 4 click-E slots. The best option available is the STM32F745VG for $83. However, while the click-E modules are very nice, there are some disadvantages in that the only interface included is SPI. So, for higher speed needs, like display interfaces, the click-E modules might not be sufficient. This is an example of the click-E evaluation board with random click-E modules filled in.
![image](https://github.com/user-attachments/assets/d0bb7c63-20f8-4b41-9a21-9d137f9eef9b)

STM32 STM32MP257F-DK Evaluation Board:

This is a more standard evaluation board, with more high speed IO and attached eMMC and DRAM for a similar price. It lacks the convenience and ease of the click-E modules, though. 

The high speed IO includes HDMI, CSI, 1‑Gbit/s Ethernet. I wouldn't necessarily need all of this high speed IO for this project but I could definitely see myself using it in the future.

![image](https://github.com/user-attachments/assets/445569c4-0a8f-4937-ac10-87e277763899)

As for the click-E modules required in this project, I don't expect to need a lot of click-E modules. I could use one to include a display, for example.


Microphone:

For the microphone, I have to choose between a standard microphone and a contact microphone. The contact microphone seems like a better option because it will only pick up the signal from the guitar, and will remove any ambient noise.
I selected this contact microphone from Amazon.
![image](https://github.com/user-attachments/assets/203b5137-0d96-4f91-baa6-b540021d3e8a)


