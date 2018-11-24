layout: true

<footer>
dinosaur.is/leds-101/
</footer>

---
class: center

# an introduction to off-grid programmable LEDs

???

---
class: center

## hi

we're [Mikey](https://dinosaur.is) and [Ben](http://www.bennolan.com/)

we've done some LED things before.

???

---
class: center

## what to expect from this workshop

this workshop should provide a rough field guide to begin your LED adventures.

we won't be able to explain everything in depth, instead we will give breadcrumbs you can use later: an overview of the landscape, what things in this landscape are called, and how to get started on your learning journey.

???

---
class: center

## outline

1. what are programmable LEDs?
2. how do you control the LEDs? (arduino and basic programming)
3. how do you connect to/from the LEDs? (soldering strips, JST plugs)
4. how do you power the LEDs? (buck converters + 12v batteries or 18650s or AAs)

with a bonus round of 'how to order the good shit from AliExpress'.

---
class: center

## what are programmable LEDs?

we're going to be playing with WS2018B or APA102C (or SK9822) LEDS.

- each pixel is individually addressable (can be an independent color)
- you talk to the LEDs over a wire using a protocol called [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface)
- powered at 5V (or lower voltages such as 3.3V is acceptable)

TODO picture of led stip, grid, single led

---

### other types of electro-magic lights

- 12v single-color LED strips
- El-Wire
- El-Plate
- ???

---

## how do you control the LEDs?

to control your heap of LEDs, you will use a micro-controller (a small computer) to send messages over a wire to the first LED, who will relay extra messages to the next LED, and so on.

---

### micro-controller

we will be using the popular Ardunio flavor of micro-controllers.

---

### spi

---

### fastled

---

### hsv

---

### example 1

single: rainbow fade

---


### example 2

strip: rainbow scroll

---

### adding buttons

---

### adding rotary encoders

---

### example 3

strip: rainbow chase

---

### more dimensions

```
set_color(x, y, color)
```

```
set_color(x, y, z, color)
```

---

### example 4

grid: explosion

---

## how to connect to/from the leds?

---

### 4-pin jst connectors

- pre-installed on LED strips by default
- useful wire-to-wire connector
- not waterproof

---

### 4-pin header connectors

https://www.amazon.com/gp/product/B0777BQC1P/

- useful wire-to-wire and board-to-wire connector
- not waterproof

---

### 4-pin waterproof connectors

---

### soldering tips

---

## how to power the leds?

---

### power use

---

### power injection

---

### 5v power supply

---

### 12v battery + dc step-down (buck) converter

---

### 18650 batteries

---

### aa batteries

---
class: center

# thanks

=^.^=

???

thanks for your attention

i barely even scratched the surface

if you want to learn more, then get amongst!
