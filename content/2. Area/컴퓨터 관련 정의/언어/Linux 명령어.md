
# grep
### 표로 보기
| 용도         | 명령어 예시                               | 설명                |
| ---------- | ------------------------------------ | ----------------- |
| 기본 검색      | `grep "text" file.txt`               | 특정 문자열 포함 줄 찾기    |
| 대소문자 무시    | `grep -i "text" file.txt`            | 대소문자 구분 없이 찾기     |
| 줄 번호 표시    | `grep -n "text" file.txt`            | 줄 번호와 함께 출력       |
| 부정 검색      | `grep -v "text" file.txt`            | 문자열이 없는 줄 출력      |
| 줄 개수 세기    | `grep -c "text" file.txt`            | 일치하는 줄 수 출력       |
| 여러 파일 검색   | `grep "text" *.log`                  | 여러 파일에서 검색        |
| 디렉토리 재귀 검색 | `grep -r "text" .`                   | 하위 폴더 포함 전체 검색    |
| 파일명만 출력    | `grep -rl "text" .`                  | 해당 문자열 포함된 파일만 표시 |
| 다중 패턴 검색   | `grep -E "foo \| bar" file.txt`      | 여러 단어 중 하나라도 포함   |
| 특정 파일형식만   | `grep "text" --include="*.c" -r .`   | 특정 확장자 파일만 검색     |
| 특정 제외 검색   | `grep "text" --exclude="*.log" -r .` | 특정 확장자 제외하고 검색    |
| 키워드 강조 출력  | `grep --color=auto "text" file.txt`  | 일치한 단어 색상 강조      |
| 스크립트 내 사용  | `ps aux \| grep nginx`               | 명령어 파이프와 함께 사용    |
| 정확한 단어 검색  | `grep -w "word" file.txt`            | 단어 전체 일치만 검색      |
| 정규표현식 사용   | `grep -P "\d{3}-\d{4}" file.txt`     | Perl 스타일 정규표현식 사용 |


### 파일 안에서 특정 단어 찾기
```bash
grep "error" log.txt
```
-> `log.txt`파일 에서 "error"가 포함된 줄 출력

### 대소문자 구분 없이 검색
```bash
grep -i "warning" log.txt
```
-> "Waring", "WARNING", "warning" 등 대소문자 무시하고 검색

### 줄 번호와 함께 출력
``` bash
grep -n "function" main.c
```
-> `main.c` 파일에서 "function"이 포함된 줄 번호와 함께 출력

### 여러 파일에서 검색
```bash
grep "TODO" *.py
```
-> 현재 디렉토리의 모든 `.py` 파일에서 "TODO" 검색

### 디렉토리 전체에서 재귀적으로 검색
```bash
grep -r "logic_sys" .
```
-> `logic_sys`가 포함된 줄을 현재 디렉토리와 하위 디렉토리 전체에서 검색

### 검색된 줄의 개수 세기
```bash
grep -c "success" result.log
```
-> "success"가 포함된 줄의 개수를 출력

### 특정 단어가 포함되지 않은 줄만 보기
```bash
grep -v "debug" log.txt
```
-> "debug"가 포함되지 않은 줄만 출력

### 일치하는 줄이 있는 파일 이름만 출력
```bash
grep -rl "config" .
```
-> "config" 라는 단어가 포함된 파일 이름만 출력(재귀)

### 복수 패턴 검색 (`or` 조건)
```bash
grep -E "fail|error" log.txt
```
또는
```bash
grep -e "fail" -e "error" log.txt
```
-> "fail" 또는 "error"가 포함된 줄 검색

### 특정 파일 형식만 검색
```bash
grep -r "main" --include="*.c" .
```
-> `.c` 파일만 검색 대상

### 명령어 조합 예시
```bash
dmesg | grep "usb"
```
->  시스템 로그 중 "usb" 관련 메시지만 출력