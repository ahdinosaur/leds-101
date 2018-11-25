layout: true

<footer>
dinosaur.is/leds-101/
</footer>

---
class: center

# an introduction to off-grid programmable LEDs

slides: https://dinosaur.is/leds-101

source: https://github.com/ahdinosaur/leds-101

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

this workshop is a whirlwind introduction to the concepts and practices to get started with off-grid art using programmable LEDs.

in our short time together, we hope to provide useful breadcrumbs to help you navigate the trails ahead:

- an overview of the landscape
- what things in this world are called
- how to get started on your journey
- what to look out for as you go
- some tips and tricks for your practice

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

we're going to be playing with WS2018B or [APA102C](https://www.pololu.com/product/2552) (or [SK9822](https://www.pololu.com/product/3086)) LEDS.

- each pixel is individually addressable (can be an independent color)
- you talk to the LEDs over wire(s) using a protocol called [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface)
- powered at 5V (or lower voltages such as 3.3V is acceptable)

<a class="thumbnail" href="https://www.adafruit.com/product/2477">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2477-04.jpg">
    <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2477-04.mp4">
    <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2477-04.jpg">
  </video>
</a>
<a class="thumbnail" href="https://www.adafruit.com/product/2736">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2736-03.jpg">
    <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2736-03.mp4">
    <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2736-03.jpg">
  </video>
</a>
<a class="thumbnail" href="https://www.adafruit.com/product/2868">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2868-07.jpg">
    <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2868-07.mp4">
    <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2868-07.jpg">
  </video>
</a>
<a class="thumbnail" href="https://www.adafruit.com/product/2860">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2860-04.jpg">
    <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2860-04.mp4">
    <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2860-04.jpg">
  </video>
</a>
<a class="thumbnail" href="https://www.adafruit.com/product/2237?length=1">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2237-08.jpg">
  <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2237-08.mp4">
  <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2237-08.jpg">
  </video>
</a>
<a class="thumbnail" href="https://www.adafruit.com/product/2435?length=2">
  <video preload="auto" muted="" loop="" autoplay="" poster="https://cdn-shop.adafruit.com/product-videos/1024x768/2435-05.jpg">
    <source src="https://cdn-shop.adafruit.com/product-videos/1024x768/2435-05.mp4">
    <img src="https://cdn-shop.adafruit.com/product-videos/1024x768/2435-05.jpg">
  </video>
</a>

???

most common form is as a strip

---

### other types of electro-magic lights

- 12v single-color LED strips
- El-Wire
- El-Plate
- ???

---

### how do you get started?

there are 3 major parts to the system:

1. LEDs
1. controller
1. power source

---

## how do you control the LEDs?

to control your heap of LEDs, you will use a micro-controller (a small computer) to send messages over a wire to the first LED, who will relay extra messages to the next LED, and so on.

---

### micro-controller

we will be using the popular Ardunio flavor of micro-controllers.

---

### [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface) (Serial Peripheral Interface)

<img src="https://upload.wikimedia.org/wikipedia/commons/e/ed/SPI_single_slave.svg" />

<img src="https://a.pololu-files.com/picture/0J6577.600.png?f2071ae9f33b8071ff69dd3a118b7ef1" />

???

reference: reference: https://www.pololu.com/product/2552

---

### Pixel bits

<img src="https://a.pololu-files.com/picture/0J6578.600.jpg?43cdc8b658def752351be635ab28978e" />

???

reference: https://www.pololu.com/product/2552

---

### [FastLED](http://fastled.io/)

```
#include <FastLED.h>

#define NUM_LEDS 60
#define DATA_PIN 6

CRGB leds[NUM_LEDS];

void setup () { 
  FastLED.addLeds<APA102>(leds, NUM_LEDS);
}

void loop () {
  leds[0] = CRGB::Red; 
  FastLED.show(); 
  delay(30); 
}
```

---

### [HSV](https://en.wikipedia.org/wiki/HSL_and_HSV)

<img src="https://upload.wikimedia.org/wikipedia/commons/3/33/HSV_color_solid_cylinder_saturation_gray.png" />

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

## how to connect to/from the LEDs?

we will need a way to connect from the controller to the LEDs,

and from each chain of LEDs to the next chain.

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

we will need a way to power the LEDs, they are very bright!

---

### power usage

each LED uses up to 60mA when white at full brightness.

in practical use, when not using white, we use 20mA as a rule of thumb, with lower brightnesses even lower.

```
60 pixels × 20 mA ÷ 1,000 = 1.2 Amps minimum
```


???

references:

- https://www.pololu.com/product/2552
- https://cdn-shop.adafruit.com/datasheets/APA102.pdf
- https://learn.adafruit.com/adafruit-neopixel-uberguide/powering-neopixels

---

### power injection

<img src="https://cdn-learn.adafruit.com/assets/assets/000/010/715/medium800/leds_brownout.jpg" />

<img src="https://cdn-learn.adafruit.com/assets/assets/000/010/716/medium800/leds_nobrown.jpg" />

---

### reducing power use

- each pixel is actually 3 LEDs: red + green + blue
  - displaying red only uses 1/3 the power
  - displaying purple (red + blue) uses 2/3 the power
  - displaying white uses 3/3 the power
- not every pixel must be on at all times!

???

reference: https://learn.adafruit.com/sipping-power-with-neopixels

---

### 5v power supply

---

### batteries



---

### 12v battery + dc step-down (buck) converter

---

### 18650 batteries

---

### aa batteries

---
class: center

## how do you get started?

---

### what parts do we need?

there are 3 major parts to the system:

1. LEDs
1. controller
1. power source

---

### beginner parts

- LEDs: start with LED strips
- LED connector: start with JST connectors
- controller: start with Teensy
- power source:
  - if small, use usb power pack
  - if large, use deep cycle battery

---

### where to source parts

- LEDs: Adafruit or AliExpress
- LED connector: Adafruit or Amazon or AliExpress
- controller: [NiceGear](https://nicegear.nz/product/teensy-lc)

---

### 


---

---

# thanks

=^.^=

???

thanks for your attention

i barely even scratched the surface

if you want to learn more, then get amongst!
