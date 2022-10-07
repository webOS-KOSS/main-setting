## Enact & Service
### test 및 시연 환경
<li>OS : Ubuntu 20.04.5 LTS</li>
<li>npm version : 16.17.0</li>
<li>yarn version : 1.22.19</li>
<li>enact-cli version : 5.0.1</li>
<li>ares-cli version : 2.3.1</li>

---
### 전체 초기 설정

```bash
npm install -g @enact/cli
npm install -g @webosose/ares-cli 
```
+) webapp을 설치했는데 화면이 나타나지 않는다면 난다면 enact/cli 재설치를 시도해보는 것을 추천드립니다

--- 
### webapp 초기 설정
기본적으로 ares-setup-device에서 자신의 webOS가 default로 설정되어 있음을 전제로 하고 있음을 알려드립니다.
<br><br>
#### app 설정

```bash
npm install
yarn install

npm run pack-p
```
<br>

#### service 설정

```bash
npm install
```

#### application install

```bash
ares-package <app 파일>/dist <service 파일>
ares-install <ipk 파일>
```
