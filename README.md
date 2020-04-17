# BME280 sensor on raspberry pi

I used the Waveshare BME280 Environmental Sensor because there is no soldering included. Just plug and play.

## hardware

```bash
sudo lsmod | grep "bcm"
```

Look for **i2c_bcm2835** and **spi_bcm2835**

## code change

for you to get the code working, you have to see where sensor is detected from the hardware.

```bash
sudo i2cdetect -y 1
```

The output

```bash
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- 76 --
```

in the main.c file search for ###ADDRESS### to see which lines you need to change.

## compile

just run **make**

## Libs

- Sensor driver for BME280 sensor
- wiringPi
- wiringPiSPI
