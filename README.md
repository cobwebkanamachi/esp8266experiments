# esp8266experiments
These are experiments for Expressif's esp8266 module.<BR>
1. How to write firmware to esp8266<BR>
1.1 you need to install pyserial<BR>
1.2 and then install esptool.py<BR>
2. And then, how to program firmware<BR>
OS env is osx 10.10.5<BR>
/Library/Frameworks/Python.framework/Versions/2.7/bin/esptool.py --port /dev/tty.usbserial-XXXXXXXX -b 9600 write_flash -ff 40m -fm qio -fs 32m 0x00000 "bin/boot_v1.4(b1).bin" 0x01000 bin/at/1024+1024/user1.2048.new.5.bin 0xfe000 bin/blank.bin 0x3fc000<BR> bin/esp_init_data_default.bin 0x3fe000 bin/blank.bin<BR>
3. test<BR>
3.1 connect esp8266 with FTDI via serial term with 115200bps<BR>
3.2 AT+GMR<BR>

# Thanx http://nemuisan.blog.bai.ne.jp/?month=201506
