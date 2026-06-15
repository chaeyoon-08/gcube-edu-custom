# gcube-edu-custom

gcube GPU 플랫폼용 커스텀 교육용 컨테이너 이미지 모음입니다. `gcube-edu-templates`의 표준 템플릿을 베이스로, 특정 수업·기관의 요구에 맞춰 추가 패키지나 설정을 얹은 이미지입니다.

## 이미지 목록

| 이미지 | 베이스 | 대상 | GPU 권장 |
|---|---|---|---|
| `edu-tensorflow-yonsei` | `edu-dl-tensorflow` | 연세대 CNN 전이학습·QAT 실습 수업 | VRAM 8GB 이상 |

각 이미지의 상세 구성은 해당 폴더의 README를 참고하세요.

## 사용

gcube 워크로드 배포 시 이미지 주소만 바꿔서 사용합니다. 포트는 모두 `8888`(JupyterLab 자동 실행), 작업 디렉터리는 `/workspace`로 동일합니다.

```
ghcr.io/data-alliance/edu-tensorflow-yonsei:1.0
chaeyoon08/edu-tensorflow-yonsei:1.0
```

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