# Klipper Install & Config


## Process Notes

### 4/18/23

Doing a little research, I've decided to install an external mosfet to handle the bed heater. [I grabbed this one off of Amazon](https://www.amazon.com/HiLetgo-Power-Module-Expansion-Printer/dp/B07CGN7NCG?crid=249ICESN2PVOT&keywords=24v+external+mosfet+3d+printer&qid=1681880631&sprefix=24v+external+mosfet+3d+printer%2Caps%2C144&sr=8-4). So, this will get rid of the Creality board. Now, I will need to use the CAN board in order to use the Z-tilt feature. But, as of rn, I'm going to just use the SKR Pico dual ports. That way I have a checkpoint to do some troubleshooting.

### 4/11/23

Okay, so one of the big changes I'm making, right now, is dual z in order to use Klipper's Z-Tilt feature [1]. Now for the board, I bought the SKR Pico. Which sucks because it doesnt have dual-z steppers. Just dual-z ports. As of right now, I have a SKR Pico, Creality v4.2.7, and a BTT EBB42 CAN. Obviously there are a myriad of ways to get this setup. As of right now, my biggest pain point is the head ache to figure it out. Here are my options
  1. Return the SKR Pico
  2. Use both the v4.2.7 and Pico. One of them would just run the dual-z
  3. Use the Pico and CAN board. CAN board has it's own stepper

Obviously, the first option is easiest and the third makes the most sense. As of rn, I'm committed to using the Pico and CAN board. Pray for me.

Also double-checking the Pico Board will work with the new bed. SKR Pico on the heater bed port is 8A [2]. The Gulfcaost bed needs 10.4A [3]. Fuck. Quick The v4.2.7 max is 15A [4]. Well, looks like I'm using all three boards. So I'm going to get the Pico and v4.2.7 setup and then figure out the CAN board.


## Citation Links

1. [Klipper Config Reference](https://www.klipper3d.org/Config_Reference.html?h=pixel)
2. [Reddit - Power Specs on SKR Pico](https://www.reddit.com/r/BIGTREETECH/comments/yjvg5u/power_specs_on_skr_pico/) 
3. [3-Point Heated Bed Upgrade For Creality Ender 3 5 And Pro 3D Printers](https://gulfcoast-robotics.com/collections/creality-ender-3-upgrades-and-parts/products/aluminum-build-plate-and-24v-200w-silicone-heater-for-heated-bed-creality-ender-3)
4. [Official Creality V4.2.7 Silent Board For Ender-3(Pro)/Ender-3V2/Ender 5](https://www.creality3dofficial.com/products/creality-silent-mainboard-v4-2-7)

I've borrowed heavily from these repos

- [simeonpashley/klipper_config](https://github.com/simeonpashley/klipper_config)
- [rootiest/zippy-klipper_config](https://github.com/rootiest/zippy-klipper_config)
