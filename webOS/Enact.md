## Enact 환경 설정
### test 및 시연 환경
<li>OS : Ubuntu 20.04.5 LTS</li>
<li>npm version : 16.17.0</li>
<li>yarn version : 1.22.19</li>
<li>ENACT-CLI version : 5.0.1</li>

### 전체 초기 설정

```bash
npm install -g @enact/cli
```
+) webapp을 설치했는데 화면이 나타나지 않는다면 난다면 시도해보는 것을 추천드립니다

--- 
### webapp 초기 설정
기본적으로 ares-setup-device에서 자신의 webOS가 default로 설정되어 있음을 전제로 하고 있음을 알려드립니다.

```bash
npm install
yarn install

npm run pack-p
ares-package dist -o ipk

ares-install ipk/<app_name>
```
혹은

```bash
sh setup.sh
```
