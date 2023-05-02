# DesktopSensorHub
A board designed to connect to a desktop computer via USB, and add sensors such as ambient light, color, proximity, gestures, and more via standard Linux IIO

## Preview (from OSHPark)
![Front of board](/OSHPark/oshpark_front.png)
![Back of board](/OSHPark/oshpark_back.png)

## Software references
- Article about the below: https://hackaday.com/2022/10/31/need-an-usb-i2c-adapter-use-your-pico/
- Repo for RP2040 i2c interface: https://github.com/Nicolai-Electronics/rp2040-i2c-interface
- Linux module compilation/setup: https://petermolnar.net/article/linux-i2c-iio-collectd/

## Board references
- Adafruit breakout for Avago APDS9960 proxmity, ALS, color, gesture sensor: https://www.adafruit.com/product/3595
- Adafruit QT2040 board for i2c -> USB: https://www.adafruit.com/product/5056

## Roadmap
- [x] Test prototype once boards arrive
  - Problem encountered, APDS9960 iio i2c driver needs an interrupt, but no interrupt is provided via RP2040 i2c bridge. Need to figure out if we can somehow provide an interrupt over USB or maybe by acting as a GPIO expander as well
- [x] Design PCB, preferrably with USB-C connector on sensor hub
- [ ] Design 3D printed case for sensor so it can mount on top of your PC like a webcam (maybe?)
- [x] Test v1 PCB
  - With much pain, eventually 1 working board as a result, lessons learned
- [ ] Optimize, reduce footprint
  - Remove button, switch to small header, move RP2040 & flash closer to USB port
  - Remove capacitors from USB data lines (not needed)
  - Add test points for APDS9960
  - Move APDS9960 to front of board for ease of assembly
  - Switch to crystal with smaller footprint (less tall)
  - Change test points to plates through holes(?)
  - Break out some extra GPIO because why not
- [ ] Test v2 PCB
- [ ] Release, make repo public (probably no one will care)
- [ ] Write userspace daemon to handle gestures, color temperature calculation and display color adjustment. Would handle display brightness adjustment too, but I think that would be better served by [wluma](https://github.com/maximbaz/wluma)
- [ ] Figure out if wake on proximity sensor is possible

## Related projects
- ColorhugALS: https://blogs.gnome.org/hughsie/2015/05/27/colorhugals-and-sensor-hid/ by https://hughsie.com/. Maybe send him an email once you have something interesting?
