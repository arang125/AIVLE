# 서울시 공유자전거 '따릉이'의 수요 예측

> **주제**: EDA, 시각화  
> **기간**: 2023.08.23

## 💻 학습 기술 스택

[![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas)](https://pandas.pydata.org/) [![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org/) [![matplotlib](https://img.shields.io/badge/matplotlib-ff8530.svg?logo=data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iMTI4IiBoZWlnaHQ9IjEyOCIgc3Ryb2tlPSIjNzc3IiBmaWxsLW9wYWNpdHk9Ii44Ij48c2NyaXB0IHhtbG5zPSIiIGlkPSJjdXN0b20tdXNlcmFnZW50LXN0cmluZy1wYWdlLXNjcmlwdCIvPg0KPHBhdGggZmlsbD0iI0ZGRiIgZD0ibTYzLDFhNjMsNjMgMCAxLDAgMiwwem0wLDE0YTQ5LDQ5IDAgMSwwIDIsMHptMCwxNGEzNSwzNSAwIDEsMCAyLDB6bTAsMTRhMjEsMjEgMCAxLDAgMiwwem0wLDE0YTcsNyAwIDEsMCAyLDB6bTY0LDdIMW0xMDgtNDUtOTAsOTBtOTAsMC05MC05MG00NS0xOHYxMjYiLz4NCjxwYXRoIGZpbGw9IiNGNjAiIGQ9Im01MCw4LTIwLDEwIDY4LDkyIDEwLTEwTDY0LDY0eiIvPg0KPHBhdGggZmlsbD0iI0ZDMCIgZD0ibTE3LDUwdjI4TDY0LDY0eiIvPg0KPHBhdGggZmlsbD0iIzdGNyIgZD0ibTY0LDY0IDYsMzVINTh6Ii8+DQo8cGF0aCBmaWxsPSIjQ0YzIiBkPSJtNjQsNjQgMTMtNDAgOSw1eiIvPg0KPHBhdGggZmlsbD0iIzA0RiIgZD0ibTY0LDY0IDE0LTYgMSw0emwtMjYsMTMgMyw0eiIvPg0KPC9zdmc+&style=flat-square&logoColor)](https://matplotlib.org/) [![seaborn](https://img.shields.io/badge/seaborn-444876.svg?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI1MzMuMyIgaGVpZ2h0PSI1MzMuMyIgdmVyc2lvbj0iMS4wIiB2aWV3Qm94PSIwIDAgNDAwIDQwMCI+PGcgZmlsbD0iI0ZGRiI+PHBhdGggZD0iTTE4MCAxMUExOTEgMTkxIDAgMCAwIDQ3IDMxMmExOTcgMTk3IDAgMCAwIDE4NSA3NSAxOTcgMTk3IDAgMCAwIDEyMS03NSAxOTcgMTk3IDAgMCAwIDM0LTE0NCAxOTcgMTk3IDAgMCAwLTc1LTEyMSAxOTcgMTk3IDAgMCAwLTEzMi0zNnptNTAgMTBhMTgyIDE4MiAwIDAgMSAxNDUgMjI3IDE4MyAxODMgMCAwIDEtMjIzIDEyN0ExODMgMTgzIDAgMCAxIDIwIDIwMGMwLTI3IDMtNDUgMTItNjhBMTgyIDE4MiAwIDAgMSAyMzAgMjF6Ii8+PHBhdGggZD0iTTE4MyAxNjZjLTkgMS0yNCA0LTMzIDctMTIgNC0yMyA4LTU2IDIzbC00NiAxNy0xOCA2IDEgNmMxIDcgNSAyNCA4IDMxbDIgNSA1IDFoNXYtMTBsMTQtMWgxNHYtOGgxNGMxMSAwIDE0IDAgMTQtMmwxNi0xYzEyIDAgMTUgMCAxNiAybDE0IDFoMTR2OGgyOHYxMWgyOHYxMmgyOHYxMWgyOHY5aDI4djdoMTRjMTAgMCAxMyAwIDE0IDJsNy04YzE0LTIxIDIzLTQ1IDI3LTcwbDEtNi0xOC02LTQ2LTE3Yy00NC0xOS01NC0yMy03NC0yOC05LTItMTMtMi0yOS0yaC0yMXoiLz48cGF0aCBkPSJtMTExIDI0NC0xIDUxdjUxbDEyIDYgMTIgNiAxLTU3di01OGgtMTJsLTEyIDF6bS0yOCAzLTEgMzh2MzlsNCA0IDIwIDE1IDEtNDh2LTQ5SDk1bC0xMiAxem01NiAwLTEgNTZ2NTZsMyAyIDIyIDZWMjQ3bC0xMi0xLTEyIDF6bS04NCA4LTEgMTd2MThsNiA4IDEzIDE2IDYgNnYtNjZINjdsLTEyIDF6bTExMiAwLTEgNTd2NTZsNyAxIDEzIDJoNXYtNTRsMS01OHYtNWgtMTNsLTEyIDF6TTQyIDI2Nmw1IDkgNCA5di0xOWgtNGwtNSAxem0xNTMgMC0xIDUzdjUyaDEybDEyLTEgMS01MnYtNTJsLTEyLTEtMTIgMXptMjggMTItMSA0NnY0NWgzbDEyLTIgMTAtMnYtNDBsMS00M3YtNGwtMTMtMS0xMiAxem0yOCAxMXY3NGwxOC03IDYtMnYtNjZoLTEybC0xMiAxem0yOCA5LTEgMjd2MjdsNC0yIDEzLTggOC01di0zN2MwLTIgMC0yLTEyLTNsLTEyIDF6bTI4IDctMSAxNnYxNGwxMy0xMmM5LTEwIDEyLTEzIDEyLTE1di0zbC0xMi0xLTEzIDF6Ii8+PC9nPjwvc3ZnPg==&style=flat-square&logoColor)](https://seaborn.pydata.org/) [![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org/)

## 📝 내용

1. 따릉이 도메인의 데이터를 파악
2. 전처리 및 분석에 필요한 형태로 정리
3. 가설 수립, 단변량 분석, 이변량 분석, 가설 검증하여 비즈니스 인사이트 도출

## 📊 데이터

-   형태: Tabular
-   출처: 서울시 공공데이터 포털
