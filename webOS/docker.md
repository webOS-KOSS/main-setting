## docker 환경 설정
### test 및 시연 환경
<li>OS : webOS OSE 2.17.0</li>
<li>docker version : </li>

### 전체 초기 설정
기본적으로 ares-setup-device에서 자신의 webOS가 default로 설정되어 있음을 전제로 하고 있음을 알려드립니다.

```bash
ares-shell

mkdir /home/root/videos

systemctl start docker
docker pull ymw0407/tesseract
docker run -v /home/root/videos: --name ymw0407/tesseract tesseract sleep infinity
docker exec -it tesseract /bin/bash
```
