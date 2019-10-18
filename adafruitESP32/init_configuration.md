## Steps to load micropython in ESP32:

1. The first thing you need to do is download the most recent MicroPython firmware .bin file to load onto your ESP32 device.
You can download it from :
_https://micropython.org/download#esp32_











Code:
import machine
pin12 = machine.Pin(12,machine.Pin.OUT)
pin12.value(1)
pin13 = machine.Pin(13, machine.Pin.IN, machine.Pin.PULL_UP)
print(pin13.value())