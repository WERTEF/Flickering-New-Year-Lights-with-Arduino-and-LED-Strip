# Flickering-New-Year-Lights-with-Arduino-and-LED-Strip
Simple code to create flickering New Year lights using Arduino and an LED strip.
#include <FastLED.h>

#define LED_PIN     6
#define NUM_LEDS    30
#define BRIGHTNESS  50

CRGB leds[NUM_LEDS];

void setup() {
    FastLED.addLeds<NEOPIXEL, LED_PIN>(leds, NUM_LEDS);
    FastLED.setBrightness(BRIGHTNESS);
}

void loop() {
    for (int i = 0; i < NUM_LEDS; i++) {
        leds[i] = CRGB::Red;
        FastLED.show();
        delay(50);
        leds[i] = CRGB::Black;
    }
    delay(500);
}
