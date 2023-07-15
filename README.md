# Samsung-SSD-970-EVO-Plus-2B2QEXM7
Firmware update for Samsung SSD 970 EVO Plus compatible for installation with macOS

## Intro
In July 2023 I tried upgrading my early 2015 macbook air A1466 with a new NVME SSD Samsung 970 EVO Plus (using an adapter). According to the most web resources, replacement should be possible and this SSD is compatible with macOS if it has the latest firmware from Samsung.

## Problem
Referring to my own experience, in case your SSD manufacturing date has to be before 2020, then it is very likely that your Samsung 970 EVO Plus does not have a firmware compatible with macOS.

If this is true, then the formatting of SSD to AFPS with GUID partition map fails and restarts the MacBook. Restarting occurs at the stage of “Mounting AFPS volume”.

This is a sure sign that you need to update the firmware on your SSD.

However, there is a big caveat: the latest firmware on Samsung’s website (as of July 2023) does recognize the installed SSD. So in case you have already created a EFI boot USB with this firmware (4B2QEXM7), then it will not detect the installed SSD during EFI boot process so you won’t be able to update the firmware!

After trial and error, I discovered that firmware version 2B2QEXM7 is compatible with macOS and detects installed Samsung SSD during the EFI boot process. But it is no longer available on the Samsung’s official website.

## Solution

In case you are facing an issue described above, then you can download the legacy firmware (2B2QEXM7), which is attached as a release to this repository.

After downloading the ISO file, please download a tool for creating EFI boot USB (e.g. Balena Etcher), then follow instructions for that tool and after creating the EFI boot USB, install it into your MacBook. Power your MacBook on and after hearing the chime press and hold “Option” key until you see a loader on the screen. In my case I also had plugged in a macOS bootable USB with Big Sur, so I was presented with 2 options: to load from macOS bootable USB or to load from EFI boot USB.

Please select loading from EFI boot USB, then follow instructions from Samsung on the screen to update your SSD to the compatible version. Once the update is complete, the MacBook will restart.

After restarting select to load from macOS bootable USB, then proceed to format Samsung 970 EVO Plus SSD as AFPS with GUID partition map, and formatting should complete without any errors or failures.
Then proceed to install the macOS to your new SSD.

### Please star this repository if it helped you. That way I have a sign that this helped someone else to save time and efforts 🙂
