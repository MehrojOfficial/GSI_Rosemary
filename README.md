# GSI INSTALLATION PROCESS
Everything to boot any GSI on Redmi Note 10S/11 SE India/Poco M5S

### ⚠️ If you are stuck on some step re-register drivers (Except one mentioned to take a certain amount of time)

**BEFORE STARTING:**
  1. Backup all your data
  2. Choose correct GSI image
  3. Visit here to download everything required -> [DOWNLOAD](https://www.pling.com/p/1951771/)

**REQUIREMENTS:**
  1. Computer (Windows is preffered)
  2. Unlocked bootloder
  3. Internet accees
  4. Knowledge to unbrick the device
  5. Unlimited patience

**Which firmware to use:**
  - MIUI 12.5 -> Android 11/12/12L/13 (preffered to avoid bugs)
  - MIUI 13 -> Android 12/12L/13
  
   (For GSI region doesn't matter)

**Which variant to choose:**
  - 'arm64' -> must for this device;
  - 'bgn' -> with GApps;
  - 'bvn' -> Vanilla (without GApps);
    
    (Don't use 'slim', 'light' sub-variants)
    
**Example naming options:**

    SparkOS-13.2-arm64_bgN-Unofficial.img.xz -> OK
    SparkOS-13.2-arm64_bvN-Unofficial.img.xz -> OK
    
    SparkOS-13.2-a64_bvN-Unofficial.img.xz -> Not OK
    SparkOS-13.2-a64_bgN-Unofficial.img.xz -> Not OK

# NOW THE REAL PROCESS BEGINS

**1. Reboot to fastboot:**
  - Turn off the device completely;
  - Press power button and volume down button together;
  - After you see "REDMI logo" release power button, but keep volume down pressed until you see "FASTBOOT" on screen.

**2. Install Windows drivers:**
  - Download "Fdrivers.zip" and extract it in easier location.
  - Keep the device connected to your PC during process.
  
  On PC:
   - Windows + X → Device Manager → Find Android and Right Click on it ↓ 
   - Update drivers → Browse my computer for drivers ↓
   - Let me pick from a list of available drivers on my computer↓ 
   - Have a disk → Browse → Find extracted drivers folder ↓
   - Open the folder → Select 'android_winusb.inf' → Click Open -> OK ↓
   - Then click Next and accept anything that pop-up.
    
  (In Windows 11, do the action again every time when you log out of "FASTBOOT" mode.)

**3. Preparation before installing:**
  - Download "platform-tools.zip' and extract it in "C" drive. 
  - Copy "product-gsi.img" to "C:\platform-tools" folder.
  - Copy your GSI rom in .img format to C:\platform-tools" folder and rename it to "gsi.img". 
  - Open "Terminal" in this folder.
   
   (Extract if the file is in '.xz' , '.gz', '.zip', etc format)


**4. Then do every command one by one in order to get no errors:**

```
fastboot reboot fastboot
```
```
fastboot delete-logical-partition product_a
```
```
fastboot create-logical-partition product_a 1000
```
```
fastboot flash product product-gsi.img
```

Next process a takes certain amount of time. Sit back and relax.
```
fastboot flash system gsi.img
```
```
fastboot -w
```
```
fastboot erase userdata
```
```
fastboot reboot
```
**5. Complete setup and enjoy.**

# Fixing issues in GSI ROM:

In Phh Treble Settings:
- For double tap to wake: enable it in 'Xiaomi features' > 'Enable DT2W' ;
- For headphone jack: enable 'Misc features' > 'Use an alternate way to detect headsets' ;
- If you want AOD: enable 'Misc features' > 'Force allow Always-On Display' ;
- For brightness: enable 'Misc features' > 'Force alternative backlight scale' ;
- For reaching lower brightness: enable 'Misc features' > 'Allows setting brightness to the lowest possible' ;
- For smooth brightness slider: enable 'Misc features' > 'Use linear screen brightness slider' ;
- For Bluetooth audio enable: 'Misc features' > 'Force-disable A2DP offload' ; 
- For Bluetooth stability: 'Misc features' > 'Bluetooth workarounds' > 'Mediaktek' ; 

SafetyNet issues (Root+Magisk):
- Flash kdrag0n's SafetyNet fix (https://github.com/kdrag0n/safetynet-fix)
