# Gesture-Controlled Drone

A gesture-controlled drone project that uses computer vision and Arduino-based transmitter control to let a user fly a drone using hand gestures instead of a traditional remote controller.

## Overview

This project combines:
- Python and OpenCV for real-time hand tracking
- MediaPipe for gesture recognition
- Arduino Nano for transmitter control simulation
- An original RF transmitter to send commands to the drone

The system captures hand gestures from a webcam, interprets the movement, and converts them into flight commands such as:
- forward
- backward
- left
- right
- takeoff
- land
- rotate left
- rotate right

## System Architecture

1. PC / Laptop with Webcam
   - Uses OpenCV + MediaPipe to detect hand gestures.
   - Interprets commands such as movement and flight actions.

2. Arduino Nano
   - Receives commands from the PC via USB.
   - Converts the commands into transmitter-like control signals.

3. Original Transmitter
   - Wired to the Arduino.
   - Sends radio signals to the drone.

4. Drone
   - Receives the wireless command and performs the requested motion.

## Hardware Interaction

The Arduino Nano is connected to the transmitter joystick/control lines as follows:
- D9 → VRX (Right stick X)
- D10 → VRY (Right stick Y)
- D11 → VLX (Left stick X)
- D12 → VLY (Left stick Y)
- 5V → Transmitter power
- GND → Transmitter ground

This method allows the Arduino to simulate joystick movement and trigger the transmitter as if a human operator were controlling it.

## Important Notes

- Use the transmitter pins that correspond to your specific remote model.
- The transmitter normally runs on 5V, so power and ground must be shared properly.
- The Arduino and transmitter should share the same ground to avoid unstable behavior.
- This method works with standard RC transmitters that accept joystick-like control signals.

## Project Flow

1. Camera detects hand gestures.
2. OpenCV and MediaPipe recognize the gesture.
3. The PC sends command data to the Arduino.
4. Arduino sends the appropriate signal to the transmitter.
5. The transmitter sends radio control to the drone.
6. The drone responds to the command.

## Use Cases

- Gesture-based drone control for education and experimentation
- Human-machine interface research
- Computer vision and embedded systems prototyping
- RC drone interaction projects

## Example Commands

The project can interpret gestures such as:
- hand raised upward → move forward
- hand lowered → move backward
- hand moved left → move left
- hand moved right → move right
- open palm → takeoff
- closed fist → land
- rotation gestures → yaw left or right

## Requirements

- Python 3
- OpenCV
- MediaPipe
- Arduino Nano
- Original drone transmitter
- USB cable for Arduino communication
- Webcam

## Project Goal

The goal of this project is to replace traditional remote-control input with natural hand-based gestures, showcasing how computer vision and embedded systems can work together to create a more intuitive drone interface.

## Notes

This project is a prototype and may require calibration depending on:
- the transmitter model
- camera position
- gesture recognition accuracy
- drone model and transmitter compatibility

## License

This project is released for educational and experimental use.
