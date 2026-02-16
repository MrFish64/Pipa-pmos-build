# 🧪 postmarketOS for Xiaomi Pad 6 (pipa)
<img alt="Image" src="https://github.com/user-attachments/assets/3da15b14-b144-4315-bfeb-2e28cef0d18e" />

  Custom postmarketOS builds for Xiaomi Pad 6 (codename: pipa)</em></p>
</div>

---

[![Platform](https:&#47;&#47;img.shields.io&#47;badge&#47;Platform-Xiaomi%20Pad%206-blue.svg)](https:&#47;&#47;github.com&#47;MrFish64&#47;Pipa-pmos-build)
[![OS](https:&#47;&#47;img.shields.io&#47;badge&#47;OS-postmarketOS-orange.svg)](https:&#47;&#47;postmarketos.org)
[![License](https:&#47;&#47;img.shields.io&#47;badge&#47;License-MIT-green.svg)](https:&#47;&#47;github.com&#47;MrFish64&#47;Pipa-pmos-build&#47;blob&#47;main&#47;LICENSE)

## 📊 Hardware Status (Xiaomi Pad 6)

| Component | Status | Details |
| :--- | :--- | :--- |
| **Display** | ✅ Supported | 
| **GPU** | ✅ Supported |
| **Touchscreen** | ✅ Supported |
| **Wi-Fi / BT** | ✅ Supported | 
| **Audio** | ⚠️ Partial | 
| **Battery** | ✅ Supported | 
| **USB-C** | ✅ Supported | 



## 🌟 Features 

- **Supported Desktop Environments**  
  * KDE Plasma Desktop  

- **Automated Builds**  
  ✅ Builds every day (UTC)  
  ✅ Kernel packages included  
  ✅ Verified device support

---

## 🔐 Login Credentials

Default System Credentials
  
- **Username:** `user`  
- **Password:** `147147` (for initial setup)


---

## 📦 Downloading Images

GitHub Actions Artifacts
  
1. Visit our [Actions tab](https://github.com/MrFish64/Pipa-pmos-build/actions)   
2. Look for the latest workflow run (marked with 🟢)  
3. Download the zip archive  
*Note:* GitHub account required for downloads

---

## 🛠️ Getting Started

1. **Download** your preferred image from the Actions tab  
2. **Extract** the ZIP archive  
3. **Flash Singleboot(only Linux)**
```bash
fastboot erase dtbo_a
fastboot erase dtbo_b
fastboot flash boot_a boot-xiaomi-pipa.img
fastboot flash boot_b boot-xiaomi-pipa.img
fastboot flash userdata rootfs-xiaomi-pipa-plasma.img
```
**Flash Dualboot (Android and Linux)**
```bash
First flash the correct fastboot rom wia fastboot (wipe the storage and Do not lock the bootloader)

boot once to check if android works fine

reboot to boot loader and run 

fastboot set_active b
fastboot erase dtbo

then temperately install pmos with
fastboot flash boot <path to boot.img>
sudo fastboot flash super <path to the larger .img>
reboot to pmos with 
sudo fastboot reboot
after booting up , 
login (password is 147147)
connect to wifi
open terminal and run
sudo apk update
sudo apk add gparted
let it finish , then open gparted from app drawer

select the storage and the last partition should have name "userdata"

right click and delete userdata , make sure to only delete it and no other partition

it should say something like "free space" or "unallocated"

next , right click on it and create new partition and label it as "userdata" with some space subtracted for your linux. (keep it ext4)

next click on the remaining space and label it as "linux" (keep it ext4)

apply changes and verify them by opening and closing gparted 

finally poweroff your tablet and hold volume keys to put it in fast boot mode

flash the fastboot rom again (flash_all.bat , wipe userdata too, don't lock the bootloader)
turn on android and there should be some storage gone , reserved as "system"

reboot back to bootloader 

run                              fastboot set_active b
fastboot erase dtbo
then permanently install pmos with
fastboot flash boot <path to boot.img>
fastboot flash linux <path to the larger .img>
reboot to pmos with 
fastboot reboot
congratulations you have successfully setup dualboot

to go from pmos to android , type in terminal 
sudo qbootctl -s a
and for android to pmos , use switch my slot , (available on fdroid , requires magisk root and a module linked on its github page  )

otherwise you can always switch from fastboot with 

<for android>
fastboot set_active a

<for pmos>
fastboot set_active b

4. **Reboot**
5. **Enjoy** postmarketOS on your Xiaomi Pad 6!
```

---

## 📅 Build Schedule

| Job | Frequency | Status |
| :--- | :--- | :--- |
| Image Build | Every Day | ![Build Status](../../actions/workflows/Build.yml/badge.svg?branch=main) |


---
---

## 🤝 Credits
- [postmarketOS Team](https:&#47;&#47;postmarketos.org) for the amazing base.
- [Maport Maintainers](https:&#47;&#47;gitlab.postmarketos.org&#47;postmarketOS&#47;pmaports) for the pipa port.
- All contributors and testers from the Xiaomi Pad 6 community.


## ❓ Troubleshooting

Check out our [Troubleshooting Guide][WIKI] for common issues, touchscreen fixes, and bootloop solutions.

[WIKI]: https:&#47;&#47;github.com&#47;MrFish64&#47;Pipa-pmos-build&#47;wiki&#47;Troubleshooting


> 🚀 *postmarketOS: A long-lasting, touch-optimized Linux distribution for mobile devices*

[postmarketOS Website](https://postmarketos.org/)  | [Documentation](https://wiki.postmarketos.org/) 
