# Distance-Sensor-Gimbal
Rapid prototype for a distance sensing gimbal. The system is controlled by a STM 32 programmable controller, the system can sense its surroundings automatically by executing a programmable subroutine, or can be controlled manually via a joystick setup (see 2 mode setup).

Note: this is a part of a school project and the code developed to control the MCU cannot be published. It is very standard NUCLEO C code that describes the subroutine and handels UART communication.

## Gimbal tech stack
- 1 STM32 Nucleo-F401RE board as its MCU and for UART communication
- 2 motor for 2 axis of rotational motion (pan and tilt)
- 1 supersonic sensor as its distance sensor (also its eyes)
- 1 Laser pointer
- 1 analog control stick 
- 2 step up and down IC buffer
- 1 LED to indicate state change

## Two modes of operation
### Mode 1: Automatic Mode

Gimbal automatically scan 180 deg. The motor will stop for a few seconds if it detect an object in front of it, and then continue moving. Once Gimbal finish scanning, the LED on the breadboard will turn blue and the system stops moving.
- When Gimbal detects an object, it will attempt to find it's center, points to it, flash the laser 3 times, then proceed to continue moving
- when the Gimbal is scanning, LED is GREEN, when it detects something, LED becomes RED, when it finishes scanning, LED turns BLUE
- Upon system reset, the Gimbal will start executing the Mode 1 subroutine

[Automatic Mode DEMO](#automatic-mode-demo)
 
### Mode 2: Manual Mode

Gimbal can be controlled by the joystick, 4 directions of movement. system in mode 2 if the LED on the bread board starts to switch color between RGB.

[Manual Mode DEMO](#manual-mode-demo)


# Gimbal operation instruction
1. power up the STM32 - connect gray USB wire to computer and STM32 
2. power up the motor using external power supply - the two motors requies 5V external power supply which cannot be provided by the STM32 board, thus we use external batteries or power generator to supply the power
3. press the black button on the PCB to reset the system to Mode1 (automatic mode). Wait for the the Gimble finish the 180 deg movement and the entire system stops moving
4. Press the blue button on the PCB to turn the system to Mode2 (manual mode). Now you can move the Gimbal with the joy stick!

Note: You can press the the blue button at any time to go to Mode 2, press the black button to reset (which start to Mode 1 subroutine) 

# Demo

### Automatic Mode Demo

 https://github.com/Huan-YiShen/Distance-Sensor-Gimbal/assets/76965211/90812e05-ba04-4eaa-a7f9-0dd3ac12ba32

### Manual Mode Demo

https://github.com/Huan-YiShen/Distance-Sensor-Gimbal/assets/76965211/d01c165f-cba9-4887-aed6-087987f7e8af
