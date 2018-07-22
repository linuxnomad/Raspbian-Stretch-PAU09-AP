# Raspbian Stretch PAU09 Panda Wireless Access Point
Modification of common configuration guides for using Raspberry Pi 3 hardware for creating an access point with the Panda Wireless PAU09

DISCLAIMER:I do not claim to be an expert in hostapd, dnsmasq, wpa_supplicant, or WiFi configurations. If I get something wrong please correct me and include documentation/explanation for me to understand the mistake.

The bulk of this configuration was obtained from roboberry at raspberryconnect.com.

http://www.raspberryconnect.com/network/item/330-raspberry-pi-auto-wifi-hotspot-switch-internet


Using the above configuration and the included hostapd.conf the PAU09 would not function correctly. All steps from the roboberry guide should be followed with the exception of the /etc/hostapd/hostapd.conf file. 


Other Guides that were used in reference:

https://elinux.org/RPI-Wireless-Hotspot

http://web.mit.edu/freebsd/head/contrib/wpa/hostapd/hostapd.conf


The main issues encountered dealt with the PAU09 not fully working with the common configurations. An Access Point could be configured but hostapd would fail with various errors pertaining to the rt2800usb driver.

https://www.raspberrypi.org/forums/viewtopic.php?t=209818

https://www.raspberrypi.org/forums/viewtopic.php?p=1296235


After various configuration testing the optimal options that allowed for the PAU09 to broadcast correctly and allow connectivity were:

Do not try to use the default rt2800usb driver in your conf file.

#driver=rt2800usb

hw_mode=g

wps_rf_bands=g
