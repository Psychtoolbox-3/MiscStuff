This is libopenhmd.so which is a mildly hacked version - only disabling some
annoying debug messages, of the current experimental rift-kalman-filter branch from
https://github.com/thaytan/OpenHMD.git

It corresponds to commit 37933ded21f33e530534ad8a43da439370944de7 from that repo.

This version has experimental support for using the Oculus CV1 sensors to
track the position and orientation of the Oculus Rift CV1 and the 1st gen
Oculus touch controllers. It also has support for linear and angular velocity
and acceleration reporting, and for enabling haptic feedback on the Oculus
touch controllers.

This is not yet merged upstream in OpenHMD public repo, but it is working
well enough for all my needs on Linux atm., so others should be able to
benefit from it as well.

This library is meant for use on 64-Bit Intel compatible processors, this
build is tested with 64-Bit Ubuntu Linux 20.04.3 LTS, but might work on
other 64-Bit Linux distributions. You can always download and build your
own more up to date versions of libopenhmd.so from the official repository
at https://github.com/OpenHMD/OpenHMD

1. "sudo cp" Copy the file into /usr/local/lib/
2. Run "sudo ldconfig"
3. You will also need to "sudo apt-get install libhidapi-libusb0",
   as libopenhmd.so depends on HIDAPI's libusb backend.
4. UpdatePsychtoolbox to version 3.0.17 or later, from a date
   of 1-August-2021 or later. Make sure to run PsychLinuxConfiguration
   once, unless that happened automatically as part of DownloadPsychtoolbox,
   UpdatePsychtoolbox or SetupPsychtoolbox on Linux.
5. Your OpenHMD supported VR HMD should then work on your 64-Bit Intel
   compatible PC with a suitable 64-Bit Linux distribution.

libopenhmd is copyrighted by the OpenHMD contributors, and distributed
under the Boost-1.0 software license, as described in the LICENSE file.

This file will be deleted as soon as a sufficiently up-to-date version
of OpenHMD is available as a regular Debian package inside an up to date
version of Ubuntu Linux. Please note that Ubuntu 20.04 LTS does ship with
OpenHMD version 0.3.0, the most recent stable public release. The difference
to the libopenhmd.so provided here is the added experimental support for
tracking of the Oculus Rift CV1 and its touch controllers, and haptic
feedback support via the touch controllers.

The following is not needed anymore on modern Linux distributions. Instead
you should install the custom xorg.conf file bundled with Psychtoolbox 3.0.17
to setup a dual-X-Screen configuration with X-Screen 1 assigned to the HMD.

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
