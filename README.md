# Arduino PWM LED & OLED

## Overview
This project is built on an Arduino Nano and controls six PWM LEDs and an OLED screen. The LEDs' brightness can be dimmed using a button, and another button toggles their on/off state. Additionally, an animated heart shape is displayed on the OLED screen, along with an image of Timon from The Lion King. The image frames are stored as XBM files, and the animation is displayed using the U8g2 library.

## Features
- **PWM LED Control**: Six PWM-capable LEDs can be turned on/off and dimmed using buttons.
- **OLED Animation**: Displays an animated heart on the OLED screen and an image of Timon from The Lion King.
  
### Button Controls:
- One button to toggle the LEDs on and off.
- Another button to cycle through LED brightness levels (100%, 50%, 30%, 10%).

## Components Used
- **Arduino Nano**: Microcontroller board used to control the LEDs and OLED screen.
- **OLED Display**: SSD1306 128x64 0.96", used to display the heart animation and Timon image.
- **LEDs**: Six PWM LEDs connected to pins 9, 10, 11, 6, 5, and 3 of the Arduino.
- **Buttons**: Two buttons, one for toggling the LEDs and another for dimming.

## Libraries
- **U8g2**: Library by Oliver for controlling the OLED display.
- **Wire**: I2C communication library, used for communicating with the OLED.

## Wiring
- **OLED Screen**: Connects to the I2C pins (SCL and SDA) of the Arduino Nano.
- **PWM LEDs**: Connected to pins 9, 10, 11, 6, 5, and 3.
- **Buttons**: Connected to pins 7 (toggle button) and 2 (dimming button).

## Code Explanation
The code begins by initializing the U8g2 library for the OLED screen. It then defines the pins for the LEDs and buttons. The buttons are debounced to avoid multiple triggers from a single press. The `heart_bits` array stores the XBM files for the heart animation, and each frame of the animation is shown sequentially on the OLED. The LEDs' brightness is controlled by a dimming button, cycling through predefined levels. The LEDs' state can be toggled on and off with another button.

### Key Variables:
- **heart_bits**: Array storing the XBM data for the heart animation frames.
- **pwmPins[]**: Pins connected to the PWM LEDs.
- **LED control**: Manages the on/off state and brightness of the LEDs.
- **buttonPressed**: Tracks if the toggle button was pressed.
- **dimButtonPressed**: Tracks if the dimming button was pressed.

## How to Use
1. **Connect the hardware**: Wire up the Arduino Nano, LEDs, buttons, and OLED screen according to the provided connections.
2. **Upload the code**: Load the code onto the Arduino Nano using the Arduino IDE.
3. **Use the buttons**:
   - **Toggle Button (Pin 7)**: Turns the LEDs on and off.
   - **Dimming Button (Pin 2)**: Cycles through brightness levels of the LEDs.
4. **View the animation**: The heart animation will appear on the OLED, followed by Timon from The Lion King.

## Files Used
- **XBM Files**: The heart animation and Timon image are stored as XBM files. These were originally in JPG/PNG format and converted using GIMP and FRHED.
- **FRHED**: Used for reading the XBM files and extracting the necessary data for the animation.
