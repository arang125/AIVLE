# Aivle 스쿨 지원 질문, 답변 챗봇 만들기

> **주제**: NLP  
> **기간**: 2023.10.30 ~ 2023.10.31

## 💻 학습 기술 스택

[![fastText](https://img.shields.io/badge/fastText-E31823?style=flat-square&logoColor=white)](https://fasttext.cc/) [![NLTK](https://img.shields.io/badge/NLTK-154F5B?style=flat-square&logoColor=white)](https://www.nltk.org/) ![MeCab](https://img.shields.io/badge/MeCab-000?style=flat-square&logoColor=white) [![KoNLPy](https://img.shields.io/badge/KoNLPy-blue?style=flat-square)](https://konlpy.org/) [![Okt](https://img.shields.io/badge/Okt-skyblue?style=flat-square)](https://github.com/open-korean-text/open-korean-text) [![GENSIM](https://img.shields.io/badge/GENSIM-001A5E?style=flat-square&logoColor=white)](https://radimrehurek.com/gensim/) [![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/) [![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/) [![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com/)

## 📝 내용

1. 탐색적 데이터 분석
2. 형태소 분석
3. Word2Vec 임베딩 벡터 기반 ML 모델링
4. LSTM
5. FastText

## 📊 데이터

-   형태: 텍스트데이터
-   출처: 에이블스쿨

## 💡 fastText

fastText는 단어 안에 단어(subword)를 고려하여 벡터화하고 학습하는 모델이다.  
Word2Vec에 비해 사전에 없는 단어라도 내부단어(subword)를 통해 유추-내부단어가 다른 단어와의 유사도를 계산하여-를 할 수 있는 유연성을 가진다.
