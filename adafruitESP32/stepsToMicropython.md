## Steps to install Micropython in ESP32.

### Material:
1. ESP32 Adafruit,
2. the firmware _.bin_ file,
3. esptools.py

### Steps:
1. download the firmware from _micropython.org_
2. install esptools -> __$ pip install esptool__
2.1. To execute the code esptool: __$ esptool.py__
3. Erase all inside the ESP32 to install the firmware the first time:
__$ esptool.py --chip esp32 erase_flash --port /dev/tty[Device]__

4. install the firmware:
__$ esptool.py --chip esp32 --port <serial_port> write_flash -z 0x1000 <esp32-X.bin>__