# Fedeer-for-students

```c++
// Motor shield использует четыре контакта 4, 5, 6, 7 для управления моторами 
// 4 и 7 — для направления, 5 и 6 — для скорости
#define SPEED_1      5 
#define DIR_1        4
 
#define SPEED_2      6
#define DIR_2        7
 
#define dot  8


void setup() {
  // настраиваем выводы платы 4, 5, 6, 7 на вывод сигналов 
  for (int i = 4; i < 8; i++) {     
    pinMode(i, OUTPUT);
  }
  pinMode (dot, INPUT);
} 
 
void loop() {

  int btnVal = digitalRead(dot);



if (btnVal == 0)
{
  // устанавливаем направление мотора «M2» в одну сторону
  digitalWrite(DIR_2, HIGH);
  // включаем второй мотор на максимальной скорости
  analogWrite(SPEED_2, 80);
     // устанавливаем направление мотора «M1» в одну сторону
  digitalWrite(DIR_1, HIGH);
  // включаем мотор на максимальной скорости
  analogWrite(SPEED_1, 80);
  // ждём одну секунду
  delay(900);

  analogWrite(SPEED_1, 0);
  analogWrite(SPEED_2, 0);
  delay(2000);

 // устанавливаем направление мотора «M2» в одну сторону
  digitalWrite(DIR_2, LOW);
  // включаем второй мотор на максимальной скорости
  analogWrite(SPEED_2, 80);
     // устанавливаем направление мотора «M1» в одну сторону
  digitalWrite(DIR_1, LOW);
  // включаем мотор на максимальной скорости
  analogWrite(SPEED_1, 80);
  // ждём одну секунду
  delay(900);

   analogWrite(SPEED_1, 0);
  analogWrite(SPEED_2, 0);
 

  }
  else {



  analogWrite(SPEED_1, 0);
  analogWrite(SPEED_2, 0);
  }
 
 
}

```
