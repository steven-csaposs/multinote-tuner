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

Microphone:

For the microphone, I have to choose between a standard microphone and a contact microphone. The contact microphone seems like a better option because it will only pick up the signal from the guitar, and will remove any ambient noise.
I selected this contact microphone from Amazon.
![image](https://github.com/user-attachments/assets/203b5137-0d96-4f91-baa6-b540021d3e8a)


