---
title: "Changing PWM Frequency for Arduino Leonardo"
short: Leonardo PWM
author: admin
date: 2014-10-25 18:14:37
categories:
  - Icosahedron

tags: 
  - arduino
  - leonardo
  - frequency
  - pwm
  - 6.1
  - wow such electrons

template: article.jade
---

# Notes:

What does it prevent? loud annoying motor noise



What else?

# Ardumoto

>  This is a motor shield for Arduino that will control two DC motors. Based on the L298 H-bridge, the Ardumoto can drive up to 2 amps per channel.

>  Control for motor attached to OUT1/2 is connected to digital line 12 (direction A) and digital line 3 (PWM A). Control for motor attached to OUT3/4 is connected to digital line 13 (direction B) and digital line 11 (PWM B).

For Ardumoto, digital lines 3 and 11 used for PWM for motors A, B respectively. 

On Arduino Uno, digital lines 3 and 11 are connected to Timer 2 (cycle length 510, so 15Mhz / 510 = 31.37kHz is the maximum possible frequency — also of 8 bit resolution, so up to 256 different possible duty cycles). 


>  | Setting  |   Divisor|   Frequency |
>  |----------|----------|-------------|
>  | `0x01`   |   1      |  31372.55   |
>  | `0x02`   |   8      |  3921.16    |
>  | `0x03`   |   32     |  980.39     |
>  | `0x04`   |   64     |  490.20  | (DEFAULT)|
>  | `0x05`   |   128    |  245.10     |
>  | `0x06`   |   256    |  122.55     |
>  | `0x07`   |   1024   |  30.64      |

    TCCR2B = TCCR2B & 0b11111000 | <setting>;

    All frequencies are in Hz and assume a 16000000 Hz system clock.

On Arduino Leonardo, digital lines 3 and 11 are connected to Timer 0, but the Arduino Library uses Timer 0 for the operation of `millis()` and `delay()`, so changing Timer 0 isn't really a valid option. 

Arduino Leonardo's ATmega32u4 microcontroller includes a new timer, Timer 4, which is connected to pins 6 and 13, and operates at a whopping 64MHz. 

> If you change TCCR0B, it affects millis() and delay(). They will count time faster or slower than normal if you change the TCCR0B settings. Below is the adjustment factor to maintain consistent behavior of these functions:


My Code:

    void setup() {
      pinMode(pwm_b, OUTPUT);
      pinMode(dir_b, OUTPUT);
      TCCR4B = TCCR4B & 0b11111000 | 0x01;      
    }

http://provideyourown.com/2012/arduino-leonardo-versus-uno-whats-new/

> Timer 0
>   bits = 8
>   Clock speed = 16 MHz (system clock speed)
>   Default prescale = 64
>   Pins D3 & D11
> 
> Timers 1 and 3
>   bits = 16
>   Clock speed = 16 MHz (system clock speed)
>   Default prescale = 64
>   Pins D5, D9 & D10
>   Pin D11 can also be set to use timer 1 output (OC1C), but the Arduino library uses it for timer 0 (8-bit). To use it on timer 1, it must be done by setting the appropriate registers.
> 
> Timer 4
>   bits = 10
>   Clock speed = 64 MHz
>   Default prescale = 64
>   Pins D6, D13
>   Pin D10 (PB6) also has a timer 4 output (OC4B), but the Arduino library uses it for timer 1 (16-bit). To use it on timer 4, it must with the registers.

http://arduino-info.wikispaces.com/Arduino-PWM-Frequency

http://www.instructables.com/id/Step-by-Step-Guide-to-the-Arduino-Leonardo/step2/Extra-PWM-pin/

http://harizanov.com/2013/04/crazy-high-frequency-pwm-with-atmega32u4/

http://academy.cba.mit.edu/classes/embedded_programming/doc7766.pdf


## For Uno:

    /**
     * Divides a given PWM pin frequency by a divisor.
     * 
     * The resulting frequency is equal to the base frequency divided by
     * the given divisor:
     *   - Base frequencies:
     *      o The base frequency for pins 3, 9, 10, and 11 is 31250 Hz.
     *      o The base frequency for pins 5 and 6 is 62500 Hz.
     *   - Divisors:
     *      o The divisors available on pins 5, 6, 9 and 10 are: 1, 8, 64,
     *        256, and 1024.
     *      o The divisors available on pins 3 and 11 are: 1, 8, 32, 64,
     *        128, 256, and 1024.
     * 
     * PWM frequencies are tied together in pairs of pins. If one in a
     * pair is changed, the other is also changed to match:
     *   - Pins 5 and 6 are paired on timer0
     *   - Pins 9 and 10 are paired on timer1
     *   - Pins 3 and 11 are paired on timer2
     * 
     * Note that this function will have side effects on anything else
     * that uses timers:
     *   - Changes on pins 3, 5, 6, or 11 may cause the delay() and
     *     millis() functions to stop working. Other timing-related
     *     functions may also be affected.
     *   - Changes on pins 9 or 10 will cause the Servo library to function
     *     incorrectly.
     * 
     * Thanks to macegr of the Arduino forums for his documentation of the
     * PWM frequency divisors. His post can be viewed at:
     *   http://www.arduino.cc/cgi-bin/yabb2/YaBB.pl?num=1235060559/0#4
     */
    void setPwmFrequency(int pin, int divisor) {
      byte mode;
      if(pin == 5 || pin == 6 || pin == 9 || pin == 10) {
        switch(divisor) {
          case 1: mode = 0x01; break;
          case 8: mode = 0x02; break;
          case 64: mode = 0x03; break;
          case 256: mode = 0x04; break;
          case 1024: mode = 0x05; break;
          default: return;
        }
        if(pin == 5 || pin == 6) {
          TCCR0B = TCCR0B & 0b11111000 | mode;
        } else {
          TCCR1B = TCCR1B & 0b11111000 | mode;
        }
      } else if(pin == 3 || pin == 11) {
        switch(divisor) {
          case 1: mode = 0x01; break;
          case 8: mode = 0x02; break;
          case 32: mode = 0x03; break;
          case 64: mode = 0x04; break;
          case 128: mode = 0x05; break;
          case 256: mode = 0x06; break;
          case 1024: mode = 0x7; break;
          default: return;
        }
        TCCR2B = TCCR2B & 0b11111000 | mode;
      }
    }


