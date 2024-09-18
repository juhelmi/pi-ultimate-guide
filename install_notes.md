

IP was seen in my case with:
```
ping raspberrypi
```

### HW setup notes

I2C enable

```
sudo raspi-config 
```

Find interface options and from there enable I2C. Reboot for new HW options.


### Other settings
Display 4K enabled
Overlay filesystem was enabled (later disabled as RAM disk was not enough big for apt upgrade)

### RealVNC install to Ubuntu
sudo apt install ~/Lataukset/VNC-Viewer-7.12.1-Linux-x64.deb

### Use of overlay filesystem
sudo apt upgrade
sudo apt dist-update

sudo reboot (for good measure)

Click on the Menu -> Preferences -> Raspberry Pi Configuration -> Performance -> Overlay file system -> Configure...

Da Dah...

Zero writes to your SD card!

Command: "sudo apt upgrade" fills overlay and for that it was dropped out.

Source: https://forums.raspberrypi.com/viewtopic.php?f=63&t=253104&p=1549229#p1549117

### GNOME system monitor
https://snapcraft.io/install/gnome-system-monitor/raspbian

### Http server
Note that SimpleHTTPServer is renamed to http.server

$python3 -m SimpleHTTPServer
/usr/bin/python3: No module named SimpleHTTPServer
juha@raspberrypi:~/Downloads/webserver $ python3 -m http.server