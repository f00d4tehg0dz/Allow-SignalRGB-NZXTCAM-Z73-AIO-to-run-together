# Allow-SignalRGB-NZXTCAM-Z73-AIO-to-run-together
 Allow for SignalRGB to control your LED lights on your NZXT AIO and NZXT CAM to control your Cooling settings
 Run NZXT CAM software alongside SignalRGB without conflicts.


## Demo
- ![](https://github.com/f00d4tehg0dz/Allow-SignalRGB-NZXTCAM-Z73-AIO-to-run-together/tree/main/screenshots/screencap.gif)
- ![](https://github.com/f00d4tehg0dz/Allow-SignalRGB-NZXTCAM-Z73-AIO-to-run-together/tree/main/screenshots/videocap.mp4)

### Prerequisites

Before you begin setting this up

1. **Disable SignalRGB Settings**: You should toggle off in SignalRGB Windows Settings under Settings>App Settings>Windows Settings, the Automatically Closing Conflicting Programs

2. **System Requirements**: Ensure your system meets the following requirements:
   - [SignalRGB](https://signalrgb.com/download) installed
   - [NZXT CAM](https://nzxt-app.nzxt.com/NZXT-CAM-Setup.exe) installed 

---

### Installation Guide

Follow these steps to set up SignalRGB to run congruently with NZXT CAM 

1. **Copy the Nzxt_Kraken_Z3_AIO.js**:
   - Copy the `Nzxt_Kraken_Z3_AIO.js` and paste it in the Nzxt folder. Note: `app-2.3.43` is the version I'm using, please change to the correct version number of your installation:
   ```bash
   C:\Users\%USERNAME%\AppData\Local\VortxEngine\app-2.3.43\Signal-x64\Plugins\Nzxt
   ```

2. **Restart**:
   - Restart and or Start SignalRGB.

3. **Start NZXT CAM**:
   - Start NZXT CAM, and ensure the cooling and AIO display is functioning correctly

4. **(OPTIONAL)**:
   - If you wish to instead start NZXT CAM with Windows Task Scheduler instead of manually starting NZXT CAM on every reboot. I have my Task Scheduler set to start NZXT CAM after I have logged into my system with a delay of 5 minutes 

### Configuration Details

If you have a different NZXT AIO than the Z73 Kraken. There are several other `.js` files in the Nzxt folder. You can either open an issue on and I will modify the appropriate `.js` file for you. Or you can try yourself!

- **Edit an NZXT AIO js file**:
  - Strip out all mention of Fan, Pump, Polling, and Control settings. 
 Ensure to leave logic only for the LED fans

- **Set to False**:
  - In the `SupportsFanControl` control logic, change `return true;` to `return false`
  ```bash
    export function SupportsFanControl(){ return false;}
  ```

## FAQ

#### Do I need to edit any other `.js` files in the NZXT folder?

- Only if your AIO is different than the Z73 model. You will need to retain all LED logic, and set fan settings to false 
```bash
  export function SupportsFanControl(){ return false;}
```

#### Do I have to use NZXT CAM?

- Absolutely not, you can use [KrakenZPlayground](https://github.com/ProtozeFOSS/KrakenZPlayground) to control your NZXT AIO LCD Screen

## Feedback

- If you have any feedback, please open an issue! Thank you