<div align="center">

# Android Emulator Helper Tool
### This script was made to greatly simplify interactions for testing with the official Android Emulator from Android Studio.
[![Android Studio Badge](https://img.shields.io/badge/Android_Studio-34A853?logo=androidstudio&logoColor=white)](https://developer.android.com/studio)
[![Linux Badge](https://img.shields.io/badge/Made_for_Linux-black?logo=linux&logoColor=black&labelColor=white)](https://distrowatch.com/dwres.php?resource=popularity)
![Testing Badge](https://custom-icon-badges.demolab.com/badge/Debug-BA160C?logo=tool&logoSource=feather&logoColor=BA160C&labelColor=white)
#

[![Intro Badge](https://img.shields.io/badge/Intro-151515)](#introduction) <sup> **•** </sup>
[![Run it Badge](https://img.shields.io/badge/Run_it-151515)](#how-to-run-it) <sup> **•** </sup>
[![Use it Badge](https://img.shields.io/badge/Use_it-151515)](#how-to-use-it)

</div>

### Introduction
This is a script created to aid with interactions on Android Emulator from Android Studio. This was created through necessity during my work in cybersecurity, as some tools used for Static Application Security Testing (SAST) and Dynamic Application Security Testing (DAST) use scripts that require access to a writable filesystem on Android, which in Android Studio's Emulator requires manually launching the emulator binary and manipulating it through ADB.

<div align="center">
  <img src=".assets/images/Help.png" alt="Demonstration of 'help' command" width="400" align="center"/>
  <img src=".assets/images/List.png" alt="Demonstration of 'list-avd' command" width="400" align="center"/>
</div>

> ###### Dependencies:
> For this script to run, it depends on a few programs: `adb`, `openssl` & `Android Studio`

### How to Run it
To run the script, give executable permission to the file and either run it at the current directory or put it at your user's `~/.local/bin` directory, to be run as a command.

```sh
cd android-emulator

chmod +x $(pwd)/android-emulator
cp $(pwd)/android-emulator ~/.local/bin/android-emulator

android-emulator help
```

###### Examples of the command syntax:
```sh
# Example of first boot of an image, so verification is turned off:
android-emulator Pixel_API_30 first-boot

# Example of installing a trusted root CA Certificate:
android-emulator Pixel_API_30 install-cert ~/cacert.pem
```

### How to Use it
This script relies on you creating an AVD from an Android image that does not have Google Play services, from Android Studio's VM Manager. After running the first-boot script, you will be in an Android environment with a writable system and root access.

Before being able to intercept requests with an intercepting proxy, you need to install your proxy's root CA Certificate. After that shut down the Android VM, so it can be launched with the parameters pointing to the proxy. From there, you are free to run external scripts to get a deeper insight on how an application runs and try to debug it.

<div align="center">

  [![Back to the Top Badge](https://custom-icon-badges.demolab.com/badge/Back_to_the_Top-151515?logo=chevron-up)](#title)

</div>
