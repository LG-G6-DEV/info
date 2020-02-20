# Workarounds
Here are all currently needed workarounds listed.  
Table of Contents:
+ [Phantom-Camera](#Phantom-Camera)

## Phantom-Camera
**Description:** Appearance of a 4th, not existent camera in the system.  
**Faulty Behaviour:** The system reports 4 cameras back. When attempting to access the last one, camera services or manager dies resulting in crashes of apps etc.  
**Analysis:** The LG G6 ships with multiple, possible sensors for the rear, wide-angle camera as seen in the
[camera_config.xml](https://github.com/LG-G6-DEV/proprietary_vendor_lge/blob/lineage-17.0/g6-common/proprietary/vendor/etc/camera/camera_config.xml). 
The system mistakenly adds all sensors regardless of whether or not they are present which leads to the appearance of the wrong camera.   
**Workaround:** The current workaround is to do a few framework patches for both camera1 and camera2 API.
[Necesary Changes](https://github.com/LG-G6-DEV/havoc_frameworks_base/commit/794cb90533137816436ccd26ff2e04947fb12e31)  
Some ROMs like LineageOS moved the retrieval of the camera amount in camera1 to a native method.  
Then,
[this](https://github.com/LG-G6-DEV/android_frameworks_base/commit/9fe519e9dcc3f0fa622aa23981944e80499d2ebc)
must be applied for camera1 instead.  
Other ROMs that are more AOSP based still use AOSPs restrictive nature in regards to exposing multiple sensors at all.  
If that's the case,
[this commit](https://github.com/CarbonROM/android_frameworks_base/commit/3ecaf4e43c82b0037cd2a474985ad01eb58e1ee3) or similar modifications are required before applying any of the before mentioned fixes.  
**Further References:** None so far.  

## Template
**Description:** Description  
**Faulty Behaviour:** Description  
**Analysis:** Description  
**Workaround:** Description  
**Further References:** Logs, fix attempts etc. go here.  