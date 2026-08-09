Markdown
# Git 저장소 특정 하위 폴더 분리 및 신규 저장소 이전 가이드

이 문서는 `git-filter-repo` 도구를 사용하여 기존 Git 저장소의 특정 하위 폴더를 커밋 기록(History)과 함께 완벽하게 분리하여 새로운 독립된 저장소로 이전하는 방법을 설명합니다.

## 📚 사전 준비
*   **작업 환경:** 윈도우 터미널, 명령 프롬프트(cmd) 또는 Git Bash
*   **필수 요구사항:** Python 및 패키지 관리자(`pip`) 설치 완료


## 1. git-filter-repo 도구 다운로드 및 설치

Python 패키지 관리자인 `pip`를 사용하여 Git 공식 권장 필터링 도구를 설치합니다. 이 과정을 통해 시스템 명령어로 도구가 등록됩니다.

```bash
pip install git-filter-repo
2. 원본 저장소 복제 (안전한 작업 공간 마련)
원본 저장소가 훼손되는 것을 원천 차단하기 위해, 분리 작업을 진행할 완전히 새로운 로컬 폴더에 원본을 복제(Clone)하여 사용합니다.
```

## 2. 원본 저장소 복제 (안전한 작업 공간 마련)
원본 저장소가 훼손되는 것을 원천 차단하기 위해, 분리 작업을 진행할 완전히 새로운 로컬 폴더에 원본을 복제(Clone)하여 사용합니다.

```bash
# 작업할 최상위 폴더로 이동
cd <작업할_상위_폴더_경로>

# 원본 저장소를 'glc2d_lib_local'이라는 임시 폴더로 클론
git clone [https://github.com/3dapi/bs17_2d_lib.git](https://github.com/3dapi/bs17_2d_lib.git) glc2d_lib_local

# 새로 클론한 임시 폴더로 진입
cd glc2d_lib_local
```


## 3. 특정 하위 폴더 분리 (필터링)
새로 만든 임시 폴더 안에서 아래 명령어를 실행합니다. gls2d_v0.1 폴더의 내용과 커밋 기록만을 최상위 경로(Root)로 끌어올리며, 그 외의 파일과 기록은 모두 영구히 삭제됩니다.

```bash
# --subdirectory-filter: 하위 폴더의 알맹이만 루트로 끌어올림
# --force: 방금 클론한 폴더에서 발생하는 안전장치 경고를 우회하여 강제 실행
git filter-repo --force --subdirectory-filter gls2d_v0.1
```

## 4. 신규 원격 저장소에 올리기 (Push)
- GitHub 등에 완전히 비어있는 신규 저장소를 생성합니다. (주의: README, .gitignore, License 파일 등을 절대 체크하지 않은 완전한 빈 상태여야 합니다.)
- 이후 분리 작업이 완료된 현재의 로컬 폴더를 새 원격 저장소에 연결하고 업로드합니다.

```bash
# 기존 origin 연결은 filter-repo 도구가 자동으로 끊어주므로, 바로 새 주소를 연결
git remote add origin [https://github.com/3dapi/glc2d_lib.git](https://github.com/3dapi/glc2d_lib.git)

# 마스터(또는 메인) 브랜치로 모든 기록 업로드
git push -u origin master
```

