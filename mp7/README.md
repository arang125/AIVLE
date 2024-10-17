# 수어-ChatGPT

> 수어 사진을 MLflow에서 관리하는 모델을 통해 예측한 후 GPT로 응답 문장을 생성한다

**주관** : [KT](https://aivle.kt.co.kr/home/main/indexMain)　　　　　**소속** : KT 에이블스쿨 4기 수도권 1반 3조　　　　　**프로젝트 기간** : 2023-11-28 ~ 2024-12-07

## 🚩 목차

-   [🛠️ 기술 스택](#%EF%B8%8F-기술-스택)
-   [💡 주요 기능](#-주요-기능)
-   [🎨 UI](#-ui)
-   [📂 프로젝트 구조](#-프로젝트-구조)
-   [🚀 실행 방법](#-실행-방법)

## 🛠️ 기술 스택

[![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)](https://mlflow.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://www.tensorflow.org)
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org)
[![OpenAI](https://img.shields.io/badge/Openai-412991?style=flat-square&logo=openai)](https://platform.openai.com)
[![AWS](https://img.shields.io/badge/AWS-%23232F3E?style=flat-square&logo=amazonaws&logoColor=white)](https://aws.amazon.com/ko)

## 💡 주요 기능

1.  Django 앱 페이지 구현

2.  ChatGPT API 연결

3.  MLflow로 모델 관리

4.  AWS로 서버 배포

## 🎨 UI

![홈페이지](https://github.com/Aivle4-Team3/Mini-project-7/assets/26417221/78c2bf7a-3160-4abe-8bd9-02e22f213e0e)

<img alt="GPT질문" src="https://github.com/Aivle4-Team3/Mini-project-7/assets/26417221/7c626cac-8bc2-41da-92e8-628aa756d1b0" style="width:49%;">
<img alt="수어질문" src="https://github.com/Aivle4-Team3/Mini-project-7/assets/26417221/0b66dc04-0d5f-4d68-b55b-b067ca1ca758" style="width:49%;">

## 📂 프로젝트 구조

<details>
<summary>열기</summary>

```
Mini-project-7
├─ .gitignore
├─ accounts
│  ├─ admin.py
│  ├─ apps.py
│  ├─ forms.py
│  ├─ migrations
│  │  ├─ 0001_initial.py
│  │  └─ __init__.py
│  ├─ models.py
│  ├─ templates
│  │  └─ registration
│  │     ├─ login.html
│  │     ├─ passsword_reset_confirm.html
│  │     ├─ passsword_reset_form.html
│  │     ├─ password_change_done.html
│  │     ├─ password_change_form.html
│  │     ├─ profile.html
│  │     └─ signup.html
│  ├─ tests.py
│  ├─ urls.py
│  ├─ views.py
│  └─ __init__.py
├─ db.sqlite3
├─ manage.py
├─ mlflow.db
├─ mysite
│  ├─ asgi.py
│  ├─ settings.py
│  ├─ urls.py
│  ├─ wsgi.py
│  └─ __init__.py
├─ README.md
├─ requirements.txt
├─ requirements_linux.txt
├─ selfchatgpt
│  ├─ admin.py
│  ├─ apps.py
│  ├─ migrations
│  │  └─ __init__.py
│  ├─ models.py
│  ├─ static
│  │  └─ abc
│  │     └─ style.css
│  ├─ templates
│  │  └─ selfgpt
│  │     ├─ index.html
│  │     └─ result.html
│  ├─ tests.py
│  ├─ urls.py
│  ├─ views.py
│  └─ __init__.py
├─ selfsignlanguagetochatgpt
│  ├─ admin.py
│  ├─ apps.py
│  ├─ migrations
│  │  ├─ 0001_initial.py
│  │  └─ __init__.py
│  ├─ models.py
│  ├─ static
│  │  └─ selflanguage
│  │     ├─ chat_style.css
│  │     └─ style.css
│  ├─ templates
│  │  └─ selflanguagechat
│  │     ├─ index.html
│  │     └─ result.html
│  ├─ tests.py
│  ├─ urls.py
│  ├─ views.py
│  └─ __init__.py
├─ static
│  └─ css
│     └─ styles.css
└─ templates
   ├─ index.html
   └─ layout.html

```

</details>

## 🚀 실행 방법

1.  요구 패키지 설치  
    `pip install -r requirements.txt`
2.  환경 변수 입력 key.config 파일을 루트 폴더 아래에 생성

```Python
CHATGPT_KEY= # https://platform.openai.com/settings/profile?tab=api-keys
```

3. 데이터베이스로 장고ORM 마이그레이션  
   `python manage.py migrate`
4. 장고 서버 실행  
   `python manage.py runserver`
5. 관리자 계정 생성  
   `python manage.py createsuperuser`
