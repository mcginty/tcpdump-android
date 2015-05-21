Overview
--------
This script will compile tcpdump for use on modern Android devices.

Forked from https://github.com/chatch/tcpdump-android, originally by Loic Poulain on OMAPpedia (http://omappedia.org/wiki/USB_Sniffing_with_tcpdump).

Build
-----
Install the [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html) (`brew install android-ndk` if you have Homebrew) then run the following, replacing the ndk path accordingly:  

    export NDK_HOME=/usr/local/Cellar/android-ndk/r10d/
    ./build-tcpdump

Install
-------
    adb root
    adb remount
    adb push build/tcpdump /system/xbin/tcpdump
    adb shell chmod 6755 /system/xbin/tcpdump

Run
---
    adb shell tcpdump -vv -i any -s 0 -w /sdcard/capture.pcap

Then pull from your device and go on your merry way down wireshark road.
