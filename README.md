# Auto Server Setup Script

Shell Script for AWS Lightsail Server Setup. Written By [강동주](https://github.com/biniprc). Inspired By [황준우](https://github.com/capollux)

## 1. AWS Lightsail

**Ubuntu 16.04 LTS**로 Lightsail Instance를 생성한다. 본 스크립트는 해당 OS를 바탕으로 작성되었다.

## 2. Lightsail 설정 (Server)

### 2.1. Auto Server Setup Script 가져오기

`git clone` 명령어로 **server_setup**스크립트를 가져온다. 지금 보고 있는 이 문서의 repository이다.

```console
$ git clone https://github.com/classjohn/server_setup.git
```

### 2.2. Rails Install Script 실행하기

#### 2.2.1. Script 실행 권한

서버 설정을 매우 편리하게 해주기 위하여 script를 작성하였다. 아까 받은 Script를 실행하면 모든 설정이 자동으로 될 것이다. 지금은 단순한 text 파일인데, 이 파일을 실행 가능한 script 파일로 바꿔주기 위하여 해당 파일에 실행 권한을 부여하자.

```console
$ sudo chmod u+x ~/server_setup/*.sh
```

#### 2.2.2. setup.sh 실행

실행 권한이 부여되면 실행을 해보자. 우선 `setup.sh` 먼저.

```console
$ ~/server_setup/setup.sh
```

#### 2.2.3. shell 새로고침

`setup.sh`에서 많은 것들을 설치하였는데, 그것들을 사용하기 위하여 shell을 refresh 해주자. 가끔 프로그램을 설치하고 컴퓨터를 재부팅 해주는 것과 같은 이유이다.

```console
$ exec $SHELL
```

#### 2.2.4. Ruby 설치

`setup.sh`를 통해 우리는 Rails에 필요한 모든 프로그램과 `rbenv`를 설치해주었다. Ruby의 경우 rbenv를 통해 직접 설치해주어야 한다.

```console
$ rbenv install 2.3.5
$ rbenv global 2.3.5
$ gem install bundler
$ rbenv rehash
```

#### 2.2.5. Rails 설치

마지막으로 rails까지 설치를 완료하자.

```console
$ gem install rails -v 4.2.9
```

### 3.1. Nginx & Passenger Install Script 실행하기

Web Server인 **Nginx**와 Application Server인 **Passenger**를 설치하는 script를 구동하자

```console
$ ~/server_setup/nginx.sh
```
