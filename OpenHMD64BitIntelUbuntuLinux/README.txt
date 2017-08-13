This is a prebuilt version of libopenhmd.so from the current
git master branch of https://github.com/OpenHMD/OpenHMD
at commit b443deb8d7fab39e3436dfc2e0438a8dfaee90d9 (13-August-2017).

This library is meant for use on 64-Bit Intel compatible processor,
tested with 64-Bit Ubuntu Linux 14.04.5 LTS and 16.04.2 LTS, but might
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
