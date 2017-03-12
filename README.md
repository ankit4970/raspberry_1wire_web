To enable 1wire support on Raspberry Pi

#$ sudo nano /boot/config.txt

dtoverlay=w1-gpio

After booting add following modules

#$ sudo modprobe w1-gpio
#$ sudo modprobe w1-therm 

Note: Need to do again after  restart

To compile:(On host)

#$ arm-linux-gnueabihf-gcc rpi_wire.c -o rpi_wire -I/****path***/curl-7.48.0/build/include /****path***/curl-7.48.0/build/lib/libcurl.a -lrt

On RPI
#$ gcc rpi_wire.c -o rpi_wire -I/****path***/curl-7.48.0/build/include /****path***/curl-7.48.0/build/lib/libcurl.a -lrt

To run the binary on pi

#> ./rpi_wire