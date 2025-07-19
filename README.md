# sequential-leds-with-button
An Arduino project that controls 3 LEDs using a push button. When pressed, the built-in LED and two others (on pins 8 and 7) blink in sequence with 1-second delays. Uses internal pull-up for the button. Great for beginners learning digital input/output.
# Push Button Controlled LEDs with Arduino

## Description
مشروع أردوينو للتحكم بثلاث لمبات LED باستخدام زر Push Button. عند الضغط على الزر، تضيء اللمبات بالتسلسل مع فواصل زمنية مقدارها ثانية واحدة. يستخدم المشروع المقاومة الداخلية للزر (INPUT_PULLUP) لتبسيط التوصيل.

## Hardware
- Arduino UNO
- Push Button
- 2x LEDs (مثلاً أحمر وأخضر)
- 2x مقاومات 220 أوم
- أسلاك توصيل وبرد بورد

## Wiring
- زر متصل بالمنفذ 2 و GND
- LED 1 متصل بالمنفذ 8 عبر مقاومة 220 أوم
- LED 2 متصل بالمنفذ 7 عبر مقاومة 220 أوم
- LED المدمج (Built-in LED) يستخدم المنفذ LED_BUILTIN

## Usage
1. وصل المكونات حسب التوصيل.
2. ارفع كود `push_button_led.ino` على لوحة Arduino.
3. اضغط على الزر لمشاهدة اللمبات تضيء بالتسلسل.

## Code Snippet

```cpp
const int buttonPin = 2;
const int ledBuiltin = LED_BUILTIN;
const int led1 = 8;
const int led2 = 7;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP);
  pinMode(ledBuiltin, OUTPUT);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
}

void loop() {
  if (digitalRead(buttonPin) == LOW) {
    digitalWrite(ledBuiltin, HIGH);
    delay(1000);
    digitalWrite(ledBuiltin, LOW);
    delay(1000);

    digitalWrite(led1, HIGH);
    delay(1000);
    digitalWrite(led1, LOW);
    delay(1000);

    digitalWrite(led2, HIGH);
    delay(1000);
    digitalWrite(led2, LOW);
    delay(1000);
  }
}
