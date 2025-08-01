# Orange Pi Zero 2W Fork
- This code is intended for Orange Pi Zero 2W, but may work on other Orange Pi devices with minimal tweaking
- Only C mode supported!! Python does NOT work because gpiozero is Rpi only.

## Prerequisites
- Please install the Orange Pi fork of wiringpi at https://github.com/orangepi-xunlong/wiringOP/tree/next
- Enable SPI PROPERLY in your OS config!!
    - See https://forum.armbian.com/topic/18824-spi-communication-nonfunctional-no-data-received/#comment-127975
    - use [spidev-test](https://github.com/rm-hull/spidev-test) to make sure your spi is working

## Changes
- Use Wiringpi by default
- Support Armbian
- **Configurable SPI settings** - Use Makefile variables to easily change SPI configuration:
  - `SPI_CHANNEL`: SPI channel (default: 1 for Orange Pi Zero 2W)
  - `GPIO_CHIP`: GPIO chip number (default: 1 for Orange Pi Zero 2W)
  - `SPI_DEVICE_PATH`: Custom SPI device path (default: auto-generated from channel)
- Use physical GPIO numbers (board agnostic)

### SPI Configuration Examples
```bash
# Use default settings (SPI channel 1, GPIO chip 1)
make RPI EPD=epd2in13

# Use SPI channel 0 instead (for standard Raspberry Pi)
make RPI EPD=epd2in13 SPI_CHANNEL=0

# Use GPIO chip 0 (for standard Raspberry Pi)  
make RPI EPD=epd2in13 GPIO_CHIP=0

# Use both channel 0 and chip 0 (standard Raspberry Pi configuration)
make RPI EPD=epd2in13 SPI_CHANNEL=0 GPIO_CHIP=0

# Use custom SPI device path
make RPI EPD=epd2in13 SPI_DEVICE_PATH="/dev/spidev0.1"
```

# 说明 explain
Development 分支用于存放用户的提交的修改代码，经验证后，我们将移植到主分支中；非常感谢您对我们的支持</br>
The Development branch is used to store the modified code submitted by users. After verification, we will migrate it to the main branch. Thank you very much for your support </br>

# e-Paper  
waveshare electronics</br>
![waveshare_logo.png](waveshare_logo.png)

# 说明 explain
这个开发分支用于存放用户的提交的修改代码，经验证后，我们将移植到主分支中；非常感谢您对我们的支持</br>
This development branch is used to store the changes committed by users. After verification, we will migrate them to the main branch. Thank you very much for your support</br>

随着屏幕越来越多，程序包也越来越大，用户移植相对比较复杂；因此我们决定在保留原有git路径的基础下，新建一个目录用于保存以后的新屏幕或者老屏幕分离出来的代码。</br>
With more and more screens and larger packages, user migration is relatively complex. So we decided to create a directory where we could store any new screen or any code that's split from the old one, while keeping the old git path.</br>

E-paper_Separate_Program 这个文件用于存放每个墨水屏单独的示例代码，用户在使用时仅需在原本的路径下添加 /E-paper_Separate_Program/xxx  (PS: xxx 为对应屏幕名称)</br>
E-paper_Separate_Program This file is used to store the separate example code for each electronic paper. Users only need to add /E-paper_Separate_Program/xxx (PS: xxx is the corresponding screen name) to the original path.</br>

## 中文:  
Jetson Nano、Raspberry Pi、Arduino、STM32例程</br>
* RaspberryPi_JetsonNano  
    > C</br>
    > Python </br>
* Arduino:  
    > Arduino UNO R3 (最新屏幕无该示例代码)</br>
    > Arduino UNO R4</br>
* STM32:  
    > STM32F103ZET6 </br>
    
更多资料请在官网上搜索:  </br>
http://www.waveshare.net</br>


## English:  
Jetson Nano、Raspberry Pi、Arduino、STM32 Demo:  </br>
* RaspberryPi_JetsonNano:  
    > C</br>
    > Python</br>
* Arduino:  
    > Arduino UNO R3 (The latest screen does not have this example code)</br>
    > Arduino UNO R4 </br>
* STM32:  
    > STM32F103ZET6 </br>
    
For more information, please search on the official website:   </br>
https://www.waveshare.com</br>



