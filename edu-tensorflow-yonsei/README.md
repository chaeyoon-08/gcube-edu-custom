# edu-tensorflow-yonsei

연세대학교 수업용 TensorFlow 이미지. `edu-dl-tensorflow` 표준 이미지에 양자화 인식 학습(QAT)과 이미지 처리 패키지를 추가합니다.

## 구성

| 항목 | 내용 |
|---|---|
| 기반 | `edu-dl-tensorflow` |
| 추가 패키지 | tensorflow-model-optimization, opencv-python-headless |
| 작업 디렉터리 | `/workspace` |
| 포트 | 8888 |

```
ghcr.io/<owner>/edu-tensorflow-yonsei:1.0
```

## 실행

컨테이너 시작 시 JupyterLab이 자동 실행되며, `/workspace`를 작업 디렉터리로 사용합니다.

## 환경변수

| 변수 | 기본값 | 설명 |
|---|---|---|
| `JUPYTER_TOKEN` | (없음) | 접속 토큰. 미지정 시 토큰 없이 접속 가능 |

git 구성 및 작업 저장소 자동 clone 관련 환경변수는 베이스 이미지에서 상속됩니다.

## 빌드

GitHub Actions의 수동 실행(workflow_dispatch)으로 빌드하며, 템플릿·베이스 이미지·태그를 선택할 수 있습니다. ghcr.io와 Docker Hub에 동시 푸시됩니다.

베이스 이미지(`edu-dl-tensorflow`)가 먼저 빌드되어 있어야 합니다.