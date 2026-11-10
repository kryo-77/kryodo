# Kryodo

Kryodo is a self balancing, two wheeled robot. It is inpiered by BD-X droid which was made by Disney.

![isometric front view](images\iso_main.png)

![isometric back view](images\iso_back.png)

## What it is

Kryodo is a self balancing robot which has two wheels.

It is about 35cm tall. It's legs are static with motors at the bottom. It has a moving head using a pan-tilt servo mechanism. 

We can control this robot either using WIFI or having it move around on its own using open-cv. The head has a ESP32-CAM module inside which streams to your PC which takes care of the open-cv.
I plan to make a custom handheld controller to control this bot as well. 

It has an ESP32-DevKit-V1 as the main microcontroller which connects to a MPU6050 which measures angle. It uses two 300rpm motors and wheels of 7cm diameter, which provide enough speed and control to move the bot fast and steady. 

I've used two MG996R servos for pan-tilt mechanism for the bot as it gives the bot a lot of expressions. There are also two more SG90 servos on the back of the head which control the "ears" for even more expressions. I got this idea from BD-X droid made by Disney.

## Why I made it

I had always wanted to make a self balancing robot, but the usual rectangular box looking robots with no enclouser didn't fit my style. A few years ago I saw BD-X droid which looked very cool, and it fit my style. 

I wanted to make something like that but on my own, but it felt too complex the last few years but finally I got the chance to push myself and make this robot for a HackClub event. I wanted to make this for so long but due to its complexity, I procrastinated so much I forgot about it till a few weeks back.

## How it works

A ESP32-DevKit-V1 controls these things:
- 2x MPU6050 - tilt measure
- 2x BTS7960 motor driver - for 2x 300rpm motors.
- 1x PCA9685 - connects with 4 servos (2x MG996R & 2x SG90)
- WS2812b leds - cosmetic
- 0.91in oled - cosmetic
- 1.3in oled - cosmetic

The two oleds are on different pins on the devkit so they dont interfere with each other as they share the same address.

![front bot view](images\canva\4.png)

Here's how the back side looks like of the head: 

![head back view](images\canva\3.png)
The SG90servos control ears.

![iso front bot view](images\canva\1.png)

Here's the servo pan tilt mechanism: 

![front bot view](images\canva\2.png)

## File structure

- `images` folder contains all images (extras + readme)
- `cad` folder contains all cad files like .stl, .step, .f3z (fusion360).
- `firmware` folder contains two files: `main.ino` for ESP32-DevKit-V1 & `cam.ino` for ESP32-CAM module.

## Firmware

Proper firmware is remaning as I've not yet assembled the robot physically.

## Wiring schematic

![Wiring schem](images\wiring_schem.png)

A PCB is optional as I've only used full boards for all the electronic components. They're all connected together using jumper wires.

## BOM

| # | Component | Qty | Use | Price (INR) | Price (USD) | Link |
|---|-----------|-----|-----|-------------|-------------|------|
| 1 | ESP32 DevKit V1 | 1 | Main microcontroller | ₹487 | ~$5.20 | [Amazon](https://www.amazon.in/ESP32-Board-WiFi-Bluetooth-Development/dp/B0HHMRZ5RJ) |
| 2 | MG996R Servo | 2 | Head pan-tilt movement | ₹359 | ~$3.83 | [Robu](https://robu.in/product/towerpro-mg996r-digital-high-torque-servo-motor/) |
| 3 | Pan Tilt for MG996R | 1 | Head pan-tilt mechanism | ₹179 | ~$1.91 | [Robu](https://robu.in/product/servo-mount-brackets-for-mg995-mg996-servo-motor/) |
| 4 | SG90 Servo | 2 | Ear movement | ₹89 | ~$0.95 | [Robu](https://robu.in/product/towerpro-sg90-9g-mini-servo-9-gram/) |
| 5 | PCA9685 | 1 | Servo control | ₹249 | ~$2.66 | [Robu](https://robu.in/product/16-channel-12-bit-pwmservo-driver-i2c-interface-pca9685-arduino-raspberry-pi/) |
| 6 | ESP32-CAM with MB | 1 | Camera, video stream to PC | ₹729 | ~$7.78 | [Robu](https://robu.in/product/esp32-cam-mb-wifi-bluetooth-development-board-with-ov2640-camera-micro-usb-connection-to-serial/) |
| 7 | 1.3in OLED | 1 | Cosmetic display | ₹369 | ~$3.94 | [Robu](https://robu.in/product/1-3-inch-i2c-iic-oled-4-pin-lcd-module-4pin-with-vcc-gnd-blue/) |
| 8 | 1.3in OLED | 1 | Cosmetic display | ₹189 | ~$2.02 | [Robu](https://robu.in/product/blue-oled-display-module/) |
| 9 | WS2812B LEDs | NA | Lighting effects | NA | NA | NA |
| 10 | 300RPM Motor | 2 | Wheel drive, speed feedback | ₹1500 | ~$16.01 | [Robokits](https://robokits.co.in/motors/encoder-dc-servo/high-torque-12v-dc-encoder-motor/dc-12v-300rpm-high-torque-quad-encoder-motor) |
| 11 | BTS7960 Motor Driver | 2 | Motor control | ₹330 | ~$3.52 | [Robokits](https://robokits.co.in/motor-drives-drivers/dc-motor-driver/bts7960-high-power-driver-module-43a?products_id=1859:537de305e941fccdbba5627e3eefbb24/) |
| 12 | MPU6050 | 1 | Orientation, motion sensing | ₹450 | ~$4.80 | [Robu](https://robu.in/product/mpu6050hmc5883lbmp180-10dof-3-axis-gyro-3-axis-acceleration-3-axis-magnetic-field-air-pres/) |


## Notes
Many changes are still needed for mounts such as servos and the motors. Thickness of leg also needs adjusting which can only be done once motor arrives as datasheet is not accurate.