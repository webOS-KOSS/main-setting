## Arduino ESP32 환경 설정
### test 및 시연 환경
<li>OS : Ubuntu 20.04.5 LTS</li>
<li>IDE : Arduino 1.8.19</li>
<li>Device : FireBeetle Board-ESP32(V3.0)</li>

### ESP32 초기 설정

![환경 설정](settings.png)
<br/>
1. 파일 -> 환경설정

![추가적인 보드 매니저 URLs](managers.png)
<br/>
2. 추가적인 보드 매니저 URLs에 https://git.oschina.net/dfrobot/FireBeetle-ESP32/raw/master/package_esp32_index.json 추가

![보드 매니저](boardmanager.png)
<br/>
3. 툴 -> 보드 -> 보드 매니저...

![esp32 install](esp32.png)
<br/>
4. 타입 = Contributed -> esp32 검색 -> esp32 by Espressif Systems 버전 2.0.4 설치

--- 
### FireBeetleESP32 초기 설정
1. 툴 -> 보드 -> ESP32 -> ESP32 Dev Module
