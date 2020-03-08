### Mint Docker 설치

1. 기존 Docker 삭제

    sudo apt-get remove docker docker-engine docker.io

2. 필요 package 설치

    sudo apt-get update && sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common

3. 도커의 공식 GPG 키와 패키지 저장소 추가 

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    sudo add-apt-repository "deb https://download.docker.com/linux/ubuntu bionic stable"

4. 도커 패키지 검색 확인

    sudo apt-get update && sudo apt-cache search docker-ce

5. 도커 CE 에디션 설치

    sudo apt-get update && sudo apt-get install docker-ce

6. 사용자 도커그룹 추가

    sudo usermod -aG docker $USER



### Nvidia Docker 설치

1. 저장소 추가

curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -

##### 기존 우분투 방식으로 진행이 안되서
    
    distribution=$(. /etc/os-release;echo $ID$VERSION_ID)

    curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list


민트에서는 강제적으로 경로 지정

curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -

curl -s -L https://nvidia.github.io/nvidia-docker/ubuntu18.04/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

sudo apt-get update


2. Nvidia Docker 설치

sudo apt-get install -y nvidia-container-toolkit

sudo systemctl restart docker
