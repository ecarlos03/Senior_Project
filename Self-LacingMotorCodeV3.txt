// ===== declare variables =====
const int forwardPin  = 8;
const int backwardPin = 12;
const int fwdPin  = 9;
const int bckPin = 13;

const int but1pin = 2;  // forward button
const int but2pin = 3;  // backward button
const int but3pin = 4;  // forward button
const int but4pin = 5;  // backward button

int but1;
int but2;
int but3;
int but4;

void setup() {
  pinMode(forwardPin, OUTPUT);
  pinMode(backwardPin, OUTPUT);
  pinMode(fwdPin, OUTPUT);
  pinMode(bckPin, OUTPUT);

  pinMode(but1pin, INPUT_PULLUP);
  pinMode(but2pin, INPUT_PULLUP);
  pinMode(but3pin, INPUT_PULLUP);
  pinMode(but4pin, INPUT_PULLUP);

  // start stopped
  digitalWrite(forwardPin, LOW);
  digitalWrite(backwardPin, LOW);
  digitalWrite(fwdPin, LOW);
  digitalWrite(bckPin, LOW);
}

void loop() {
  but1 = digitalRead(but1pin);
  but2 = digitalRead(but2pin);
  but3 = digitalRead(but3pin);
  but4 = digitalRead(but4pin);

  // Button logic (INPUT_PULLUP: pressed = LOW)
  if (but1 == LOW) {
    digitalWrite(forwardPin, HIGH);
  } else {
    digitalWrite(forwardPin, LOW);
  }

  if (but2 == LOW) {
    digitalWrite(backwardPin, HIGH);
  } else {
    digitalWrite(backwardPin, LOW);
  }
    if (but3 == LOW) {
    digitalWrite(fwdPin, HIGH);
  } else {
    digitalWrite(fwdPin, LOW);
  }

  if (but4 == LOW) {
    digitalWrite(bckPin, HIGH);
  } else {
    digitalWrite(bckPin, LOW);
  }
}