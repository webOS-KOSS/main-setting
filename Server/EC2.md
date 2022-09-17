## EC2
### TEST 및 시연 환경
<li>환경 : AWS EC2</li>
<li>AMI : ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-20220609</li>
<li>인바운드 규칙 : </li>

```javascript
{포트범위 : 22}, {프로토콜 : TCP}, {원본 : 0.0.0.0/0} // shell
{포트범위 : 1883}, {프로토콜 : TCP}, {원본 : 0.0.0.0/0} // MQTT
{포트범위 : 8080}, {프로토콜 : TCP}, {원본 : 0.0.0.0/0} // Express Web Server
```
<li>사용자 데이터 : </li>

```bash
#!/bin/bash
apt update -y
apt upgrade -y
apt install mosquitto -y
apt install mosquitto-clients -y
apt install -y nodejs
apt install -y npm
apt install git -y
npm install -g nodemon

ufw disable
echo "listener 1883" >> /etc/mosquitto/mosquitto.conf
echo "allow_anonymous true" >> /etc/mosquitto/mosquitto.conf
systemctl restart mosquitto.service

cd /home/ubuntu
git clone https://github.com/webOS-KOSS/post_backend.git
cd post_backend
touch .env
echo "MONGO_URL=\"mongodb+srv://yun1211:yunbird1211@cluster0.znfuk.mongodb.net/Cluster0?retryWrites=true&w=majority\"" >> .env
```
---
### MQTT Broker IP
개인 AWS EC2로 설정시 해당 인스턴스의 퍼블릭 IPv4를 사용하면 된다.<br/>
우리 팀의 AWS EC2와 같은 경우에는 3.35.48.163:1883으로 MQTT Broker를 사용하기로 하였다.

---
### Express Web Server
개인 MongoDB로 설정시 해당 인스턴스의 퍼블릭 IPv4를 사용하면 된다.<br/>
<a href="3.35.48.163:8080">3.35.48.163:8080</a>으로 아파트 게시판 web Server에 접속할 수 있다.