# GitHub 저장소와 로컬 병합 및 푸시 작업 정리

## 1. 로컬 Git 저장소 초기화 및 원격 저장소 연결

```bash
git init
git remote add origin https://github.com/3dapi/UnrealLesson.git
```

## 2. 파일 추가 및 첫 커밋

```bash
git add .
git commit -m "Initial commit"
```

## 3. 원격 저장소의 main 브랜치 기반으로 로컬 main 생성 및 푸시

GitHub 저장소에 `main` 브랜치가 이미 존재하므로, 로컬에서 다음과 같이 진행:

```bash
git fetch origin
git checkout -b main origin/main
```

그 후 작업 후:

```bash
git push -u origin main
```

## 4. 기존 로컬 브랜치(master)와 병합

### 병합 시 에러 발생

```bash
git merge master
# fatal: refusing to merge unrelated histories
```

### 서로 다른 히스토리 병합 (강제 병합)

```bash
git merge master --allow-unrelated-histories
```

충돌이 발생하면 수동으로 해결 후:

```bash
git commit
```

## 5. 병합된 main 브랜치 푸시

```bash
git push origin main
```

## 6. master 브랜치 정리

로컬 브랜치 삭제:

```bash
git branch -d master
```

원격 브랜치 삭제:

```bash
git push origin --delete master
```

## 7. GitHub 저장소 용량 및 제한 사항

- 저장소 수: **무제한**
- 저장소당 권장 용량: **1GB (최대 5GB까지 가능하지만 경고 발생 가능)**
- 개별 파일 크기 제한: **100MB**
- 그 이상은 Git LFS 사용 필요

### Git LFS 사용 예

```bash
git lfs install
git rm -r --cached .
git lfs track "*.mp3"
git lfs track "*.mp4"

git add .gitattributes
git lfs ls-files
git add myfile.mp3
git commit -m "Add large file using Git LFS"
git push origin main --force
```

## 8. Git Squash
- 최신부터 n개 커밋을 대상으로 함.
```bash
git rebase -i HEAD~n
```
- vi editor 화면에서 가장 오래된커밋만 **pick** 으로 유지
- 나머지 7개 줄의 pick을 모두 s (squash)로 변경
- 메시지 창이 열리면 대표 메시 하나만 남긴뒤 저장
- 강제 푸시
```bash
git push origin main --force
```
## 9. Git amend / push
- git-fork 를 사용하면 amend를 체크해놓고 쓰다보면 종종 충돌을 발생
- <img width="157" height="23" alt="git_amend_crash" src="https://github.com/user-attachments/assets/e2386484-c7cd-485b-b81d-19b541da3f16" />
- 원인
  - amend는 최신 커밋을 수정하여 새로운 커밋으로 덮어쓰는 작업.
  - 로컬(Local): amend로 인해 기존 커밋의 해시(Hash) 값이 바뀌어 완전히 새로운 커밋이 생성 (↑1 발생)
  - 원격에는 아직 수정 전의 기존 커밋이 그대로 남아 있음 (↓1 발생)
  - 충돌: Git은 이 두 커밋이 서로 다른 것으로 간주, Pull 과 동시에 Push 를 표시
  - 해결 방법 A:
    - 강제 푸시 (Force Push) - 원격 저장소를 강제로 덮어 씀.
    - 작업한 내용이 본인만 사용하는 브랜치, 또는 최신 수정본(amend 한 내용)이 확실한 경우.
    - 주의: 다른 협업자가 해당 브랜치를 이미 내려받았다면 혼란을 줄 수 있으므로, 혼자 작업하는 브랜치일 때 주로 사용.
  - 해결 방법 B
    - 현재 폴더를 git 이 없는 폴더에 복사
    - Soft Reset: git reset --soft HEAD~1 (파일 수정 내역은 남기고 커밋만 취소)
    - 복사 한 것을 덮어 쓰고 커밋

- git push --force

```bash
git rebase -i HEAD~n
```
- vi editor 화면에서 가장 오래된커밋만 **pick** 으로 유지
- 나머지 7개 줄의 pick을 모두 s (squash)로 변경
- 메시지 창이 열리면 대표 메시 하나만 남긴뒤 저장
- 강제 푸시
```bash
git push origin main --force
```

# GitHub 명령어

## 파일 모드 해제
- Windows, Mac의 파일 모드가 다름. 맥에서 만든 파일을 윈도우에서 다운로드 되었을 때 권한 문제와 파일 Line Endings 문제 발생 할 수 있음.
- Git이 파일 권한 변경을 무시하도록 설정
``` bash
	- git config core.filemode false
```
- 상태 강제 초기화
``` bash
 	- git reset --hard HEAD
```
- 옵션
	- git checkout -b "version"
