## Docker 환경 설정
### test 및 시연 환경
<li>OS : webOS OSE 2.18.0.g-unofficial</li>
<li>docker version : Docker version 20.10.8, build 62eae52c2a</li>

### 전체 초기 설정
기본적으로 ares-setup-device에서 자신의 webOS가 default로 설정되어 있음을 전제로 하고 있음을 알려드립니다.

```bash
ares-shell

mkdir /media/images
chmod 777 /media/images # 사진을 저장하기 위해서 권한 설정

systemctl start docker

docker login # 자신의 docker 계정으로 login하기

docker pull yun1211/tesseract
docker run -d --name tesseract -v /media/images:/root/images yun1211/tesseract sleep infinity

docker exec -it tesseract /bin/bash
```
