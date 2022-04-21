
Get [`adb`](https://developer.android.com/studio/command-line/adb) and [`fastboot`](https://android.googlesource.com/platform/system/core/+/master/fastboot/#fastboot)
from the [platform-tools](https://developer.android.com/studio/releases/platform-tools)

[Using ADB and fastboot](https://wiki.lineageos.org/adb_fastboot_guide)

Check connection to phone, `adb devices`. USB debug must be enabled and then authorized on phone.

```
# Enable USB debugging on phone
# Connect phone via USB
adb devices
# Authorize on phone
adb reboot bootloader
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQyMjg5MjQ0NCwtMTUxOTk0ODA1Ml19
-->