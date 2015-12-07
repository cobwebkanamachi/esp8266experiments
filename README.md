# esp8266experiments
These are experiments for Espressif's esp8266 module.<BR>
I use this bellow.<BR>
http://akizukidenshi.com/catalog/g/gM-09607/<BR>
1. How to write firmware to esp8266<BR>
1.1 you need to install pyserial<BR>
1.2 and then install esptool.py<BR>
1.3 download esp_iot_sdk_v1.4.0_15_09_18.zip from expressif bbs<BR>
1.4 extract firmware files from zip to ./bin (under esp_iot_sdk_v1.4.0_15_09_18/esp_iot_sdk_v1.4.0/bin to ./bin)<BR>
2. And then, how to program firmware<BR>
OS env is osx 10.10.5<BR>
/Library/Frameworks/Python.framework/Versions/2.7/bin/esptool.py --port /dev/tty.usbserial-XXXXXXXX -b 9600 write_flash -ff 40m -fm qio -fs 32m 0x00000 "bin/boot_v1.4(b1).bin" 0x01000 bin/at/1024+1024/user1.2048.new.5.bin 0xfe000 bin/blank.bin 0x3fc000 bin/esp_init_data_default.bin 0x3fe000 bin/blank.bin<BR>
3. test<BR>
3.1 connect esp8266 with FTDI via serial term with 115200bps<BR>
3.2 AT+GMR<BR>
4. SDK<BR>
4.1 we use vagrant.<BR>
choose vagrant file bellow for experiment.<BR>
https://github.com/kmpm/esp8266-vagrant<BR>
please clone.<BR>
4.2 get image of ubuntu/trusty32<BR>
vagrant box add ubuntu/trusty32  https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-i386-vagrant-disk1.box<BR>
4.3 vagrant up<BR>
but you suffer some error..<BR>
4.4 ssh<BR>
ssh -p 2222 vagrant@127.0.0.1<BR>
4.5 uname -a<BR>
vagrant@vagrant-ubuntu-trusty-32:~$ uname -a<BR>
Linux vagrant-ubuntu-trusty-32 3.13.0-71-generic #114-Ubuntu SMP Tue Dec 1 02:35:20 UTC 2015 i686 i686 i686 GNU/Linux<BR>
now i am here:0)<BR>
#obsolete procedure bellow.<BR>
I am experiment make vagrant image, so bellow is obsolete:-)<BR>
I will change this section after.<BR>
4.1 1st you would better to read<BR>
http://www.esp8266.com/wiki/doku.php?id=setup-windows-compiler-esp8266<BR>
4.2 download sysgcc all in one installer<BR>
Prebuilt GNU toolchain for esp8266<BR>
http://gnutoolchains.com/esp8266/<BR>
but you would need to install rm or other commands by yourself:-).<BR>
4.3 you would suffer some error to invoke make clean <BR>
http://d.hatena.ne.jp/ir9Ex/20121206/1354774247<BR>
#Thanx http://nemuisan.blog.bai.ne.jp/?month=201506<BR>
