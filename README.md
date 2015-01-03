Overview
--------
This script will cross compile tcpdump for use on Android devices.

It was written by Loic Poulain on OMAPpedia. See http://omappedia.org/wiki/USB_Sniffing_with_tcpdump for full details.

Build
-----
Install the [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html) (`brew install android-ndk` if you have Homebrew) then:  

    export NDK_HOME=/ndk/is/here
    ./build-tcpdump

Install on Droid
----------------
    adb root
    adb remount
    adb push build/tcpdump /system/xbin/tcpdump
    adb chmod 6755 /system/xbin/tcpdump

Run
---
    adb shell tcpdump -vv -i any -s 0 -w /sdcard/capture.pcap
