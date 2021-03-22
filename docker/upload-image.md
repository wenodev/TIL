# 만들어진 Docker image를 본인의 DockerRepository로 push하는 방법

1. docker hub 계정만들기 : https://hub.docker.com/signup
2. docker repository 생성 : https://docs.docker.com/docker-hub/repos/
3. 터미널 창에서 docker login 하기
```
sudo docker login
```
4. 2번에서 만든 repository와 연결하기
```
sudo docker tag [IMAGE ID] [계정이름]/[레포이름]:[태그이름]
```
5. 생성된 docker image 확인 : 4번에서 만들어진 IMAGE인지 확인해야한다. (REPOSITORY 확인하면된다)
```
sudo docker images
```
6. Repository에 push하기
```
sudo docker push [계정이름]/[레포이름]:[태그이름]
```
