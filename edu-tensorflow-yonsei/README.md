# edu-tensorflow-yonsei

연세대 CNN 전이학습·QAT 실습 수업 맞춤 이미지. `edu-dl-tensorflow` 베이스에 수업에 필요한 추가 패키지와 설정을 얹은 커스텀 이미지입니다.

## 구성

| 항목 | 내용 |
|---|---|
| 기반 | `edu-dl-tensorflow` (TensorFlow 2.17 포함) |
| 추가 패키지 | 수업 커리큘럼에 맞춘 패키지 (자세한 내용은 Dockerfile 참고) |
| 작업 디렉터리 | `/workspace` |
| 포트 | 8888 |

## 사용

gcube 워크로드 배포 시 아래 설정으로 사용합니다.

| 항목 | 값 |
|---|---|
| 이미지 (권장) | `public.ecr.aws/g3x5o1w3/gcube/custom/edu-tensorflow-yonsei:1.0` |
| 이미지 (대안) | `ghcr.io/data-alliance/edu-tensorflow-yonsei:1.0` |
| 포트 | 8888 |
| GPU | VRAM 8GB 이상 |

배포 후 서비스 URL로 접속하면 JupyterLab이 열립니다.

AWS ECR이 GitHub Container Registry보다 다운로드 속도가 빠르기 때문에 사용을 권장합니다.

> **노트북은 한 번에 하나씩 열어 실행하세요.** 여러 노트북을 동시에 열면 각 노트북의 커널이 메모리를 함께 점유해, 메모리 부족으로 워크로드가 종료될 수 있습니다. 다른 노트북으로 넘어갈 때는 이전 노트북의 커널을 종료(Shut Down Kernel)하면 더 안정적입니다.

## 환경변수

모든 환경변수는 선택 사항입니다. 비공개 저장소를 사용하거나 커밋 작성자를 지정하려는 경우에만 입력합니다.

| 변수 | 기본값 | 설명 |
|---|---|---|
| `JUPYTER_TOKEN` | (없음) | JupyterLab 접속 토큰. 미지정 시 토큰 없이 접속 |
| `GIT_CLONE_REPO` | (없음) | 워크로드 시작 시 `/workspace`에 자동 clone할 저장소 URL |
| `GIT_USER_NAME` | (없음) | git 커밋 작성자 이름 |
| `GIT_USER_EMAIL` | (없음) | git 커밋 작성자 이메일 |
| `GIT_TOKEN` | (없음) | git 인증 토큰(PAT). private 저장소 clone/push 시 필요 |
| `GIT_HOST` | `github.com` | git 호스트. GitLab(`gitlab.com`) 또는 사내 git 서버 주소도 가능 |