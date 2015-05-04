# HW4
1. Installed pyOCD
2. Installed pyinstaller
3. Created gdb_server file from post installation instructions
4. Attempted to run basic_test.py python script but encountered the following error

    user@ubuntu:/mnt/hgfs/mbed/pyOCD-master/test$ python basic_test.py 
Traceback (most recent call last):
  File "basic_test.py", line 48, in <module>
    board = MbedBoard.chooseBoard()
  File "/mnt/hgfs/mbed/pyOCD-master/pyOCD/board/mbed_board.py", line 150, in chooseBoard
    all_mbeds = MbedBoard.getAllConnectedBoards(transport, False, blocking, target_override)
  File "/mnt/hgfs/mbed/pyOCD-master/pyOCD/board/mbed_board.py", line 104, in getAllConnectedBoards
    all_mbeds = INTERFACE[usb_backend].getAllConnectedInterface(mbed_vid, mbed_pid)
  File "/mnt/hgfs/mbed/pyOCD-master/pyOCD/interface/pyusb_backend.py", line 71, in getAllConnectedInterface
    config = board.get_active_configuration()
  File "/usr/local/lib/python2.7/dist-packages/usb/core.py", line 825, in get_active_configuration
    return self._ctx.get_active_configuration(self)
  File "/usr/local/lib/python2.7/dist-packages/usb/core.py", line 211, in get_active_configuration
    self.managed_open()
  File "/usr/local/lib/python2.7/dist-packages/usb/core.py", line 106, in managed_open
    self.handle = self.backend.open_device(self.dev)
  File "/usr/local/lib/python2.7/dist-packages/usb/backend/libusb1.py", line 778, in open_device
    return _DeviceHandle(dev)
  File "/usr/local/lib/python2.7/dist-packages/usb/backend/libusb1.py", line 640, in __init__
    _check(_lib.libusb_open(self.devid, byref(self.handle)))
  File "/usr/local/lib/python2.7/dist-packages/usb/backend/libusb1.py", line 592, in _check
    raise USBError(_strerror(ret), ret, _libusb_errno[ret])
usb.core.USBError: [Errno 13] Access denied (insufficient permissions)

5. Flashed mbed board to firmware mbedmicrontroller_141212
6. Unplugged and replugged the mbed board
7. New firmware updated automatically
8. Activated mbed USB microcontroller via Removable Devices in VMplayer
9. mbed files from the microcontroller initially did not appear in VMplayer initially but ultimately does appear after some troubleshooting
10. Retried to run python script basic_test.py in the test directory of pyOCD, but the same USB error appears below
    usb.core.USBError: [Errno 13] Access denied (insufficient permissions)
11. Ran the same python script with sudo
    user@ubuntu:/mnt/hgfs/mbed/pyOCD-master/test$ sudo python basic_test.py
12. Script runs but is waiting for USB device even though the mbed board is already connected
    INFO:root:Waiting for a USB device connected

