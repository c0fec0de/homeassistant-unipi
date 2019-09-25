# Installation

[Home Assistant] supports various installation methods. [EVOK] requires [raspbian](https://www.raspberrypi.org/downloads/raspbian/).

## 1. Create SD-Card Install Raspbian without Desktop

The Raspbian Lite installation is sufficient.

Download [Raspbian Buster Lite](https://downloads.raspberrypi.org/raspbian_lite_latest) and 
[write it to an SD-Card](https://www.raspberrypi.org/documentation/installation/installing-images/README.md).

On Linux
```bash
# Insert SD-Card in your computer
# Lookup your SD-Card Device
lsblk
# Unzip the Image
unzip 2019-07-10-raspbian-buster-lite.zip
# Write the Image to the SD-Card (Replace mmcblkX with the corresponding number for lsblk)
sudo dd bs=4M if=2019-07-10-raspbian-buster-lite.img of=/dev/mmcblkX status=progress conv=fsync
sync
# Remove SD-Card from your computer
```

## 2. Raspbian Setup

* Insert the SD-Card into your UniPi.
* Connect a keyboard and monitor (remove protector on the right side of the device).
* Connect the UniPi to your LAN (assuming you have a DHCP-Server running)
* Power the UniPi (the first boot might take a little bit longer)
* Login to the device (Note: keyboard layout is "UK default"):
```
raspberrypi login: pi
Password: raspberry
```
* Update
```bash
sudo apt update -y
sudo apt upgrade -y
```

* Configure
```bash
sudo raspi-config

# Goto "4 Localisation Options" ==> "I2 Change Timezone"
# Goto "4 Localisation Options" ==> "I3 Change Keyboard Layout"
# Goto "5 Interfacing Options" ==> "P2 SSH" ==> "Yes"
# <FINISH>
```

* Reboot and re-login
```bash
sudo reboot
# Rebooting
raspberrypi login: pi
Password: raspberry
```

* Change password
```bash
passwd
```

* Determine UniPi's IP address

```bash
ifconfig
# See eth0 and inet for something like 192.168.X.Y
```

* Configure a Static-IP (optional)

Please see [How to Set A Static IP Address on Debian 10 Buster](https://linuxconfig.org/how-to-set-a-static-ip-address-on-debian-10-buster)

* Login via SSH

Use putty or a ssh-client:
```
ssh pi@192.168.X.Y
```

If you successfully connected via SSH, the keyboard and monitor are not needed anymore.
Its up to you, to continue via SSH or keyboard and monitor.


## 3. Install EVOK

Follow the [EVOK] installation instructions (just copy-paste these lines to the UniPi console):

```bash
sudo echo "deb https://repo.unipi.technology/debian stretch main" > /etc/apt/sources.list.d/unipi.list
wget https://repo.unipi.technology/debian/unipi_pub.gpg -O - | sudo apt-key add
sudo apt update -y
sudo apt-get install nginx -y
sudo rm -f /etc/nginx/sites-enabled/default
sudo apt-get install evok -y
sudo systemctl enable evok
```

Check that evok got started properly
```bash
sudo systemctl status evok | grep Active
# Should return something like
# Active: active (running) since ...
```

Reboot
```bash
sudo reboot
# re-login
```

## 4. Check EVOK Installation

Open the following http://192.168.X.Y in your browser.
You can check input states and toggle outputs.

-----

[Home Assistant]:https://www.home-assistant.io
[EVOK]:https://github.com/UniPiTechnology/evok