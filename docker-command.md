# Docker 명령어 정리
## 설치 유무 확인
```
docker
```
## 현재 실행중인 Docker확인
```
sudo docker ps
```
## Ubuntu 18.04 이미지 받기
```
sudo docker pull ubuntu:18.04
```
참고 : 하나의 이미지는 여러개의 레이어로 되어있다.
## Ubuntu 18.04 실행
```
sudo docker run -it ubuntu:18.04 bash
sudo docker run -it --name ubuntu ubuntu:18.04 bash // 'ubuntu' 라는 이름으로 실행
```
## 현재까지 실행했던 image 목록
```
sudo docker ps -a
```

## doker 삭제
```
sudo docker rm [name]
```
## docker 다시 실행
```
sudo docker start [name]
```
## docker 중단
```
sudo docker stop [name]
```


