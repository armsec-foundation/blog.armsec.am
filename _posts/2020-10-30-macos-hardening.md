---
layout: post
title: General Mac OS Security Configurations
---

### Spotlight

* Go to `System Preferences > Spotlight`
* Unselect `Allow Spotlight Suggestions in Look up`


### Passwords

* Go to `System Preferences > Security & Privacy > General tab`
* Select `Require password immediately after sleep or screen saver begins`

* Go to `System Preferences > Security & Privacy > General tab > Advanced`
* Select `Require an administrator password to access system-wide preferences`

### File Vault

* Go to `System Preferences > Security & Privacy > FileVault tab`
* Select `Turn On FileVault`

[FileVault](https://en.wikipedia.org/wiki/FileVault) provides full disk
(technically, full volume) encryption on macOS. FileVault encryption protects
data at rest and hardens (but not always prevents) someone with physical access
from stealing data or tampering with your Mac.

### Firewall

* Go to `System Preferences > Security & Privacy > Firewall tab`
* Select `Turn On Firewall`
* Then select `Firewall Options…`, and ensure these three tick boxes are checked:
  * Built-in, basic firewall which blocks incoming connections only.

### Privacy

* Go to `System Preferences > Security & Privacy > Privacy tab`
* Look for the Advertising selection, then unselect Limit Ad Tracking

* Go to `System Preferences > Security & Privacy > Privacy tab`
* Look for the `Analytics & Improvements selection`,
  then unselect `Share Mac Analytics` & `Improve Siri & Dictation`

* Go to `System Preferences > Security & Privacy > Privacy tab`
* Review the selections and remove any other apps you don’t want to
  have access to your disk.

* Go to `System Preferences > Security & Privacy > Privacy tab`
* Select `Location Services`, then unselect Applications that don’t
  need to use your Location

### Software Updates

* Go to `System Preferences > Software Update`
* Check you’re on the latest version of macOS, then select
  `Automatically keep my Mac up-to-date`.
* Select Advanced, and check all of the tick boxes under `Automatically:`

### DNS Configuration

* Go to `System Preferences > Network > Advanced > DNS tab`
* Ensure `DNS Servers` contains DNS servers for OpenDNS:
  - 1.1.1.1
  - 8.8.8.8
  - 208.67.220.220
  - 208.67.222.222
* Remove any other addresses.

### Bluetooth

* Go to `System Preferences > Bluetooth`
* Click `Turn Bluetooth Off` when not in use.
* To make Bluetooth on/off switching faster, put Bluetooth icon on Menu Bar
  * Go to `System Preferences > Bluetooth > Show Bluetooth in menu bar`.

### Sharing

* Go to `System Preferences > Sharing`
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

* Go to `System Preferences > Sharing`
* Change your Computer Name to something that isn’t directly identifiable.

### Wake on WiFi

* Go to `System Preferences > Energy Saver > Power Adapter tab`
* Unselect Wake for Wi-Fi network access.

### Date & Time

* Go to `System Preferences > Date & Time > Time Zone tab`
* Select `Set time zone automatically using current location`

### Backup

* Go to `System Preferences > Time Machine`
* Recommend turning on `Back Up Automatically` if in possession of an external
  drive.

### iCloud

* Go to `System Preferences > Apple ID`
* If you’re using iCloud, ensure that you’ve configured two-step verification.
  Here’s [Apple’s official help article](https://support.apple.com/en-nz/HT204152).

### System Integration

By Default in New mac os versions it is enabled and will protect System files
If the OS is El Capitan and later, make sure system integrity protection is on.
Terminal command: csrutil status
SIP: https://support.apple.com/en-us/HT204899

* Go to `System Preferences > Security & Privacy > General tab`
* Recommend turning on Allow apps downloaded from: App Store

### Firmware Password

**IMPORTANT!** make sure you remember password

Setting a firmware password prevents a Mac from starting up from any device
other than the startup disk. It may also be set to be required on each boot.
This may be useful for mitigating some attacks which require physical access to
hardware.

* Make sure your Mac is powered off then turn it on.
* Activate Recovery Mode by immediately holding down the Command and R keys.
* Wait until the OS X Utilities screen appears.
* Click on the Utilities menu from the menu bar.
* Select Firmware Password Utility.
* Click on the Turn On Firmware Password...
* Enter a new password, verify it and click the Set Password button.
* Click on Quit Firmware Password Utility
* Click on the menu.
* Select Restart.

### Do not use a user with administrative privileges

Create standard users for general usage. Use administrator user when you
require admin privileges.

### Disable auto login functional from mac os

Go to `System Preferences > Users & Groups > Press Login Options > From Automatic login drop down menu > Off`

### Useful Tools

NIST developed scripts handling different aspects of macOS
configuration parameters: https://github.com/usnistgov/applesec
My suggestion is to use it as a source for our version!
See the draft document (4).


Resources:
* https://github.com/drduh/macOS-Security-and-Privacy-Guide#firewall
* https://medium.com/macoclock/macos-catalina-hardening-quick-tips-7288d7acf09d
* https://github.com/0xmachos/mOSL
* [Guide to Securing macOS 10.12 4 Systems for IT Professionals](https://csrc.nist.gov/CSRC/media/Publications/sp/800-179/rev-1/draft/documents/sp800-179r1-draft.pdf)


Third party tools for security: https://objective-see.com/products.html
NOTE: Do not install Lulu firewall, it has a lot of bugs and can cause a lot of
problems.

ReiKey tool: Malware and other applications may install persistent keyboard
"event taps" to intercept your keystrokes. ReiKey can scan, detect, and monitor
for such taps.
