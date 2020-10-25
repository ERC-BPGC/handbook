# Blue Pill (STM32F103C8T6)

## Introduction
The STM32F103C8T6 (also known as 'STM32' or 'Blue Pill") is a cheap development board based on the ARM Cortex M3 microprocessor. [This](https://www.youtube.com/watch?v=EaZuKRSvwdo) video by Great Scott can prove to be an introductory video to understand what it exactly is and how it can be used.

<p align="center">
<img align="center" src="https://github.com/adbidwai/handbook/blob/master/docs/electronics/Development_Boards/images/bluepill_intro.jpeg">
</p>

## Naming Convention of STM microcontrollers </br>
|**Parameter**|**Meaning**|
|---------|-------|
|STM| name of the manufacturer (STMicroelectronics)| </br>
|32| 32 bit ARM architecture |</br>
|F|Foundation |</br>
|1| Core (ARM Cortex M3)| </br>
|03| Line (describes peripherals and speed) </br>
|C| 48 pins </br>
|8|64 KB flash memory</br>
|T|LQFP package (Low Profile Quad Flat Pack) </br>
|6|Operating Temperature Range (-40 °C to 85 °C) </br>

## Technical Specifications of STM32 </br>
|**Parameter**|**Meaning**|
|---------|-------|
|Architecture|32 bit ARM Cortex M3 </br>
|Operating Voltage| 2.7V to 3.6V </br>
|CPU Frequency | 72 MHz </br>
|Number of GPIO pins| 37 </br>
|Number of PWM pins| 12 </br>
 |Analog Input Pins| 10 (12 bit resolution) </br>
 |I2C Peripherals| 2 </br>
 |SPI Peripherals| 2 </br>
 |CAN 2.0 Peripheral|1| </br>
 |Timers | 3(16-bit), 1| (PWM) </br>
 |Flash Memory| 64KB |</br>
|RAM| 20kB |</br>

## Programming STM32 </br>
### 1) 
For more insights about the technical specifcations refer to the [official datsheet](https://www.st.com/resource/en/datasheet/stm32f103c8.pdf) and [reference manual](https://www.st.com/content/ccc/resource/technical/document/reference_manual/59/b9/ba/7f/11/af/43/d5/CD00171190.pdf/files/CD00171190.pdf/jcr:content/translations/en.CD00171190.pdf) by STMicroelectronics.
