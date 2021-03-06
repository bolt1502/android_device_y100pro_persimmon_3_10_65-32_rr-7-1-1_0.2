Device repository for Doogee Y100Pro (CyanogenMod)
===========================
For Stock 3.10.65 kernel

Это дерево создано на основе работы @divis1969 , без него ничего бы не было.

Getting Started
---------------

Initialize a repository with CyanogenMode:

    repo init -u git://github.com/CyanogenMod/android.git -b cm-14.1
    
Sync sources:    

    repo sync
    
Build the code:
    
    cd device
    mkdir y100pro
    cd y100pro
    git clone https://github.com/bolt1502/android_device_y100pro_persimmon_3_10_65-32_rr-7-1-1_0.2.git persimmon
    cd persimmon/patches
    . apply-patches.sh
    cd vendor
    mkdir y100pro
    cd y100pro
    git clone https://github.com/bolt1502/android_vendor_y100pro_persimmon_3_10_65.git persimmon
    cd ../../
    source build/envsetup.sh
    breakfast persimmon
    make -j 4 bacon

Current state
-------------

- Cyanogen boots
- Touch, screen, keyboard working
- Wifi is working
- Audio is working
- Telephony is working (see Known Issues)
    - USIM (3G) supported
    - Incoming/outgoung call
    - SMS, USSD
    - Data connectivity
- GPS
- Bluetooth (pairing only testes so far)
- Sensors

Known Issues
-------------
- Android Camera App is not stable (hangs) ex. with location enabled
- Camera
- Telephony crashes eventually on location request from camera. 
- Hardware OMX codecs are not working

Change log
----------

### v0.2
- Fixed an issue with proximity on some devices
- Fixed an issue with ICC IO in MTK ril (no radio with some SIM cards)
- Fixed a modem crash caused by mtk_agps request
- Fixed an issue with WiFi SoftAP
- Ported power HAL from CyanogenMod 6735 (also implements Double Tap To Wake feature)
- Ported FOTA solution from meilan2 cm-12.1

### v0.1
- Initial port from cm-14.0 (v0.3) to cm-14.1

