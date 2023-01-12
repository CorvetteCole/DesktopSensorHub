# DesktopSensorHub
A board designed to connect to a desktop computer via USB, and add sensors such as ambient light, color, proximity, gestures, and more via standard Linux IIO

## Software references
- https://hackaday.com/2022/10/31/need-an-usb-i2c-adapter-use-your-pico/
- https://github.com/Nicolai-Electronics/rp2040-i2c-interface

## Board references
- Adafruit breakout for Avago APDS9960 proxmity, ALS, color, gesture sensor: https://www.adafruit.com/product/3595
- Adafruit QT2040 board for i2c -> USB: https://www.adafruit.com/product/5056

## Roadmap
- Test prototype once boards arrive
- Design PCB, preferrably with USB-C connector on sensor hub
- Design 3D printed case for sensor so it can mount on top of your PC like a webcam (maybe?)
- Test v1 PCB
- Optimize, reduce footprint
- Test v2 PCB
- Release, make repo public (probably no one will care)
- Write userspace daemon to handle gestures, color temperature calculation and display color adjustment. Would handle display brightness adjustment too, but I think that would be better served by [wluma](https://github.com/maximbaz/wluma)
- Figure out if wake on proximity sensor is possible

