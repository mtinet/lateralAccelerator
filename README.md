# lateralAccelerator


 
***
      아두이노, GY-86, Common Cathode RGB LED,  일반 LED를 사용한 횡G 측정용 키트입니다.  
      (GY-86 : MPU6050 + HMC5883L(지자기:Magneto) + MS5611(기압계:Barometer))
***

1. 자전거와 자동차, 오토바이 등에 활용이 가능할 것 같구요. 차량의 종류에 따라서 감도 조정을 하면 됩니다. 자동차의 실내에서 가속도나 감속도를 파악하는 용도로 사용해도 될 것 같군요. 

2. 감도 조정은 927~1022째 줄 사이의 수치를 수정하면 됩니다.  

3. 현재 세팅은 gy-86의 x축을 기준으로 중력가속도를 16이라 했을 때, 다음과 같이 세팅되어 있습니다. 

 - 중력가속도 1을 기준으로 같은값으로 왼쪽이나 오른쪽으로 기울이면 기울기에 따라 같은 갯수의 붉은 LED가 점멸합니다.
 - 가속과 감속을 감지하여 가운데의 RGB LED가 가속 시에는 파란색으로 감속 시에는 빨간색으로 바뀝니다.

4. 테스트 영상 링크(사진을클릭하세요.)

[![테스트 영상 링크](https://raw.githubusercontent.com/mtinet/lateralAccelerator/master/20170502_022741.jpg)](https://youtu.be/YjH0g60Ffdg)  


5. 핀배치
 - 회로도  
 ![](https://github.com/mtinet/lateralAccelerator/blob/master/circuit.png?raw=true)  
 
~~~  
- 아두이노 나노와 가속도 센서 연결  
~~~   

| 아두이노 나노  | GY-86|
| :------------: | :-----------: |
| VCC           |   VCC       |
| GND           |   GND       |
| SDA           |   A4        |
| SCL           |   A5        |

~~~  
- 아두이노 나노와 가속도 센서 연결    
(아두이노 나노에 5V핀이 하나뿐이어서 2번 핀을 항상 5V가 출력되도록 설정했습니다.)  
~~~  

| 아두이노 나노  | LED |
| :------------: | :-----------: |
|   GND       |   GND         |
|   13        |   left 5       |
|    12       |   left 4       |
|   11        |   left 3        |
|    10       |   left 2        |
|   9         |   left  1        |
|    8        |   right 1        |
|    7        |   right 2        |
|    6        |   red(RGB LED)  |
|    5        |   blue(RGB LED)   |
|    4        |   right 3        |
|    3        |   right 4        |
|    2        |   right 5        |
  
6. 안내
- [일반버전](https://github.com/mtinet/lateralAccelerator/blob/master/lateralAccelerator.ino)은 가속도에 따라 LED가 계속 켜져있습니다.  
- [플래시버전](https://github.com/mtinet/lateralAccelerator/blob/master/lateralAcceleratorFlash.ino)은 가속도에 따라 LED 번쩍거립니다.  
- [Non Serial Print 버전](https://github.com/mtinet/lateralAccelerator/blob/master/lateralAcceleratorNonSerial.ino)은 Serial Print를 하지 않아 시스템 처리속도가 좀 더 예민합니다.  
