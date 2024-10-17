# 차량 공유업체의 차량 파손 여부 분류하기

> **주제**: CNN, VGG-16  
> **기간**: 2023.11.01

## 💻 학습 기술 스택

![VGG-16](https://img.shields.io/badge/VGG--16-purple?style=flat-square) [![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/) [![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/) [![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com/)

## 📝 내용

1. 데이터 전처리
2. CNN 모델링
3. 데이터 증강 & 전이학습 (VGG16)

## 💡 VGG-16

VGG-16은 16개 계층으로 구성된 컨벌루션 신경망이다.  
ImageNet 데이터베이스의 백만 개의 영상에 대해 사전 훈련된 신경망이다.  
전이학습을 통해 특정 이미지(차량 파손 여부)를 재훈련하고 미세조정을 거쳐 활용된다.
