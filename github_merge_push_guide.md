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
git lfs track "*.mp3"
git add .gitattributes
git add myfile.mp3
git commit -m "Add large file using Git LFS"
git push
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
