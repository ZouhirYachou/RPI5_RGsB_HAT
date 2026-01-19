# Raspberry Pi 5 RGsB HAT

A Raspberry Pi 5 HAT PCB that generates analog RGsB (RGB Sync on Green) using the GPIO with RGB666 mode (VGA666).


## What it does
- Outputs analog RGB from GPIO with RGB666 mode (PCB design inspired by the Passive VGA adapter 666 https://github.com/fenlogic/vga666)
- Provides SOG (CSYNC generated from HSYNC and VSYNC thanks to the PIO Hardware RP1 on RPI5)
- Only works with Raspberry Pi 5
- Solder pads to install a 12V to 5V (3A Max) buck converter
  
## Repository contents
- `hardware` – Schematic, Gerber, BOM, Pick and place
- `rgsb_hat_setup.sh` Bash script to install requirements, CSYNC service and display configuration for 240p analog output

## Getting started
1. Install assembled PCB to RPI 5
2. Run the rgsb_hat_setup.sh
3. Connect to supported display: This was designed for embedded 6.5 inches displays on BMW E series (E46, E85, E83 ...) where it only accepts analog RGsB signal at 400*240p resolution. 

## Safety / warnings
- With the buck converter, do not plug any other power source to the RPI5.
- 75Ω termination should already be present on the display side.

## Contributing
- Any improvements on the design are welcome.

## Todo list
- Improve with a buck converter integrated to the PCB design

## Images

3D Render of the latest version of the PCB
<p align="center">
  <img src="images/PCB_RPI_HAT_RGsB.png" width="600">
</p>

This below picture is using the previous version of the PCB with a Pi Pico for CSYNC https://github.com/mbt28/pico-csync-generator
With the current design, CSYNC is integrated with the RPI5 PIO Hardware, no need to use an additional Pi Pico
<p align="center">
  <img src="images/PXL_20251115_114836545.jpg" width="600">
</p>

Display 400*240p resolution on OEM CID on a BMW E85/E86
<p align="center">
  <img src="images/PXL_20251115_114838423.jpg" width="600">
</p>
