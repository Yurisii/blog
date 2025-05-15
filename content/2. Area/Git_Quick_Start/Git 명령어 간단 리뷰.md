
다양한 개념들이 있지만 이렇게 정리하면 잘 와닿지가 않죠, 하나씩 해보면서 배워보겠습니다.

먼저 git이 설치되어 있는지 확인합니다.
참고로 저는 현재 `CentOS 7.9` 환경에서 작업합니다.

---

## 0. Git 기본 설정
먼저 Git 버전을 확인합니다:
```bash
git --version
```
버전 정보가 출력되면 설치되어 있는 것입니다. 만약 설치되어 있지 않다면 다음 명령어로 설치합니다:
```bash
yum install git
```

버전을 확인했으면 사용자 정보를 설정합니다:
```bash
git config --global user.name "user"
git config --global user.email "user@usermail.com"
```
`--global` 옵션으로 저장하면 모든 Git 저장소에 기본값으로 적용됩니다. 특정 디렉토리에서만 다른 사용자 정보를 사용하고 싶다면, 해당 디렉토리에서 `--local` 옵션으로 다시 설정하여 덮어쓸 수 있습니다.

---

## 1. 작업 디렉토리 접근
작업할 디렉토리를 만들고 해당 디렉토리로 이동합니다:
```bash
mkdir git-test
cd git-test
```

---

## 2. Git 저장소 초기화
현재 디렉토리를 Git 저장소로 초기화합니다:
```bash
git init
```
초기화 후 숨김 파일을 포함하여 디렉토리 내용을 확인합니다:
```bash
ls -a
```
`.git/` 이라는 숨김 디렉토리가 생성되었다면, 이 디렉토리는 Git이 버전 관리를 수행하는 내부 공간임을 의미합니다.

---

## 3. 관리할 파일 생성
버전 관리를 테스트할 간단한 파일을 생성합니다:
```bash
echo "hello git" > hello.txt
```

---

## 4. Git 상태 확인
파일 생성 후 Git 상태를 확인합니다:
```bash
git status
```
다음과 유사한 출력이 나타납니다:
```
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	hello.txt
nothing added to commit but untracked files present (use "git add" to track)
```
여기서 `hello.txt`가 "Untracked file"로 표시된 것은 Git이 아직 이 파일을 관리 대상으로 삼지 않았다는 의미입니다. 관리 대상으로 삼으려면 스테이징 영역에 추가해야 합니다.

---

## 5. 스테이징 영역에 추가
`hello.txt` 파일을 스테이징 영역에 추가합니다:
```bash
git add hello.txt
```
다시 `git status`를 실행하면 출력이 변경된 것을 확인할 수 있습니다:
```
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
#	new file:   hello.txt
#
```
이제 `hello.txt` 파일이 스테이징 영역에 추가되어 Git의 관리 대상이 되었습니다.

---

## 6. 로컬 커밋
스테이징된 변경 사항을 로컬 저장소에 커밋합니다:
```bash
git commit -m "first commit for hello.txt"
```
커밋 후 로그를 확인하여 커밋 기록을 볼 수 있습니다:
```bash
git log
```
최근 커밋 기록이 출력됩니다.

---

## 7. 브랜치
현재 브랜치 목록과 현재 위치한 브랜치를 확인합니다:
```bash
git branch
```
`* master` (또는 버전에 따라 `* main`)가 표시되면 현재 master (또는 main) 브랜치에 있다는 뜻입니다.

새로운 브랜치를 생성해 보겠습니다. `readme`라는 이름의 브랜치를 만듭니다:
```bash
git branch readme
```
생성한 `readme` 브랜치로 전환합니다:
```bash
git checkout readme
```
"Switched to branch 'readme'"라는 메시지가 출력됩니다. 이제 `readme` 브랜치에서 작업을 진행합니다. `git branch`로 다시 확인하면 `* readme`가 표시될 것입니다.
`readme` 브랜치에서 파일을 수정하고 커밋합니다:
```bash
echo "Test branch" >> hello.txt
git add hello.txt
git commit -m "modified hello.txt in readme branch"
```
"modified hello.txt in readme branch"와 "1 file changed, 1 insertion(+)" 같은 메시지가 출력되며 커밋되었음을 알려줍니다.

다시 master 브랜치로 돌아갑니다:
```bash
git checkout master
```
`readme` 브랜치에서 작업한 내용을 master 브랜치로 병합(merge)합니다:
```bash
git merge readme
```
병합이 완료된 후에는 `readme` 브랜치를 삭제할 수 있습니다:
```bash
git branch -d readme
```

---

## 8. diff
Git은 작업을 세 구역으로 나누어 관리합니다:
- **Working Directory**: 현재 작업 중인 파일이 있는 곳
- **Staging Area**: `git add` 명령으로 추가된 파일이 대기하는 곳
- **Local Repository**: `git commit` 명령으로 변경 사항이 저장된 곳

`git diff`는 이들 간의 차이점을 확인할 때 사용하는 명령어입니다.

- Working Directory와 Staging Area 간의 차이 확인:
  ```bash
  git diff
  ```

- Staging Area와 마지막 커밋(HEAD) 사이의 차이 확인 (파일을 `add`한 후 아직 커밋하지 않았을 때):
  ```bash
  git diff --cached
  ```

- 현재 커밋 상태(HEAD)와 Working Directory 전체의 차이 확인:
  ```bash
  git diff HEAD
  ```
- 특정 파일만 비교:
  ```bash
  git diff hello.txt
  git diff --cached hello.txt
  ```
- 브랜치 간 차이 비교:
  ```bash
  git diff master..readme
  git diff readme..master
  ```
  앞쪽 브랜치가 기준이 되고, 뒤쪽 브랜치가 비교 대상입니다. 예를 들어 `git diff master..readme`는 `readme` 브랜치를 기준으로 `master` 브랜치와 어떤 차이가 있는지 보여줍니다.

- 이전 커밋과의 비교:
  ```bash
  git diff HEAD^
  ```
  위 명령어는 현재 HEAD의 바로 이전 커밋과 비교합니다.

- 가장 최근 커밋의 상세 변경 내용 확인:
  ```bash
  git show
  ```
  이 명령어는 가장 최근 커밋(예: merge 커밋)으로 인해 어떤 파일이 어떻게 변경되었는지 diff 형식으로 보여줍니다. 출력 중간에 `@@ -1 +1,2 @@`와 같은 라인이 보일 수 있는데, 이는 diff에서 줄 번호 변경을 설명하는 부분입니다. 위 예시는 원본 파일의 1번째 줄이 삭제되고, 새로운 내용이 1번 줄부터 2번 줄까지 추가되었음을 의미합니다. 그 아래에는 실제 내용 변경이 다음과 같이 표시됩니다:
 
	`diff`
	``` shell
  - hello git
  + hello git
  + Test branch
	```


  이 출력은 'hello.txt' 파일에서 "Test branch"라는 문장이 새로 추가된 변화를 보여줍니다. 앞의 `-`는 기존에 있던 줄이 삭제되었음을, `+`는 추가된 내용을 나타냅니다. 


## 9. push & pull & clone
원격 저장소와 관련된 주요 명령어 세 가지는 `git clone`, `git pull`, `git push`입니다.

- **`git clone [원격 저장소 주소]`**: 원격 서버에 있는 저장소를 내 컴퓨터로 처음 복제해오는 명령어입니다.
  ```bash
  git clone <repository_url>
  ```
  이 명령을 실행하면 `.git` 폴더가 포함된 로컬 Git 디렉토리가 자동으로 생성됩니다.
- **`git pull [원격 저장소 별칭] [브랜치명]`**: 원격 서버에 반영된 최신 커밋을 로컬 저장소로 가져오는 명령어입니다.
  ```bash
  git pull origin master
  ```
  이미 `clone` 해온 저장소에서 사용합니다. 원격 저장소의 최신 커밋을 로컬 저장소로 가져오고, 자동으로 병합(merge)까지 수행합니다. 이는 `git fetch` 후 `git merge`를 실행하는 것과 동일합니다.
- **`git push [원격 저장소 별칭] [브랜치명]`**: 로컬에서 커밋한 내용을 원격 저장소에 업로드하는 명령어입니다.
  ```bash
  git push origin master
  ```
  로컬에서 `commit`까지 마친 변경 사항을 원격 서버로 올립니다.

변경 사항이 생기면 꼭 커밋하는 습관을 들입시다.