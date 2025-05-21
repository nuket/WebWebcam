# WebWebcam

Preview webcam output and control exposure settings using a modern browser.

## Rationale (🤦🏻‍♂️)

I wrote this because Microsoft's Camera App is a nightmare on Corporate PCs and
I wasted about an hour with a colleague trying to install it on a locked-down
Windows machine.

We couldn't install the Camera App because we didn't have admin rights and the Windows
Store wasn't available.

We couldn't access the already-installed Camera App executable, because it's hidden
behind admin rights in `C:\Program Files\WindowsApps`.

```
C:\Program Files>dir /ah
 Volume in drive C has no label.
 Volume Serial Number is 5459-FD64

 Directory of C:\Program Files

05/16/2025  05:01 PM    <DIR>          ..
04/01/2024  09:24 AM               174 desktop.ini
11/13/2023  04:06 PM    <DIR>          Uninstall Information
04/01/2024  09:34 AM    <DIR>          Windows Sidebar
05/19/2025  02:44 PM    <DIR>          WindowsApps
               1 File(s)            174 bytes
               4 Dir(s)  278,822,080,512 bytes free

C:\Program Files>cd WindowsApps
Access is denied.
```

I love it when an Operating System tells me that and hides things from me.

Downloading the `Windows Camera Installer.exe` and then running it would take us
back into either Internet Exploder (like I said, a corporate PC) or would simply
open the Windows App Store webpage in Microsoft Edge.

i.e. they made a 1MB executable do what an old `.url` shortcut would do. But hey,
at least the executable is signed, right?

Totally, completely, idiotic.

## Settings

Example from my system:

```json
{
    "aspectRatio": {
        "max": 2560,
        "min": 0.0006944444444444445
    },
    "brightness": {
        "max": 255,
        "min": 0,
        "step": 1
    },
    "colorTemperature": {
        "max": 6500,
        "min": 2800,
        "step": 10
    },
    "contrast": {
        "max": 100,
        "min": 0,
        "step": 1
    },
    "exposureMode": [
        "continuous",
        "manual"
    ],
    "exposureTime": {
        "max": 1250,
        "min": 2.44140625,
        "step": 2.44140625
    },
    "facingMode": [
        "user"
    ],
    "frameRate": {
        "max": 30,
        "min": 0
    },
    "height": {
        "max": 1440,
        "min": 1
    },
    "resizeMode": [
        "none",
        "crop-and-scale"
    ],
    "saturation": {
        "max": 100,
        "min": 0,
        "step": 1
    },
    "sharpness": {
        "max": 7,
        "min": 0,
        "step": 1
    },
    "whiteBalanceMode": [
        "continuous",
        "manual"
    ],
    "width": {
        "max": 2560,
        "min": 1
    }
}
```

## Refs

I used a combination of the following tutorials and help sites:

* https://www.geeksforgeeks.org/how-to-integrate-webcam-using-javascript-on-html5/
* https://googlechrome.github.io/samples/image-capture/update-camera-zoom.html
* https://webrtc.github.io/samples/src/content/getusermedia/exposure/
* https://github.com/webrtc/samples/blob/gh-pages/src/content/getusermedia/exposure/js/main.js

Long may their links remain alive.
