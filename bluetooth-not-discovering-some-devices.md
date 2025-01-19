# `bluetoothctl` fails to discover some devices

Issue first occured when I tried connecting the Lenovo ThinkPad Bluetooth Mouse
to this machine. The issue was that other devices were able to discover the mouse
in their bluetooth settings but for me `bluetoothctl` did not seem to see the mouse.

Turns out the bluetooth backend was misconfigured. Inside of `/etc/bluetooth/main.conf`
the controller mode was set to `bredr`. Setting it to `dual` resolved the issue

# Further questions

What are those bluetooth controller modes?

Turns out that Bluetooth works in 3 modes:
- basic rate/enhanced data rate configured inside  `/etc/bluetooth/main.conf` as (`bredr`)
- Low-Energy (LE) for some devices (`le`)
- Dual-mode (bredr or LE) (`dual`)

Seems like the ThinkPad mouse only operates in the `le` mode whereas my bluetooth
config was configured to only support `bredr` and that prevented `bluetoothctl`
from finding the mouse.
