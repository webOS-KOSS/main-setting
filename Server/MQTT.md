## MQTT Broker
### TEST 및 시연 환경
<li>환경 : AWS EC2</li>
<li>AMI : ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-20220609</li>
<li>인바운드 규칙 : {포트 범위 : 1883}, {프로토콜 : TCP}, {원본 : 0.0.0.0/0}</li>
<li>사용자 데이터 : </li>

```bash
#!/bin/bash
apt update -y
apt upgrade -y
apt install mosquitto -y
apt install mosquitto-clients -y
ufw disable
echo "listener 1883" >> /etc/mosquitto/mosquitto.conf
echo "allow_anonymous true" >> /etc/mosquitto/mosquitto.conf
systemctl restart mosquitto.service
```
---
### MQTT Broker IP
개인 AWS EC2로 설정시 해당 인스턴스의 퍼블릭 IPv4를 사용하면 된다.
우리 팀의 AWS EC2와 같은 경우에는 3.34.5.104:1883으로 MQTT Broker를 사용하기로 하였다.
