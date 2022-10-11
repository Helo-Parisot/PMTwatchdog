# PMTwatchdog

Simple Watchdog timer programm, to understand how a watchdog works, using C multithreading 

## License

MIT licence
> Copyright 2022 Héloïse Parisot & Formato ESEO
>
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the   Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


## Usage

### What are watchdog timers ?

A watchdog timer (WDT) is a device or electronic card that performs a specific operation after a certain period of time if something goes wrong with an electronic system and the system does not recover on its own.

A common problem is for a machine or operating system to lock up if two parts or programs conflict, or, in an operating system, if memory management trouble occurs. In some cases, the system will eventually recover on its own, but this may take an unknown and perhaps extended length of time. A watchdog timer can be programmed to perform a warm boot (restarting the system) after a certain number of seconds during which a program or computer fails to respond following the most recent mouse click or keyboard action. The timer can also be used for other purposes, for example, to actuate the refresh (or reload) button in a Web browser if a Web site does not fully load after a certain length of time following the entry of a Uniform Resource Locator (URL).

A WDT contains a digital counter that counts down to zero at a constant speed from a preset number. The counter speed is kept constant by a clock circuit. If the counter reaches zero before the computer recovers, a signal is sent to designated circuits to perform the desired action.

[Learn more about Watchdogs](https://www.embedded.com/introduction-to-watchdog-timers/)



### Usage of PMT Watchdog 

PMT watchdog shows how you can create a watchdog using multrithreading in C. This conception of a watchdog can be used in several problems, and follows this simplified class diagram : 

![simplified class diagram](https://imagizer.imageshack.com/img922/9958/vVmaFA.png)

This program performs a calculation of pi in ''compute.pi'' and a timer counts down constantly. If the duration of the pi calculation exceeds the timer, the program is stopped.

The correct operation of the watchdog can be checked by adjusting the duration of the execution of the π-computation (parameter ```iterationCount``` of the function ```startComputePi```) according to whether it ends before or after the watchdog expires.



### Building parameters

#### Precompiler
- macro definition _POSIX_C_SOURCE=199309L
- macro definition _REENTRANT
#### Compiler
- ISO C99 standard
#### Link Editor
- use pthread library
- use rt library


### Building 

This program can be built using a Makefile : Run the command ```make all``` in the directory with the source code and it will automatically compile static and shared libraries and a little test program (not the full test suite).



