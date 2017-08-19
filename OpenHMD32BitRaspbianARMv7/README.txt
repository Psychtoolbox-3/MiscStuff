This is a prebuilt version of libopenhmd.so from the current
git master branch of https://github.com/OpenHMD/OpenHMD
at commit b443deb8d7fab39e3436dfc2e0438a8dfaee90d9 (13-August-2017).

This library is meant for use on the RaspberryPi with
Raspbian, so it is compiled for 32-Bit ARMv7 architecture.

1. "sudo cp" Copy the file into /usr/local/lib/
2. Run "sudo ldconfig"
3. You will also need to "sudo apt-get install libhidapi-libusb0",
   as libopenhmd.so depends on HIDAPI's libusb backend.
4. UpdatePsychtoolbox to version 3.0.14 or later, from a date
   of 9-July-2017 or later. Make sure to run PsychLinuxConfiguration
   once, unless that happened automatically as part of DownloadPsychtoolbox,
   UpdatePsychtoolbox or SetupPsychtoolbox on Linux.
5. Your OpenHMD supported VR HMD should then work on the RaspberryPi
   or compatible devices.

libopenhmd is copyrighted by the OpenHMD contributors, and distributed
under the Boost-1.0 software license, as described in the LICENSE file.

This file will be deleted as soon as a sufficiently up-to-date version
of OpenHMD is available as a regular Debian package inside an up to date
version of Raspbian.

This folder also contains openhmdkeepalivedaemon. This executable needs to
be installed on your Linux system and started at system boot if you use a
HMD other than the Rift DK1 or Rift DK2. Otherwise the HMD will not get
detected by PTB and the X-Server properly and the VR rendering will not
display on the HMD, but on your regular displays, which is not what you
want. openhmdkeepalivedaemon is currently distributed under MIT license.
