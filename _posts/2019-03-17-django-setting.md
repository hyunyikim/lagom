---
layout: post
title: Django 세팅
categories:
- django
---
#### Django 특징
- MVC 패턴 기반 MVT : Model 데이터, View 컨트롤러, Template 화면
- 객체관계매핑(Object-Relational Mapping) : 직접 SQL 언어로 데이터를 요청할 필요 없이 객체(클래스)를 사용해 데이터를 처리
- 자동으로 구성되는 관리자 화면  
- 우아한 URL 설계 : 정규표현식으로 복잡한 URL 표현 가능, 함수와 1:1 매핑
- 자체 템플릿 시스템
- 캐시 시스템 : 캐시 단위를 페이지부터 사이트 전체, 특정 뷰의 결과, 템플릿의 일부 영역만 지정할 수 있다
- 소스 변경사항 자동 반영 : .py 파일의 변경 여부를 감시하고 있다가 변경이 되면 변경 내역을 바로 반영한다
- 웹사이트에 대한 전체 프로그램이 프로젝트이고, 모듈화된 단위 프로그램이 애플리케이션이라고 부른다

&nbsp;  
#### Settings.py
- ALLOWED_HOSTS 항목 지정
  * DEBUG=True는 개발 모드, False는 운영모드
  * 운영 모드라면 ALLOWD_HOSTS에 반드시 서버의 ID나 도메인을 지정해야 한다
  * 개발 모드라면 값을 지정하지 않아도 ['localhost', '127.0.0.1'] 로 간주
- 프로젝트에 포함되는 애플리케이션 등록
  * INSTALLED_APPS에 애플리케이션 추가
  * 모듈 경로부터 앱 생성시 자동으로 생성된 apps.py 파일에 Config까지 등록
- 데이터베이스 엔진
  * 디폴트는 SQLite3
  * 다른 DB로 변경하고 싶다면 settings.py 파일에서 수정
- 타임존 지정
  * 최초에는 세계표준시(UTC)
  * 한국 시간으로 변경
  * USE_TZ=True로 설정하면 장고가 알아서 시간대 조정(일광절약시간제를 사용하지 않는다면 False로 설정하는게 편리)

```python
# settings.py
DEBUG = True
ALLOWED_HOSTS = ['localhost', '127.0.0.1']

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'polls.apps.PollsConfig',
]

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}

TIME_ZONE = 'Asia/Seoul'
```

&nbsp;  
#### 기본 테이블 생성
- DB에 변경사항이 있을 때 반영해주는 명령어인 migrate 실행
- 장고는 사용자와 그룹 테이블이 필요하다는 가정하게 설계 되었기 때문에 명령어 실행이 필요
- 실행 결과로 SQLite3의 DB 파일인 db.sqlite3 파일 생성

&nbsp;  
#### 장고 서버 실행
- 장고는 간단한 테스트용 웹서버로 runserver 제공
- runserver용으로 별도 cmd창 열어서 사용하는게 편리

&nbsp;  
#### 장고 기본 폴더구조
```
(myvenv) C:\Users\Hyunyi\djangoProject>tree /F mysite
OS 볼륨에 대한 폴더 경로의 목록입니다.
볼륨 일련 번호가 00000091 EA99:DCE0입니다.
C:\USERS\HYUNYI\DJANGOPROJECT\MYSITE
│  db.sqlite3
│  manage.py
├─mysite
│  │  settings.py
│  │  urls.py
│  │  wsgi.py
│  └─ __init__.py
└─polls
    │  admin.py
    │  apps.py
    │  models.py
    │  tests.py
    │  views.py
    │  __init__.py
    ├─templates
    │  └─polls
    │          detail.html
    │          index.html
    │          results.html
    └─migrations
       └─__init__.py  
```

&nbsp;  
#### 가상환경 설치시 pycharm에서 경로 설정하기
- cmd에서 장고 프로젝트를 만들고 파이참에서 열었는데 파이참이 장고 모듈을 찾지 못했다.
- cmd에서 가상환경을 설치하고 그 위에 장고를 설치했는데 파이참에서는 그 가상환경을 찾지 못해서 그랬던 것
- 파이참에서 가상환경 안에 있는 python.exe 파일을 인터프리터로 설정해주면 해결 
&nbsp;  
---
출처 - 책 [파이썬 웹프로그래밍](http://www.hanbit.co.kr/store/books/look.php?p_code=B4329597070)
