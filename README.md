## KHUropbox

<p align="center"><img width="200" src="static/image/header.png" /></p>

클라우드 플랫폼을 사용한 2019년 1학기 클라우드 컴퓨팅 과목 팀 프로젝트입니다. 팀원 들의 원할한 소통을 위해 영어보다 한국어로 작성되었습니다.



##### Notice

- 새로운 기능 구현 시 branch로 관리 혹은 fork에서 자신 repository에서 구현 후 Pull Request로 합쳐주세요.
- 버그, Trouble Shooting은 Issue를 활용해주세요.



##### 구현 목록(및 예정)

- [x] 로그인, 회원가입  

- [x] 비밀번호 수정

- [x] S3 기반 파일 업로드, 삭제

- [x] AWS 플랫폼 DB 기반(MySQL 예정) migration 연동

- [ ] 외부인과 파일 공유, Session Problem

- [ ] 도커 가상화(Dockerfile) 예정

- [ ] Elastic Beanstalk와 Elastic Load Balancing을 사용한 부하분산처리

- [ ] 게시판 및 댓글 기능, DB 구조화

- [ ] S3에서 파일 이름으로 인한 검색

- [ ] 사용자 마다 Bucket 나누기, 회원가입시 고유 Bucket 생성

- [ ] S3 Bucket에 대한 DB 구조화

- [ ] 대용량 파일 업로드에 대한 aws cognito 설정

  

**추후에 AWS 이용할 때 AWS 키 안올리도록 주의해주세요.**



## Quick Start

```shell
$ git clone https://github.com/khuropbox/khuropbox && cd khuropbox
$ sudo apt install virtualenv python3-pip
$ pip3 install virtualenv

$ ln -s /home/ubuntu/.local/bin/virtualenv virtualenv
$ ./virtualenv env
$ source env/bin/activate

$ pip3 install -r requirement.txt

$ python manage.py migrate
$ python manage.py runserver 0:8000
```



## 개발 환경 설정 방법

1. `Ubuntu Server 16.04 LTS (HVM), SSD Volume Type`으로 ec2를 만듭니다.

2. ec2 보안 그룹의 8000번 포트를 열어 줍니다.

3. `ssh -i your_pem_key.pem ubuntu@server_ip` 

4. `$ git clone -b dev --single-branch https://github.com/khuropbox/khuropbox`

5. `$ sudo apt-get update`

6. `$ sudo apt install virtualenv python3-pip`

7. `$ pip3 install virtualenv`

8. `$ ln -s /home/ubuntu/.local/bin/virtualenv virtualenv`

9. `$ ./virtualenv env`

10. `$ source env/bin/activate`

11. `$ pip3 install -r requirement.txt`

12. `$ vim config.ini`

    ```ini
    [aws]
    AWS_ACCESS_KEY_ID = your_access_key
    AWS_SECRET_ACCESS_KEY = your_secret_access_key
    AWS_STORAGE_BUCKET_NAME = bucket_name
    ```

13. `$ python manage.py migrate`

14. `$ python manage.py runserver 0:8000`

15. 크롬 창에서 `serverip:8000` 으로 접속하면 됩니다.

**개발 시 본인이 맡은 브랜치는 본인의 이니셜로 만들어 개발 후 브랜치로 push후 master 브랜치에는 Pull Request로 주세요.**



## Dependancy

- django==2.1.7
- Pillow==5.4.1
- djangorestframework==3.9.2



## Team Members

- 정다은
- 정의동 
- 정태환(@graykode)
- 조아진