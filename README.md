# arduino-Filter

The Filter library includes filtering software used to smooth analog inputs. This is really useful when you have an analog signal that is unstable.

## Gettings started

### Prerequisites
1. The [Arduino IDE](http://www.arduino.cc) 1.8.0 or higher
2. The [Industrial Shields Arduino boards](http://blog.industrialshields.com/en/installing-industrial-shields-equipment-to-the-arduino-ide/) (optional, used in the examples)

### Installing
1. Download the [library](https://github.com/Industrial-Shields/arduino-Filter) from the GitHub as a "ZIP" file.
2. From the Arduino IDE, select the downloaded "ZIP" file in the menu "Sketch/Inlcude library/Add .ZIP library".
3. Now you can open any example from the "File/Examples/Filter" menu.


## Usage

```c++
#include <Filter.h>
```

The filter module includes filtering software used to smooth analog inputs. This is really useful when you have an analog signal that is unstable. The definition of the analog filter requires a number of samples and a sample period:
```c++
AnalogFilter<10, 2> aFilter;
```
In this example, the sample time is 2ms and the number of samples is 10.

It is also possible to call the constructor of the filter with an initial value.
```c++
AnalogFilter<10, 2> aFilter(24000);
```
Here the initial value of the filter is 24000, instead of 0 (the default).

The `update` function returns the filtered value according to the passed input value as argument.

```c++
int input = analogRead(I0_0);
int filteredInput = aFilter.update(input);
```
