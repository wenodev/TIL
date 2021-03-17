# Ubuntu 20.04 에서 Docker 설치하기
### 해당 글은 공식문서를 참고하였습니다.
### 공식문서 : https://docs.docker.com/engine/install/ubuntu


## 필요조건
아래의 64-bit version이 필요하다.
- Ubuntu Groovy 20.10
- Ubuntu Focal 20.04 (LTS)
- Ubuntu Bionic 18.04 (LTS)
- Ubuntu Xenial 16.04 (LTS)

## 오래된 버전 삭제
'docker', 'docker.io', or 'docker-engine' 라고 불리는 오래된 버전의 docker가 설치되어있으면 아래의 코드로 삭제하라
```
 sudo apt-get remove docker docker-engine docker.io containerd runc
```
## Repository를 이용한 설치
Docker엔진을 설치하기 전에 Docker Repository를 설치해야한다. 그다음에 Repository로부터 설치를 하고 업데이트를 할 수 있다.
```
// apt-get 최신화
 sudo apt-get update 
 
 // https를 통해 저장소를 사용하기 위한 설정
 sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
// Docker’s official GPG key 추가
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 
 // 안정적인 Repository 설치하기
  echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
## Docker 옌진 설치
```
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io
```
## Docker가 정상적으로 설치되었는지 확인
``` 
sudo docker run hello-world
```

