# adbpy 
Python wrapper for [Android Debug Bridge](https://developer.android.com/studio/command-line/adb.html#directingcommands).

## Installation
```commandline
pip install adbpy
```

## Usage
### Simple Control
```python
from adbpy import adb
from adbpy.device import Device

devices = adb.get_devices()

device = Device(devices[0])
print(device.get_id())
print(device.get_screen_density())
device.tap_back()
device.tap(0, 0)
```
### Record Screen While Testing
```python
from adbpy import adb
from adbpy.device import Device
from threading import Thread
import os


def record_screen():
    device.record_screen(name="video", dst_path=cur_dir, time=10)


cur_dir = os.path.abspath(os.path.dirname(__file__))

devices = adb.get_devices()
device = Device(devices[0])
Thread(target=record_screen).start()

# Do your test 
device.tap(0, 0)
device.swipe(0, 0, 100, 100)
device.long_press(0, 0, 3000)
```

## Issues

## Todo

## Features To Add
* Add Some Intelligence

## License
[MIT License](LICENSE)