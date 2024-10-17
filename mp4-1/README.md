# 서울시 공공 데이터 기반 생활인구 예측

> **주제**: 시계열분석, ML, DL  
> **기간**: 2023.10.12

## 💻 학습 기술 스택

[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/) [![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/) [![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas)](https://pandas.pydata.org/) [![matplotlib](https://img.shields.io/badge/matplotlib-ff8530.svg?logo=data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iMTI4IiBoZWlnaHQ9IjEyOCIgc3Ryb2tlPSIjNzc3IiBmaWxsLW9wYWNpdHk9Ii44Ij48c2NyaXB0IHhtbG5zPSIiIGlkPSJjdXN0b20tdXNlcmFnZW50LXN0cmluZy1wYWdlLXNjcmlwdCIvPg0KPHBhdGggZmlsbD0iI0ZGRiIgZD0ibTYzLDFhNjMsNjMgMCAxLDAgMiwwem0wLDE0YTQ5LDQ5IDAgMSwwIDIsMHptMCwxNGEzNSwzNSAwIDEsMCAyLDB6bTAsMTRhMjEsMjEgMCAxLDAgMiwwem0wLDE0YTcsNyAwIDEsMCAyLDB6bTY0LDdIMW0xMDgtNDUtOTAsOTBtOTAsMC05MC05MG00NS0xOHYxMjYiLz4NCjxwYXRoIGZpbGw9IiNGNjAiIGQ9Im01MCw4LTIwLDEwIDY4LDkyIDEwLTEwTDY0LDY0eiIvPg0KPHBhdGggZmlsbD0iI0ZDMCIgZD0ibTE3LDUwdjI4TDY0LDY0eiIvPg0KPHBhdGggZmlsbD0iIzdGNyIgZD0ibTY0LDY0IDYsMzVINTh6Ii8+DQo8cGF0aCBmaWxsPSIjQ0YzIiBkPSJtNjQsNjQgMTMtNDAgOSw1eiIvPg0KPHBhdGggZmlsbD0iIzA0RiIgZD0ibTY0LDY0IDE0LTYgMSw0emwtMjYsMTMgMyw0eiIvPg0KPC9zdmc+&style=flat-square&logoColor)](https://matplotlib.org/) [![seaborn](https://img.shields.io/badge/seaborn-444876.svg?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI1MzMuMyIgaGVpZ2h0PSI1MzMuMyIgdmVyc2lvbj0iMS4wIiB2aWV3Qm94PSIwIDAgNDAwIDQwMCI+PGcgZmlsbD0iI0ZGRiI+PHBhdGggZD0iTTE4MCAxMUExOTEgMTkxIDAgMCAwIDQ3IDMxMmExOTcgMTk3IDAgMCAwIDE4NSA3NSAxOTcgMTk3IDAgMCAwIDEyMS03NSAxOTcgMTk3IDAgMCAwIDM0LTE0NCAxOTcgMTk3IDAgMCAwLTc1LTEyMSAxOTcgMTk3IDAgMCAwLTEzMi0zNnptNTAgMTBhMTgyIDE4MiAwIDAgMSAxNDUgMjI3IDE4MyAxODMgMCAwIDEtMjIzIDEyN0ExODMgMTgzIDAgMCAxIDIwIDIwMGMwLTI3IDMtNDUgMTItNjhBMTgyIDE4MiAwIDAgMSAyMzAgMjF6Ii8+PHBhdGggZD0iTTE4MyAxNjZjLTkgMS0yNCA0LTMzIDctMTIgNC0yMyA4LTU2IDIzbC00NiAxNy0xOCA2IDEgNmMxIDcgNSAyNCA4IDMxbDIgNSA1IDFoNXYtMTBsMTQtMWgxNHYtOGgxNGMxMSAwIDE0IDAgMTQtMmwxNi0xYzEyIDAgMTUgMCAxNiAybDE0IDFoMTR2OGgyOHYxMWgyOHYxMmgyOHYxMWgyOHY5aDI4djdoMTRjMTAgMCAxMyAwIDE0IDJsNy04YzE0LTIxIDIzLTQ1IDI3LTcwbDEtNi0xOC02LTQ2LTE3Yy00NC0xOS01NC0yMy03NC0yOC05LTItMTMtMi0yOS0yaC0yMXoiLz48cGF0aCBkPSJtMTExIDI0NC0xIDUxdjUxbDEyIDYgMTIgNiAxLTU3di01OGgtMTJsLTEyIDF6bS0yOCAzLTEgMzh2MzlsNCA0IDIwIDE1IDEtNDh2LTQ5SDk1bC0xMiAxem01NiAwLTEgNTZ2NTZsMyAyIDIyIDZWMjQ3bC0xMi0xLTEyIDF6bS04NCA4LTEgMTd2MThsNiA4IDEzIDE2IDYgNnYtNjZINjdsLTEyIDF6bTExMiAwLTEgNTd2NTZsNyAxIDEzIDJoNXYtNTRsMS01OHYtNWgtMTNsLTEyIDF6TTQyIDI2Nmw1IDkgNCA5di0xOWgtNGwtNSAxem0xNTMgMC0xIDUzdjUyaDEybDEyLTEgMS01MnYtNTJsLTEyLTEtMTIgMXptMjggMTItMSA0NnY0NWgzbDEyLTIgMTAtMnYtNDBsMS00M3YtNGwtMTMtMS0xMiAxem0yOCAxMXY3NGwxOC03IDYtMnYtNjZoLTEybC0xMiAxem0yOCA5LTEgMjd2MjdsNC0yIDEzLTggOC01di0zN2MwLTIgMC0yLTEyLTNsLTEyIDF6bTI4IDctMSAxNnYxNGwxMy0xMmM5LTEwIDEyLTEzIDEyLTE1di0zbC0xMi0xLTEzIDF6Ii8+PC9nPjwvc3ZnPg==&style=flat-square&logoColor)](https://seaborn.pydata.org/) [![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com/)

![time_series](https://github.com/user-attachments/assets/ad796def-60c6-4281-814a-45a4c79a4846)

## 📝 내용

1. EDA
2. 데이터 전처리
3. 머신러닝 모델링
4. 딥러닝 모델링

## 📊 데이터

-   형태: 시계열데이터
-   출처: 서울시 공공데이터 포털

## 💡 이동 평균 시 예측 데이터 오염

시계열 예측을 위해
train_set과 test_set의 y값은 총생활인구수이며 X 테이블에는 시프트와 롤링을 한 파생변수가 들어가게 된다.  
이때, X테이블에 총생활인구수의 값이 이동 평균(롤링)에 들어가면 실상 데이터 예측값을 참조하게 되는 것이다.  
그러므로 이동 평균시에는 반드시 `shift(1)`로 해당 날짜 전부터 이동 평균 계산이 들어가야 한다.

```python
train_set["총생활인구수"].shift(1).rolling(24, min_periods=1).mean()
```
