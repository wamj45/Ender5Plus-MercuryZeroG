# Ender5 Plus

### **Please save profiles with names that are easy to identify. Avoid terms like `Generic`, `Standard`, etc. Default profiles use these terms and can easily lead to confusion on which profile to use.**

## OrcaSlicer
- [ ] Select the `Prepare` tab
### Create Printer Profile
- [ ] Start with a default `RatRig V-Core 3 400` printer
- [ ] Click the `Edit Preset` icon.
#### Basic Information Tab
- [ ] Set `Printable Height` to `375mm`
- [ ] Check the boxes for `Use relative E distances` and `Use firmware retraction`
- [ ] Select `Printable area`. Set `Size x`:`350` `Size y`: `325`. Origin should be `x:0 y:0`
- [ ] Save Profile
#### Machine G-Code Tab
- [ ] Machine Start G-Code

   ```
   START_PRINT EXTRUDER_TEMP=[nozzle_temperature_initial_layer] BED_TEMP=[bed_temperature_initial_layer_single]
   ```
- [ ] Machine End G-Code
  ```
  END_PRINT
  ```
- [ ] Save Profile
#### WiFi Connection
- [ ] Click the `WiFi Connection Icon` next to `Edit Preset`. Set:
  - [ ] `Host Type`: `Octo/Klipper`
  - [ ] `IP`: `192.168.0.221`
- [ ] Test connection by selecting the `Device` tab. This should load a WebUI of the klipper instance for the machine. If not ensure correct `IP` address was set. Restart klipper.
- [ ] Save 


### PLA Profile
This profile is for **PLA** only!! Do not attempt to print any other material with these settings!
- [ ] Select `RatRig Generic PLA` profile
- [ ] Click the `Edit Preset` icon
#### Filament Tab
- [ ] Set `Flow ratio` to `0.9626`
- [ ] Ensure `Enable pressure advance` is box checked
- [ ] Set `Pressure advance` to `0.046`
- [ ] Set `Recommended nozzle temperature` `Max` to `250`
- [ ] Set `Nozzle` `First layer` and `Other layers` to `230`
- [ ] Set `Max volumetric speed` to `15`
#### Cooling Tab
- [ ] Anywhere you see the words `fan speed` set that value to `60%`
- [ ] Save Profile
  
### Quality Profile
**The following settings work with any layer height. For regular parts we use the `0.2mm` profile. If we ever need a higher quality part we can pass the same settings to any other profile with a smaller layer height, i.e `0.08mm`.**
- [ ] Ensure the `Advanced` slider is set to allow 
#### Quality Tab
- [ ] Scroll down to the `Advanced` section
- [ ] Set `Order of inner wall/outer wall/ infill` to `outer/inner/infill` 

#### Others Tab
- [ ] Under the `Bed adhesion` section set `Brim type` to `No-Brim`.  
**Note**: A brim may be needed depending on the part surface area. Or the material you are printing. But in general they are annoying and unnecessary
- [ ] Under the `G-Code output` tab set `Filename format` to 
```
{input_filename_base}.gcode
``` 
- [ ] Save Profile