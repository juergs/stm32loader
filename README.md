STM32Loader
===========

Python script which will talk to the STM32 bootloader to upload and download firmware.

Requires Python 3.

Original Version by: Ivan A-R <ivan@tuxotronic.org>.


Usage
-----

```
./stm32loader.py [-hqVewvr] [-l length] [-p port] [-b baud] [-a addr] [file.bin]
    -h          This help
    -q          Quiet
    -V          Verbose
    -e          Erase (note: this is required on previously written memory)
    -w          Write
    -v          Verify (recommended)
    -r          Read
    -l length   Length of read
    -p port     Serial port (default: /dev/tty.usbserial-ftCYPMYJ)
    -b baud     Baud speed (default: 115200)
    -a address  Target address
    -g address  Address to start running at (0x08000000, usually)
```


Example
-------

```
stm32loader.py -e -w -v somefile.bin
```

This will pre-erase flash, write `somefile.bin` to the flash on the device, and then perform a verification after writing is finished.
