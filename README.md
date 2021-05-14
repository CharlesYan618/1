<img width="128" height="128" src="https://i.imgur.com/MFgAUdY.png" alt="icon_square">

# Xposed-Disable-FLAG_SECURE

Xposed Module to Disable `FLAG_SECURE`, enabling screenshots and recording in apps that normally wouldn't allow it.

## [Downloads](https://github.com/VarunS2002/Xposed-Disable-FLAG_SECURE/releases/)

> [![APK: v2.0.0](https://img.shields.io/badge/APK-v2.0.0-brightgreen)](https://github.com/VarunS2002/Xposed-Disable-FLAG_SECURE/releases/download/2.0.0/Xposed-Disable-FLAG_SECURE_2.0.0.apk)
![Download-Count](https://img.shields.io/github/downloads/VarunS2002/Xposed-Disable-FLAG_SECURE/total?color=blue)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Module Repository Listings:

### [Xposed Repository](https://repo.xposed.info/module/com.varuns2002.disable_flag_secure)

### [LSPosed Repository](https://github.com/Xposed-Modules-Repo/com.varuns2002.disable_flag_secure)

## Requirements:

- Android 8.0+ (Oreo/SDK 26)

- Xposed implementation installed properly like [EdXposed](https://github.com/ElderDrivers/EdXposed/)
  and [LSPosed](https://github.com/LSPosed/LSPosed/)

- Untested but may work on Rootless Xposed implementations like [Tai Chi](https://github.com/taichi-framework/TaiChi/)

## Usage:

- EdXposed:
    - Normal Mode:
        - Enable the module and reboot
    - White List / Activation Scope Mode:
        - Enable the module
        - Select `Android System`
        - Select the target app in which you want to enable screenshots
        - Reboot
    - Black List Mode:
        - Enable the module
        - Do not select `Android System`
        - Do not select the target app in which you want to enable screenshots
        - Reboot
- LSPosed:
    - Enable the module
    - Select `System Framework`
    - Select the target app in which you want to enable screenshots
    - Reboot

## Note:

- This app does not prevent apps from detecting that you've taken a screenshot or recorded it like Snap or Instagram.
  This only enables it in apps that prohibit screenshots and recording. So don't screenshot your girlfriend's nudes.
  (You probably don't have one since you're reading this anyway)


- Xposed Implementations Tested on:
    - [EdXposed](https://github.com/ElderDrivers/EdXposed/)
    - [LSPosed](https://github.com/LSPosed/LSPosed/)


- Apps Tested on:
    - Amazon Prime Video (Screenshots and Screen Recording of Media)
    - Netflix (Screenshots and Screen Recording of Media) (read additional info below)
    - Telegram (Secret Chat & Disappearing Media)
    - Reddit (Anonymous Browsing Mode)
    - Google Chrome (Incognito Mode)
    - Brave Browser (Incognito Mode):
    - Disney+ (Screenshots and Screen Recording of Media) (read additional info below)

- This app is a fork of the existing apps but with better compatibility:
    - https://github.com/veeti/DisableFlagSecure/
    - https://github.com/LSPosed/DisableFlagSecure/
    - https://gitlab.com/azhao12345/disableflagsecure/


### Additional Info on DRM encrypted content (Disney+, Netflix)

When playing DRM encrypted content, most devices will use hardware decryption capabilites.
This hardware decrytion will push the video directly onto the screen, bypassing any screenshots/screenshare/recording functionality.

One possible solution is to disable this hardware decryption by installing the Magisk module [`liboemcrypto.so disabler`](https://github.com/Magisk-Modules-Repo/liboemcryptodisabler).
This will force the device to not use hardware decryption and in combination with this module will enable screenshots, screenshare and recording.

Installing this module might have unintended consequences, such as lowered video quality. Read more [here](https://forum.xda-developers.com/t/magisk-module-liboemcrypto-disabler-for-drm-protected-content-netflix-my5-etc.3794393).

In the end it's your choice whether to use it, but as it's systemless, testing it is recommended, as removing the module will revert back to the previous state.
