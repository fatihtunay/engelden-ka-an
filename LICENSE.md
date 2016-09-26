const int trig = 10;
const int eco = 8;
int sure;
int m;


const int sol_i = 2;
const int sol_g = 3;
const int sag_i = 4;
const int sag_g = 5;

void setup() {
  pinMode (trig , OUTPUT);
  pinMode (eco , INPUT);
  pinMode (sol_i, OUTPUT);
  pinMode (sol_g, OUTPUT);
  pinMode (sag_i, OUTPUT);
  pinMode (sag_g, OUTPUT);
  Serial.begin (9600);

}

void loop() {

  digitalWrite (trig , HIGH);
  delayMicroseconds(1000);
  digitalWrite (trig , LOW);
  sure = pulseIn ( eco , HIGH);
  m = (sure / 2) / 28.5;
  Serial.print(m);



  if (m <= 30);
  {
    delay(50);
    digitalWrite (sol_i , LOW);
    digitalWrite (sol_g , HIGH);
    digitalWrite (sag_i , HIGH);
    digitalWrite (sag_g , LOW);
    delay(150);
  }
  else
  {
    digitalWrite (sol_i , HIGH);
    digitalWrite (sol_g , LOW);
    digitalWrite (sag_i , HIGH);
    digitalWrite (sag_g , LOW);
  }

}
