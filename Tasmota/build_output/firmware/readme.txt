These files are needed for flashing Tasmota32 with esptool.py to an ESP32.

Command syntax for flashing Tasmota32 firmware on ESP32 via Esptool (replace COM Port Number!):

esptool.py --port /dev/ttyUSB0 erase_flash

esptool.py --chip esp32 --port /dev/ttyUSB0 --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dout --flash_freq 40m --flash_size detect 0x1000 bootloader_dout_40m.bin 0x8000 partitions.bin 0xe000 boot_app0.bin 0x10000 LABDisplay.bin 



select configuration, config module in the weather station website after giving wifi credentials
gpio21 i2c sda
gpio22 i2c scl

then for display oled:
webmenu consoles, console

rule1 on BME280#Temperature do displaytext [f0s2p15x0y0] %value% C endon on BME280#Humidity do displaytext [x0y25] %value% % endon on tele-BME280#Pressure do displaytext [x0y50] %value% hPa endon

 rule1 on
 displaymodel 7
 displaymode 0
 teleperiod 10

and then reset and toogle on

