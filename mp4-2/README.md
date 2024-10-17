# 1대1 문의 내용 유형 분류기

> **주제**: NLP  
> **기간**: 2023.10.16 ~ 2023.10.18

## 💻 학습 기술 스택

[![NLTK](https://img.shields.io/badge/NLTK-154F5B?style=flat-square&logoColor=white)](https://pandas.pydata.org/) [![GENSIM](https://img.shields.io/badge/GENSIM-001A5E?style=flat-square&logoColor=white)](https://radimrehurek.com/gensim/) ![MeCab](https://img.shields.io/badge/MeCab-000?style=flat-square&logoColor=white) [![KoNLPy](https://img.shields.io/badge/KoNLPy-blue?style=flat-square)](https://konlpy.org/) [![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/) [![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/) [![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com/)

![wordcloud](https://github.com/NarciSource/Aivle--MiniProject-4-2/assets/26417221/2f3943b3-a88f-4e41-8ca9-f3b251f25214)

## 📝 내용

1. 텍스트 분석
2. 데이터 전처리
    - 증강
    - N-grams
    - Sequence
    - Word2Vec
3. 텍스트 분류
    - ML
    - DNN
    - RNN
    - CNN
    - LSTM

## 📊 데이터

-   형태: 텍스트데이터
-   출처: 에이블스쿨

## 💡 라이브러리

-   **Gensim**: 머신 러닝을 사용하여 토픽 모델링과 자연어 처리를 수행
-   **NLTK**: 자연어 처리 및 문서 분석용 패키지
-   **[ktextaug](https://github.com/jucho2725/ktextaug)**: 한국어 텍스트 증강을 위한 노이즈 생성 패키지
    -   자모 분리
    -   모음 변형
    -   음운

## 💡 형태소분석기

-   KoNLPy, MeCab

## 💡 N-grams

N-grams은 통계적 접근의 언어 모델(SLM: Statistical Language Model)로 N개의 연속적인 단어 단위로 끊어서 이를 하나의 토큰으로 간주하고 이용한다.  
연속적인 단어열을 사용함으로써 표현할 수 있는 정보가 증가한다.
