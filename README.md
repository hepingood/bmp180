<div align=center>
<img src="/doc/image/logo.png"/>
</div>

## LibDriver ADS1115

[English](/README.md) | [ 简体中文](/README_CN.md)

### Table of Contents

  - [Description](#Description)
  - [Instruction](#Instruction)
  - [Install](#Install)
  - [Usage](#Usage)
    - [example basic](#example-basic)
  - [Document](#Document)
  - [Contributing](#Contributing)
  - [License](#License)
  - [Contact Us](#Contact-Us)


### Description

The BMP180 is the function compatible successor of the BMP085, a new generation of high precision digital pressure sensors for consumer applications.The ultra-low power, low voltage electronics of the BMP180 is optimized for use in mobile phones, PDAs, GPS navigation devices and outdoor equipment. With a low altitude noise of merely 0.25m at fast conversion time, the BMP180 offers superior performance. The IIC interface allows for easy system integration with a microcontroller.The BMP180 is based on piezo-resistive technology for EMC robustness, high accuracy and linearity as well as long term stability.

LibDriver BMP180 is a full function driver of BMP180 launched by LibDriver.It provides temperature, pressure reading and mode setting functions and so on.

### Instruction

/src includes LibDriver BMP180 source files.

/interface includes LibDriver BMP180 IIC platform independent template。

/test includes LibDriver BMP180 driver test code and this code can test the chip necessary function simply。

/example includes LibDriver BMP180 sample code.

/doc includes LibDriver BMP180 offline document.

/datasheet includes BMP180 datasheet。

/project includes the common Linux and MCU development board sample code. All projects use the shell script to debug the driver and the detail instruction can be found in each project's README.md.

### Install

Reference /interface IIC platform independent template and finish your platform IIC driver.

Add /src, /interface and /example to your project.

### Usage

#### example basic

```C
uint8_t res;
uint32_t i;
float temperature;
uint32_t pressure;

res = bmp180_basic_init();
if (res)
{
    return 1;
}

...

for (i = 0; i < 3; i++)
{
    bmp180_interface_delay_ms(1000);
    res = bmp180_basic_read((float *)&temperature, (uint32_t *)&pressure);
    if (res)
    {
        bmp180_basic_deinit();

        return 1;
    }
    bmp180_interface_debug_print("bmp180: temperature is %0.2fC.\n", temperature);
    bmp180_interface_debug_print("bmp180: pressure is %dPa.\n", pressure);
    
    ...
        
}

...

bmp180_basic_deinit();

return 0;
```

### Document

Online documents: https://www.libdriver.com/docs/bmp180/index.html

Offline documents: /doc/html/index.html

### Contributing

Please sent an e-mail to lishifenging@outlook.com

### License

Copyright (C) LibDriver 2015-2021 All rights reserved 



The MIT License (MIT) 



Permission is hereby granted, free of charge, to any person obtaining a copy

of this software and associated documentation files (the "Software"), to deal

in the Software without restriction, including without limitation the rights

to use, copy, modify, merge, publish, distribute, sublicense, and/or sell

copies of the Software, and to permit persons to whom the Software is

furnished to do so, subject to the following conditions: 



The above copyright notice and this permission notice shall be included in all

copies or substantial portions of the Software. 



THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR

IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,

FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE

AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER

LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,

OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE

SOFTWARE. 

### Contact Us

Please sent an e-mail to lishifenging@outlook.com