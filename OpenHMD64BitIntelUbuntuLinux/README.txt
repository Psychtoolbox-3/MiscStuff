This is a prebuilt version of libopenhmd.so from the current
git master branch of https://github.com/OpenHMD/OpenHMD
at commit 1da57f3201d2e0fa50e30a29033bb4c94ed5afc3 (15-October-2019).

This library is meant for use on 64-Bit Intel compatible processor,
tested with 64-Bit Ubuntu Linux 18.04.3 LTS and 16.04.2 LTS, but might
work on other 64-Bit Linux distributions. You can always download and
build your own more up to date versions of libopenhmd.so from the
official repository at https://github.com/OpenHMD/OpenHMD

1. "sudo cp" Copy the file into /usr/local/lib/
2. Run "sudo ldconfig"
3. You will also need to "sudo apt-get install libhidapi-libusb0",
   as libopenhmd.so depends on HIDAPI's libusb backend.
4. UpdatePsychtoolbox to version 3.0.14 or later, from a date
   of 9-July-2017 or later. Make sure to run PsychLinuxConfiguration
   once, unless that happened automatically as part of DownloadPsychtoolbox,
   UpdatePsychtoolbox or SetupPsychtoolbox on Linux.
5. Your OpenHMD supported VR HMD should then work on your 64-Bit Intel
   compatible PC with a suitable 64-Bit Linux distribution.

libopenhmd is copyrighted by the OpenHMD contributors, and distributed
under the Boost-1.0 software license, as described in the LICENSE file.

This file will be deleted as soon as a sufficiently up-to-date version
of OpenHMD is available as a regular Debian package inside an up to date
version of Ubuntu Linux.

This folder also contains openhmdkeepalivedaemon. This executable needs to
be installed on your Linux system and started at system boot if you use a
HMD other than the Rift DK1 or Rift DK2. Otherwise the HMD will not get
detected by PTB and the X-Server properly and the VR rendering will not
display on the HMD, but on your regular displays, which is not what you
want. openhmdkeepalivedaemon is currently distributed under MIT license.

On system with systemd as service manager, you can setup openhmdkeepalivedaemon
to start automatically during system bootup by use of a systemd service definition
file. The following example was successfully tested on Ubuntu 16.04-LTS:

1. Copy openhmdkeepalivedaemon to /usr/local/bin/openhmdkeepalivedaemon
2. Copy openhmdkeepalive.service to /lib/systemd/system/openhmdkeepalive.service
3. systemctl enable openhmdkeepalive.service
4. This should work after the next system reboot, or immediately if you manually
   start the service via "systemctl start openhmdkeepalive"

You could always disable openhmdkeepalivedaemon again via:

systemctl disable openhmdkeepalive.service
