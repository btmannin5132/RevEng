# Microcontorller Tutorial

Ben Manning, Purdue University

Last Modified: 2025-12-04



## Overview

In this lab, you will reverse-engineer and replicate key components of a
basic appliance using an Arduino Nano. The goal is to explore common
functionalities like sensor inputs, data display, and motor control,
which are often found in consumer appliances. Each task includes wiring
diagrams, sample code, and exercises to apply your knowledge. This
hands-on approach simulates real-world reverse engineering, where you
must modify existing systems and overcome limitations.

### Learning Objectives

-   Interface with GPIO to control inputs and outputs.

-   Implement digital and analog sensors to simulate user input.

-   Display information using I2C displays.

-   Communicate with multiple devices using I2C and UART protocols.

-   Control DC brushed motors and servos using PWM.

-   Understand the limitations of the Arduino Nano in
    reverse-engineering contexts.

## Materials Needed

-   Arduino Nano

-   Breadboard and jumper wires

-   Resistors ($10k\Omega$, $220\Omega$)

-   Push button

-   Potentiometer

-   7-segment display

-   I2C LCD display (16x2)

-   DC motor (brushed)

-   L298N motor driver module

-   Servo motor

-   Ultrasonic sensor (HC-SR04)

-   Power supply (5V)

## Disclosure

This lab is designed in the assumption that the learner has a general
knowledge set of electronics and programming. The learner does not need
to know the formatting needed for an Arduino or C specifically, but
should be familiar with how functions are designed in programming.

Schematics are not generally provided in this document. While there is a
wiring guide to state what pins are used where, the user is assumed to
know generally how standard devices are attached in a circuit. For
example, a potentiometer will need to have an input voltage and common
ground attached to outside pins for it to operate as a voltage divider.

## Introduction to Arduino

Arduino is an open-source electronics platform that simplifies the
process of building and controlling electronics. The Arduino Nano, used
in this lab, is a small, versatile board that includes digital and
analog pins, PWM outputs, and communication protocols like I2C and UART.
It is widely used in prototyping and reverse-engineering tasks due to
its low cost and simplicity.

### General information on an Arduino and using the Arduino IDE

If you do not have the Arduino IDE already, please download and install
the environment. The Arduino IDE can be downloaded at not cost from
Arduino LLC at
[www.arduino.cc/en/software](www.arduino.cc/en/software).

Functionally, an Arduino has two primary functions that must be inside
of every program that is uploaded to it. The **setup()** function runs
once and is used to initialize different parts of the microcontroller.
After the **setup()** function, the **loop()** function runs essentially
as a loop initialized with while(0==0), meaning that the program will
run indefinitely until it is halted by turning the device off, or it
runs into an error that causes it to crash.

Inside of the Arduino IDE, there are a variety of examples and libraries
that come pre-installed to assist you with your project at hand.
[arduino.cc](arduino.cc) also has a community tab with a forum and
project hub that can likely assist with whatever issues you may have.

### Advanced Microcontroller systems (AVRs)

The main processor for the Arduino an Atmel ATMEGA328 chip which is in
the AVR family of microprocessors. You can use the processor
independently using more traditional programming similar to what you
will experience in ECE362 at Purdue. This opens up the processor to a
variety of other functions and applications that are partially limited
on an Arduino due to Arduino LLC's mission to make the microcontroller
more user-friendly. There is also a lot of documentation available on
programming AVRs if you wish to go down this road.

Reverse engineering plays a large role in electronics competition as a
way to spin off a competitor's product. Using an inexpensive
microcrontroller can often allow for a competitor to cut costs by
limiting the amount of analog electronics needed to make a system by
simulating the analog nature of some devices. Recreating the device
using a microcontroller can also assist you with understanding the
process that a device goes through to complete a task.

Your primary task for this lab is to create a functional replica of the
thermostat that was reverse engineered in the beginning of the course
using an Arduino Nano along with assorted sensors and switches. Document
your processes and findings in your journal like you would any other
lab.

Below you will find a variety exercises that will introduce you to
different functions of the Arduino Nano and assist you with some sample
code to get moving on the primary task at hand. Use the exercises as you
see fit to complete your task, and then as a resource in the future as
you replicate other products.

## GPIO and Digital Sensors/Buttons

### Objective

Interface with basic digital sensors to simulate appliance control, such
as buttons and indicators.

### Wiring Diagram

Connect a push button to digital pin `D2` and an LED to pin `D13`. Pull
the button LOW with a 10K$\Omega$ resistor. Use a 220$\Omega$ resistor
in series with the LED. Ensure that there is proper voltage and ground
attached to all components.

### Sample Code

``` {.objectivec language="C"}
const int buttonPin = 2;
const int ledPin = 13;
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  buttonState = digitalRead(buttonPin);
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
```

### Exercise

Modify the code so that the LED toggles on and off with each button
press, staying on after one press and turning off after another.

## Analog Sensors for Control

### Objective

Use an analog sensor to simulate variable control, such as temperature
adjustment or speed control.

### Wiring Diagram

Connect the center pin of a potentiometer to pin `A0` and an LED to pin
`D9`. Use a 220$\Omega$ resistor in series with the LED. Make sure the
outside pins of the potentiometer are attached to 5V and GND of the
Arduino.

### Sample Code

``` {.objectivec language="C"}
const int potPin = A0;
const int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int sensorValue = analogRead(potPin);
  int outputValue = map(sensorValue, 0, 1023, 0, 255);
  analogWrite(ledPin, outputValue);
}
```

### Exercise

Modify the code to control the frequency of a buzzer using the
potentiometer instead of controlling an LED.

## 7-Segment Display

### Objective

Display numeric data, such as temperature or time, on a 7-segment
display. Ensure that there is proper voltage and ground attached to all
components.

### Wiring Diagram

Connect the 7-segment display to pins `D2` through `D8` using
220$\Omega$ resistors.

### Sample Code

``` {.objectivec language="C"}
const int segments[] = {2, 3, 4, 5, 6, 7, 8};

const byte digitPatterns[10] = {
  B00111111, B00000110, B01011011, B01001111, B01100110,
  B01101101, B01111101, B00000111, B01111111, B01101111
};

void setup() {
  for (int i = 0; i < 7; i++) {
    pinMode(segments[i], OUTPUT);
  }
}

void loop() {
  displayDigit(3);  // Display number 3
  delay(1000);
}

void displayDigit(int digit) {
  byte pattern = digitPatterns[digit];
  for (int i = 0; i < 7; i++) {
    digitalWrite(segments[i], bitRead(pattern, i));
  }
}
```

### Exercise

Modify the code to cycle through digits 0 to 9 on the 7-segment display
every second.

## I2C LCD Display

### Objective

Display information on an I2C LCD (16x2).

### Wiring Diagram

Connect the I2C LCD to the Arduino Nano's `SDA` (pin `A4`) and `SCL`
(pin `A5`). Ensure that there is proper voltage and ground attached to
all components.

### Sample Code

``` {.objectivec language="C"}
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);  // LCD address 0x27

void setup() {
  lcd.begin();
  lcd.backlight();
  lcd.print("Hello, World!");
}

void loop() {}
```

### Exercise

Modify the code to display \"Appliance ON\" when a button is pressed and
\"Appliance OFF\" when the button is released.

## DC Motor Control Using PWM

### Objective

Control the speed and direction of a DC motor using PWM signals.

### Wiring Diagram

Connect the motor to an L298N motor driver, and use pins `D9`, `D10`,
and `D11` for control. Ensure that there is proper voltage and ground
attached to all components.

### Sample Code

``` {.objectivec language="C"}
const int in1Pin = 9;
const int in2Pin = 10;
const int enablePin = 11;

void setup() {
  pinMode(in1Pin, OUTPUT);
  pinMode(in2Pin, OUTPUT);
  pinMode(enablePin, OUTPUT);
}

void loop() {
  digitalWrite(in1Pin, HIGH);
  digitalWrite(in2Pin, LOW);
  analogWrite(enablePin, 128);  // Set motor speed
  delay(2000);

  analogWrite(enablePin, 0);  // Stop motor
  delay(1000);
}
```

### Exercise

Modify the code so that the motor speed is controlled by a potentiometer
connected to pin `A0`.

## Servo Control Using PWM

### Objective

Control a servo motor to move parts, like dials or levers, in an
appliance.

### Wiring Diagram

Connect the servo motor's signal wire to pin `D9`. Ensure that there is
proper voltage and ground attached to all components.

### Sample Code

``` {.objectivec language="C"}
#include <Servo.h>

Servo myServo;

void setup() {
  myServo.attach(9);
}

void loop() {
  myServo.write(0);  // Rotate servo to 0 degrees
  delay(1000);
  myServo.write(90);  // Rotate to 90 degrees
  delay(1000);
}
```

### Exercise

Modify the code to control the servo position using a potentiometer
connected to pin `A0`.

### Advanced Exercise

Modify the code to control the servo WITHOUT the servo library.

## Limitations of the Arduino Nano in Reverse Engineering

-   **Memory**: The Nano's 2KB SRAM may limit the complexity of the
    operations or number of libraries you can run simultaneously.

-   **Processing Power**: The 16 MHz clock speed may not suffice for
    real-time data processing or handling multiple sensor inputs
    concurrently.

-   **Pin Count**: The limited number of I/O pins (14 digital) restricts
    how many devices you can connect simultaneously.

-   **No Native Wireless Communication**: Wireless communication, such
    as Bluetooth or Wi-Fi, is not built-in and requires external
    modules.

## Another Disclosure: Use other Microcontrollers in the future!

As you may be aware, there are a wide variety of other microcontollers
out there that vary in size, functionality, and usability. Explore your
options to better fit your applications. Below are some of the major
micorcontrollers that are commercially available quite regularly.

-   Arduino (AVRs, Arudino Uno, Nano, Micro, Mega \...)\
    Pros:

    -   Open-source

    -   Simple to use

    -   Wide variety of models and styles

    -   Large hobby community

    Cons:

    -   Limited in functionality unless used as AVR

    -   Argued to be outdated compared to newer microcontrollers

-   ESP (ESP32, ESP8266)\
    Pros:

    -   Open-source

    -   A lot of embedded functionality such as Wi-Fi and Bluetooth

    -   Large hobby community

    Cons:

    -   Main board is more difficult to solder than other controllers

    -   Limited anlaog pins- need to use an external mux to get more
        functionality

-   STM (STM8, STM32)\
    Pros:

    -   Used a lot in commercial products

    -   Very large functionality

    Cons:

    -   Proprietary

    -   Need licence to program properly

-   Raspberry Pi Pico (RP2040)\
    Pros:

    -   New

    -   Inexpensive

    -   Developing user base

    -   New versions being released with a lot of different
        functionality

    Cons:

    -   Proprietary

    -   New

-   Raspberry Pi (mini-computer)\
    While not a microcontroller, a Raspberry Pi can be programmed with
    much of the same functions as the above microcrontollers with a lot
    more memory and power.\
    Pros:

    -   Inexpensive

    -   strong user base

    -   Full Linux OS support

    -   WiFi, HDMI, USB, Ethernet, Camera input ready to go.

    Cons:

    -   Proprietary

    -   Needs OS installed

    -   Takes longer to setup, but can streamline in the future.
