
Get [`adb`](https://developer.android.com/studio/command-line/adb) and [`fastboot`](https://android.googlesource.com/platform/system/core/+/master/fastboot/#fastboot)
from the [platform-tools](https://developer.android.com/studio/releases/platform-tools)

[Using ADB and fastboot](https://wiki.lineageos.org/adb_fastboot_guide)

Check connection to phone, `adb devices`. USB debug must be enabled and then authorized on phone.

```
# Enable USB debugging on phone
# Connect phone via USB
adb devices  # Verify connection
# Authorize on phone
adb reboot bootloader
fastboot devices  # Verify connection (may require to run as root)
fastboot flashing unlock
fastboot flash boot <recovery_filename>.img  # Flash w/ temporary recovery image
fastboot reboot recovery   # Not all phones support booting into recovery mode from fastboot
adb sideload filename.zip
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgyMjU2Njg5NSwxNTk0NTU5NTcxLDE0MD
UzMzQxMzgsLTE1MTk5NDgwNTJdfQ==
-->