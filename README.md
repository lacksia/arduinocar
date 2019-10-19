# 1. 유튜브 

https://youtu.be/kyGNYXmMNtE

# 2. 실습에 대한 설명

1.앱 인벤터로 조종앱 만들기

https://user-images.githubusercontent.com/50895677/67139097-0a5ec300-f287-11e9-83cc-1d494a384130.png

2.조종앱 휴대폰에 다운로드

3.아두이노 코딩

#include <Servo.h>

Servo sr, sl;

void setup() {

  Serial.begin(9600);
  
  sr.attach(13); sl.attach(12);
  
}

void loop() {

  if (Serial.available()) {
  
   char b[2];  //pitch b[0], roll b[1]
    
   int p, r;
    
   Serial.readBytes(b, 2);
    
   p = b[0] * 3; // 피치값 -90~0~90, 전 후진  // 1500-270 ~ 1500+270
    
   r = b[1];        // 롤 값 -90~0~90, 좌 우회전  // 1500-90 ~ 1500+90
    
   sr.write(1500 + p - r);
    
   sl.write(1500 - p - r);
    
   Serial.write('1');
   
 }
 }

4.블루투스 페어링

# 3. 소감

저희가 배운 앱 인벤터를 이용하여 만들어낸 앱과 집적 배운 아두이노 코드를 사용하여 블루투스로 연결해 Abot이 저의 뜻대로 

움직이는 걸 보는게 감회가 새로웠고 블루투스의 개념에 대해 한층 더 잘 이해할 수 있는 계기가 되었습니다. 앞으로도 유용히 

이용 할 수 있도록 더 학습하도록 하겠습니다.

