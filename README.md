# gcube-edu-custom

gcube GPU 플랫폼용 커스텀 교육용 컨테이너 이미지 모음입니다. `gcube-edu-templates`의 표준 템플릿을 베이스로, 특정 수업·기관의 요구에 맞춰 추가 패키지나 설정을 얹은 이미지입니다.

## 이미지 목록

| 이미지 | 베이스 | 대상 |
|---|---|---|
| `edu-tensorflow-yonsei` | `edu-dl-tensorflow` | 연세대 CNN 전이학습·QAT 실습 수업 |

각 이미지의 상세 구성은 해당 폴더의 README를 참고하세요.

## 공통 사항

- 베이스: `gcube-edu-templates`의 템플릿 이미지
- 작업 디렉터리: `/workspace`
- 포트: `8888` (JupyterLab 자동 실행)
- git 자동 설정 및 저장소 자동 clone(`GIT_CLONE_REPO`) 기능은 베이스에서 상속

| 환경변수 | 설명 |
|---|---|
| `JUPYTER_TOKEN` | JupyterLab 접속 토큰. 미지정 시 토큰 없이 접속 |
| `GIT_CLONE_REPO` | 워크로드 시작 시 `/workspace`에 자동 clone할 저장소 URL |

## 이미지 주소

```
# Docker Hub
chaeyoon08/<이미지명>:<태그>
```