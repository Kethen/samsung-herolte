### Credits
https://github.com/8890q/ for LineageOS 18.1 device tree, kernel, hardware support, blobs

https://forum.xda-developers.com/t/treble-aosp-g930x-g935x-project_pizza-trebleport-v2-0.3956076/ for libsensor blobs

https://github.com/NotKit for giving me very helpful hints about ubports/halium specifics

these awesome people gave me useful pointers for https://github.com/Kethen/herolte_treble to come to fruition, and is used in this port:

https://github.com/ivanmeler

https://github.com/ExpressLuke

https://github.com/00p513-dev


### Currently Known Issues
- while bluebinder + 3.18 bt stack has issues, bluetooth seems to work best with the 4.2 bluetooh stack, however:
	- full power off has to be disabled for it to play well with the uart hci, hopefully the wifi chip itself takes the power down command well
	- hciattach can't set a macaddress at all with this chip, so the macaddress from /efs cannot be applied, while the chip has a built-in mac address
- swlan0 is disabled to not confuse NetworkManager, but that means no wifi tethering while wifi is connected, wlan0 is used to do both
- fingetprint sensor should work, but only tested on /dev/vfsspi(viper), not /dev/esfp0(egis), I don't have a s7 with egis fingerprint sensor to test with
- camcorder audio desync, likely an issue that should be fixed on ubport itself however, https://gitlab.com/ubports/development/core/qtubuntu-camera/-/issues/22

### Pending merge requests included
- Color/Pixel format for hardware video decoding  https://github.com/ubports/gst-plugins-bad-packaging/pull/4
- Pulse audio https://github.com/ubports/pulseaudio-modules-droid-30/pull/1
- Sensorfw https://gitlab.com/ubports/development/core/packaging/sensorfw/-/merge_requests/8
- halium-generic-adaptation-build-tools https://gitlab.com/ubports/porting/community-ports/halium-generic-adaptation-build-tools/-/merge_requests/2

### TODO
