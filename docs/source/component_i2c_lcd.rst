.. _cpn_i2c_lcd1602:

I2C LCD1602
==============

.. image:: img/i2c_lcd1602.png
    :width: 800

* **GND**: Ground
* **VCC**: Voltage supply, 5V.
* **SDA**: Serial data line.
* **SCL**: Serial clock line.

As we all know, though LCD and some other displays greatly enrich the man-machine interaction, they share a common weakness. When they are connected to a controller, multiple IOs will be occupied of the controller which has no so many outer ports. Also it restricts other functions of the controller. 

Therefore, LCD1602 with an I2C module is developed to solve the problem. The I2C module has a built-in PCF8574 I2C chip that converts I2C serial data to parallel data for the LCD display.        

* `PCF8574 Datasheet <https://www.ti.com/lit/ds/symlink/pcf8574.pdf?ts=1627006546204&ref_url=https%253A%252F%252Fwww.google.com%252F>`_

**Features**

* Display 2-lines x 16-characters
* Color：Blue Backlight, White characters
* Default Address: 0x27
* Working voltage: 5V
* Chip: PCF8574T
* Backlight on by default
* Contrast can be adjusted via potentiometer
* 4 Pins: GND, VCC, SDA and SCL


**I2C Address**

The default address is basically 0x27, in a few cases it may be 0x3F.

Taking the default address of 0x27 as an example, the device address can be modified by shorting the A0/A1/A2 pads; in the default state, A0/A1/A2 is 1, and if the pad is shorted, A0/A1/A2 is 0.

.. image:: img/i2c_address.jpg
    :width: 600

**Backlight/Contrast**

Backlight can be enabled by jumper cap, unplugg the jumper cap to disable the backlight. The blue potentiometer on the back is used to adjust the contrast (the ratio of brightness between the brightest white and the darkest black).


.. image:: img/back_lcd1602.jpg

* **Potentiometer**: It is used to adjust the contrast (the clarity of the displayed text), which is increased in the clockwise direction and decreased in the counterclockwise direction.
* **Shorting Cap**: Backlight can be enabled by this cap，unplugg this cap to disable the backlight.

    .. note::
        Because of the different production batches, the backlight on some I2C LCD1602 is on by default, so there is no solder pin and no jumper cap required.
        
        .. image:: img/i2c_lcd1602_backlight.png 

