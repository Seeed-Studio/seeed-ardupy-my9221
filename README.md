# Seeed ArduPy MY9221 [![Build Status](https://api.travis-ci.com/Seeed-Studio/seeed-ardupy-my9221.svg?branch=master)](https://travis-ci.com/github/Seeed-Studio/seeed-ardupy-my9221)

## Introduction
Seeed ArduPy MY9221 is a Arduino libraies binding for ArduPy.

Grove – LED Bar is comprised of a 10 segment LED gauge bar and an MY9221 LED controlling chip. It can be used as an indicator for remaining battery life, voltage, water level, music volume or other values that require a gradient display. There are 10 LED bars in the LED bar graph: one red, one yellow, one light green, and seven green bars. Demo code is available to get you up and running quickly. It lights up the LEDs sequentially from red to green, so the entire bar graph is lit up in the end. Want to go further? Go ahead and code your own effect.

You can get more information in here [Grove_LED_Bar](https://github.com/Seeed-Studio/Grove_LED_Bar).

![da](https://raw.githubusercontent.com/Seeed-Studio/Grove_LED_Bar/master/Grove_LED_Bar.gif)

## How to binding with ArduPy
- Install [AIP](https://github.com/Seeed-Studio/ardupy-aip)
- Build firmware with Seeed ArduPy MY9221
```
    aip install Seeed-Studio/seeed-ardupy-my9221
    aip build
```
- Flash new firmware to you ArduPy board
```
    aip flash <path of the new firmware>
```
For more examples of using AIP, please refer to [AIP](https://github.com/Seeed-Studio/ardupy-aip).

## Usage

```
from arduino import grove_led_bar
import time

led_bar = grove_led_bar(0, 1) #clock, data
i = 0

while True:
    i = i + 1
    led_bar.set_bits(i)
    time.sleep(0.05)
```

## API Reference

- **set_bits(*value\<int\>*)**

    Turn on the corresponding No of LED.
    ```
    set_bits(0b000000000000101) # Turn on LEDs 1 and 3
    set_bits(0x155); # Turn on LEDs 1, 3, 5, 7, 9
    ```

- **get_bits(*null*)**

    Get current LED bar state.
    ```
    get_bits()
    ```

- **set_level(*level\<float\>*)**

    Walk through the levels
    ```
    set_level(5)
    ```
- **set_brightness(*No\<int\>, brightness\<float\>*)**

    Set brightness of the corresponding No LED.
    ```
    set_brightness(1, 50) # Set Led No. 1 brightness to 50
    ```
- **set_brightness(*No\<int\>, brightness\<float\>*)**

    Toggle the corresponding No of LED.
    ```
    toggle(5) # Toggle the LEDs 1.
    ```


----

This software is written by seeed studio<br>
and is licensed under [The MIT License](http://opensource.org/licenses/mit-license.php). Check License.txt for more information.<br>

Contributing to this software is warmly welcomed. You can do this basically by<br>
[forking](https://help.github.com/articles/fork-a-repo), committing modifications and then [pulling requests](https://help.github.com/articles/using-pull-requests) (follow the links above<br>
for operating guide). Adding change log and your contact into file header is encouraged.<br>
Thanks for your contribution.

Seeed Studio is an open hardware facilitation company based in Shenzhen, China. <br>
Benefiting from local manufacture power and convenient global logistic system, <br>
we integrate resources to serve new era of innovation. Seeed also works with <br>
global distributors and partners to push open hardware movement.<br>


[![Analytics](https://ga-beacon.appspot.com/UA-46589105-3/Grove_LED_Bar)](https://github.com/igrigorik/ga-beacon)