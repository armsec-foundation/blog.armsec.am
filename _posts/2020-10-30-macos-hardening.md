---
layout: post
title: General Mac OS Security Configurations
description: In this post we've aggregated all the necessary configurations \
  one needs to harden his/her MacOS based machine.
---

In this post we've aggregated all the necessary configurations one needs to
harden his/her MacOS based machine.


## Spotlight

* Go to **System Preferences** ‣ **Spotlight**.
* Unselect **Allow Spotlight Suggestions in Look up**.

![Spotlight](/assets/images/2020-10-30/001-spotlight.png)


## Security & Privacy

### General

* Go to **System Preferences** ‣ **Security & Privacy** ‣ **General** tab.
* Select **Require password immediately after sleep or screen saver begins**.

It is also recommended not to install applications outside of the AppStore.

* Select **App Store** at **Allow apps downloaded from:**

![Security & Privacy ‣ General](/assets/images/2020-10-30/002-privacy-general.png)

* Go to **System Preferences ‣ Security & Privacy ‣ General** tab.
* Click on **Advanced** button to open additional settings.
* Select **Require an administrator password to access system-wide preferences**.

![Security & Privacy ‣ General](/assets/images/2020-10-30/003-privacy-general-advanced.png)


### FileVault

[FileVault](https://en.wikipedia.org/wiki/FileVault) provides full disk
(technically, full volume) encryption on macOS. FileVault encryption protects
data at rest and hardens (but not always prevents) someone with physical access
from stealing data or tampering with your Mac.

* Go to **System Preferences ‣ Security & Privacy ‣ FileVault** tab.
* Select **Turn On FileVault**.

![FileVault](/assets/images/2020-10-30/004-filevault.png)


### Firewall

* Go to **System Preferences ‣ Security & Privacy ‣ Firewall** tab.
* Select **Turn On Firewall**.
* Then select **Firewall Options…**, and ensure all check boxes are checked.

![Firewall](/assets/images/2020-10-30/005-firewall.png)


### Privacy

* Go to **System Preferences ‣ Security & Privacy ‣ Privacy** tab.
* Look for the **Advertising** section, then unselect **Limit Ad Tracking**.

![Advertising](/assets/images/2020-10-30/006-advertising.png)


* Look for the **Analytics & Improvements** section,
  then unselect **Share Mac Analytics** & **Improve Siri & Dictation**.

![Analytics & Improvements](/assets/images/2020-10-30/007-analytics.png)


* Look for **Full Disk Access**.
* Review the selections and remove any other applications you don’t want to
  have access to your disk.

![Full Disk Access](/assets/images/2020-10-30/008-fulldisk-access.png)


* Select **Location Services**, then unselect applications that don’t
  need to use your Location.

![Location Services](/assets/images/2020-10-30/009-location-services.png)



## Software Updates

* Go to **System Preferences ‣ Software Update**
* Check that you’re on the latest version of macOS, update to latest
  version if needed and select **Automatically keep my Mac up-to-date**.

![Software Update](/assets/images/2020-10-30/010-autoupdate.png)

* Select Advanced, and check all of the check boxes under **Automatically:**

![Advanced Update Settings](/assets/images/2020-10-30/011-update-advanced.png)



## DNS Configuration

* Go to **System Preferences ‣ Network ‣ Advanced ‣ DNS** tab.
* Ensure **DNS Servers** are configured to use CloudFlare, Google and OpenDNS:
  - 1.1.1.1
  - 8.8.8.8
  - 208.67.220.220
  - 208.67.222.222
* Remove any other addresses.

![DNS](/assets/images/2020-10-30/012-dns.png)


## Bluetooth

* Go to **System Preferences ‣ Bluetooth**
* Click **Turn Bluetooth Off** when not in use.
* To make Bluetooth on/off switching faster, enable Bluetooth icon on Menu Bar
  * Check the **Show Bluetooth in menu bar** checkbox.

![Bluetooth](/assets/images/2020-10-30/013-bluetooth.png)


## Sharing

* Go to **System Preferences ‣ Sharing**
* Ensure all of the services below are unchecked:
  * Screen Sharing
  * File Sharing
  * Media Sharing
  * Printer Sharing
  * Remote Login
  * Remote Management
  * Remote Apple Events
  * Bluetooth Sharing
  * Internet Sharing
  * Content Caching
* Change your Computer Name to something that isn’t directly identifiable.

![Sharing](/assets/images/2020-10-30/014-sharing.png)


## Wake on WiFi

* Go to **System Preferences ‣ Energy Saver ‣ Power Adapter** tab
* Unselect Wake for Wi-Fi network access.

![Wake on WiFi](/assets/images/2020-10-30/015-wake-on-wifi.png)


## Date & Time

* Go to **System Preferences ‣ Date & Time ‣ Time Zone** tab
* Select **Set time zone automatically using current location**

![Time Zone](/assets/images/2020-10-30/016-time-zone.png)


## Backup

* Go to **System Preferences ‣ Time Machine**
* Recommend turning on **Back Up Automatically** if in possession of an external
  drive.


## iCloud

* Go to **System Preferences ‣ Apple ID**
* If you’re using iCloud, ensure that you’ve configured two-step verification.
  Check out the [Apple’s official guide](https://support.apple.com/en-nz/HT204152)
  to enable 2FA.


## Do not use a user with administrative privileges

Create standard user for general usage. Use administrator user when you require
administrative privileges.

![Standard User](/assets/images/2020-10-30/018-standard-user.png)


## Disable Auto Login

* Go to **System Preferences ‣ Users & Groups**
* Press **Login Options**
* Select **Off** in the **Automatic login** drop down menu

![Automatic login](/assets/images/2020-10-30/019-autologin.png)


## System Integration

Make sure the system integrity protection is on (available on El Capitan and
later). Run the following command in the Terminal app.

```
csrutil status
```

![SIP](/assets/images/2020-10-30/017-sip-check.png)

More details are available [here](https://support.apple.com/en-us/HT204899).


## Firmware Password

**IMPORTANT!** When firmware password is forgotten, the only way to recover is
to bring your mac to an official Apple Store or Apple Certified Service
Provider.

Setting a firmware password prevents a Mac from starting up from any device
other than the startup disk. It may also be set to be required on each boot.
This may be useful for mitigating some attacks which require physical access to
hardware. See the official Apple's instructions
[here](https://support.apple.com/en-am/HT204455).


## Resources and Tools

* NIST developed scripts that handle different aspects of macOS configuration
  parameters. It is available open source on
  [GitHub](https://github.com/usnistgov/applesec).
* [GitHub drduh/macOS-Security-and-Privacy-Guide](https://github.com/drduh/macOS-Security-and-Privacy-Guide)
* [https://medium.com/macoclock/macos-catalina-hardening-quick-tips-7288d7acf09d](https://medium.com/macoclock/macos-catalina-hardening-quick-tips-7288d7acf09d)
* [GitHub 0xmachos/mOSL](https://github.com/0xmachos/mOSL)
* [Guide to Securing macOS 10.12 4 Systems for IT Professionals](https://csrc.nist.gov/CSRC/media/Publications/sp/800-179/rev-1/draft/documents/sp800-179r1-draft.pdf)
* [Third party tools for security](https://objective-see.com/products.html).
    * Do not install Lulu firewall, it has a lot of bugs and can cause a lot
      of problems.
    * ReiKey tool: Malware and other applications can install persistent keyboard
      "event taps" to intercept your keystrokes. ReiKey can scan, detect, and
      monitor for such taps.
