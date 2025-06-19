Perl로 제작된 [[XML|xml]]로 변환하는 코드를 Python으로 변환하는 **과정** 중 공부한 문법에 대한 정리
# Perl
### Type

**데이터 타입 및 변수 기호**

| 변수 타입 | 데이터 타입       | 기호  | 예시                              | 설명                       |
| ----- | ------------ | --- | ------------------------------- | ------------------------ |
| 스칼라   | 숫자, 문자열 등    | `$` | `my $name = "Alice";`           | 하나의 값 (숫자, 문자열 등)를 저장    |
| 배열    | 리스트          | `@` | `my @colors = ("red", "blue");` | 순서 있는 여러 값을 저장 (0부터 인덱스) |
| 해시    | 키-값 쌍 (딕셔너리) | `%` | `my %ages = ("Tom" => 30);`     | 키-값 쌍으로 구성된 집합 저장        |

**Scope 관련**

| 키워드     | 용도                      | 설명                                       |
| ------- | ----------------------- | ---------------------------------------- |
| `my`    | 지역 변수 선언                | 블록(함수, if문 등) 내부에서만 유효한 변수 선언            |
| `our`   | 패키지 전역 변수 선언            | 전체 패키지에서 접근 가능한 전역 변수 (전역 범위에서 공유 필요할 때) |
| `local` | 일시적 지역화 (기존 전역 변수 덮어쓰기) | 기존 전역 변수의 값을 임시로 바꾸고 블록이 끝나면 원래 값 복원     |
|         |                         |                                          |

# Python

>[!reflection]
>함수의 구조 및 중첩 여부는 들여쓰기(tab)를 통해서 확인한다. (괄호를 안쓴다.)
>import는 include랑 비슷한 개념?


## import

>[!definition] import in python
>모듈(파일) 전체를 가져와서 객체, 함수, 클래스 등을 사용할 수 있게 합니다. 모듈은 한 번만 로드되며 이를 통해 네임스페이스 관리가 가능해져 충돌을 관리합니다.

>[!reflection] import vs include
>결론적으로 보면 비슷해보이는데, `import`는 모듈 단위로 가져와서 기능마다 호출하는 개념이고, `#include`는 코드 블록을 포함시켜 모든 내용이 동일한 파일 내에 존재하게 만드는 개념이다.

### sys
> [!info] sys
> Python 인터프리터와 상호작용하기 위한 기능을 제공합니다.

|기능|설명|예시 코드|
|---|---|---|
|`sys.argv`|명령줄 인자 받기|`sys.argv[1]`|
|`sys.exit()`|프로그램 강제 종료|`sys.exit(1)`|
|`sys.path`|모듈 탐색 경로 확인 및 수정|`sys.path.append('mymodule')`|
|`sys.stdin`, `stdout`|표준 입출력 스트림 제어|`sys.stdin.read()`|
|`sys.version`|현재 파이썬 버전 확인|`print(sys.version)`|

```python title:sys
import sys

if len(sys.argv) < 2:
    print("Usage: script.py filename")
    sys.exit(1)

print(f"Filename is: {sys.argv[1]}")
```

### os
>[!info] os
>운영체제와 상호작용하기 위한 기능을 제공합니다.

| 기능                       | 설명                    | 예시 코드                   |
| ------------------------ | --------------------- | ----------------------- |
| `os.getcwd()`            | 현재 작업 디렉토리 얻기         | `os.getcwd()`           |
| `os.chdir(path)`         | 작업 디렉토리 변경            | `os.chdir("/tmp")`      |
| `os.listdir(path)`       | 디렉토리 내 파일 목록          | `os.listdir(".")`       |
| `os.environ`             | 환경 변수 접근              | `os.environ["HOME"]`    |
| `os.path`                | 경로 관련 유틸리티 (조합, 분리 등) | `os.path.join()`        |
| `os.remove()`, `mkdir()` | 파일 삭제, 디렉토리 생성 등      | `os.remove("file.txt")` |

```python
import os

files = os.listdir(".")
for f in files:
    print(f)

```

### re
> [!definition] re
> Python에서 정규 표현식을 사용하여 문자열 검색과 조작을 위한 모듈입니다.

| 기능             | 설명                            | 예시 코드                                |
| -------------- | ----------------------------- | ------------------------------------ |
| `re.match()`   | 문자열의 시작에서 패턴 일치 여부 확인         | `re.match(r'\d+', '123abc')`         |
| `re.search()`  | 문자열 전체에서 패턴 일치 여부 검색          | `re.search(r'\d+', 'abc123')`        |
| `re.findall()` | 문자열에서 패턴에 일치하는 모든 부분을 리스트로 반환 | `re.findall(r'\d+', 'abc123def456')` |
| `re.split()`   | 패턴을 기준으로 문자열을 분할              | `re.split(r'\s+', 'Hello World')`    |
| `re.sub()`     | 패턴에 일치하는 부분을 다른 문자열로 대체       | `re.sub(r'\s+', '-', 'Hello World')` |
| `re.compile()` | 정규 표현식 패턴을 컴파일하여 재사용 가능하게 준비  | `pattern = re.compile(r'\d+')`       |

```python
import re

text = "The rain in Spain"
# 문자열의 시작에서 일치 여부 확인
match = re.match(r'\bThe\b', text)
if match:
    print("Match found at the start of the string!")

# 문자열 전체에서 검색
search = re.search(r'Spain', text)
if search:
    print("Match found within the string.")
```


## Syntax

### Formatting
Python에서 문자열 앞에 붙는 `f`나 `r` 등의 접두사는 문자열의 형식을 지정하는 데 사용됩니다. 여기 각각의 의미와 함께 다른 가능한 형식들을 설명합니다:

1. **f-string (`f"string"`)**:
    
    - **설명**: 문자열 내에 변수를 직접 삽입할 수 있는 포매팅 방식입니다. `{}`를 사용하여 변수나 표현식을 포함할 수 있습니다.
    - **예시**:
        
        ```python
        name = "Alice"
        greeting = f"Hello, {name}!"
        print(greeting)  # "Hello, Alice!"
        ```
        
2. **Raw String (`r"string"`)**:
    
    - **설명**: 백슬래시(`\`)를 이스케이프 문자로 처리하지 않고 일반 문자로 간주합니다. 주로 정규 표현식을 사용할 때 유용합니다.
    - **예시**:
        
        ```python
        path = r"C:\new_folder\test"
        print(path)  # "C:\new_folder\test"
        ```
        
3. **b-string (`b"string"`)**:
    
    - **설명**: 바이트 문자열을 정의합니다. 주로 바이너리 데이터를 다룰 때 사용됩니다.
    - **예시**:
        
        ```python
        byte_data = b"Example bytes"
        ```
        
4. **u-string (`u"string"`)**: (Python 2에서)
    
    - **설명**: 유니코드 문자열을 나타냅니다. Python 3에서는 모든 문자열이 기본적으로 유니코드입니다.
5. **Triple Quotes (`""" or '''`)**:
    
    - **설명**: 여러 줄 문자열을 생성할 수 있습니다. 주석이나 긴 문자열에 유용합니다.
    - **예시**:
        
        ```python
        long_text = """This is a
        multi-line string."""
        ```
        

이러한 형식들은 Python 내에서 문자열을 다루는 데 있어 다양한 방법을 제공합니다. `f-string`과 `r-string`은 특히 자주 사용되는 유용한 기능입니다.


## Function
### a
# Perl to Python

### sys

|목적|Perl|Python|
|---|---|---|
|커맨드라인 인자 처리|`@ARGV`|`sys.argv`|
|프로그램 종료|`exit()`|`sys.exit()`|

### os
| 목적       | Perl                     | Python                                         |
| -------- | ------------------------ | ---------------------------------------------- |
| 환경 변수 접근 | `$ENV{VAR}`              | `os.environ["VAR"]` 또는 `os.environ.get("VAR")` |
| 현재 디렉토리  | `pwd`, `\`               | `os.getcwd()`                                  |
| 파일 존재 여부 | `-e $file`               | `os.path.exists(file)`                         |
| 절대 경로 판단 | `-e`, `-d`, `-f` + 정규표현식 | `os.path.exists()`, `os.path.isdir()` 등        |


### re
|목적|Perl|Python|
|---|---|---|
|정규표현식 매칭|`$x =~ m/^\/$/`|`re.match(r"^/$", x)`|
|정규표현식 치환|`$x =~ s/.../.../`|`re.sub()` (아직 등장 안 했지만 대응됨)|


- next -> continue 
- last -> break
- close ->

### argument
#### Function argument
아래와 같이 받은 인자를 로컬 변수에 할당하는 형태는
```perl
sub string {
    my $beg = $_[0];
    my $end = $_[1];
    ...
}
```

아래처럼 파이썬으로 변환이 가능하다.
```python
def string(beg, end):
```

#### 일치하는 함수

```perl
chomp($start)
```
문자열의 끝에 있는 줄 바꿈 문자를 제거한다.

``` python
start = start.strip()
```
문자열의 양 끝에서 공백 문자(기본적으로 포함된 공백, 줄 바꿈 문자 등)를 제거합니다. `lstrip()`과 `rstrip()`을 사용하면 각각 왼쪽과 오른쪽만 제거할 수도 있다.




| Perl                     | Python                                       |
| ------------------------ | -------------------------------------------- |
| `my $x = "";`            | `x = ""`                                     |
| `while (1)`              | `while True:`                                |
| `get_line();`            | `get_line()`                                 |
| `if (!defined($xxx))`    | `if xxx is None:`                            |
| `=~ /\s*XYZ\s*:\s*(.+)/` | `re.search(r"\s*XYZ\s*:\s*(.+))", line_buf)` |
| `chomp($x)`              | `x = x.strip()`                              |
| `last;`                  | `break`                                      |
| `return $x;`             | 동일 (`return x`)                              |
- Perl의 `my $x = "";`는 Python에서 `x = ""`로 작성됩니다.
- 무한 루프는 Perl에서 `while (1)`로, Python에서는 `while True:`로 표현합니다.
- Perl의 함수 호출 `get_line();`은 Python에서는 `get_line()`으로 동일하게 사용됩니다.
- Perl에서 정의되지 않은 값을 체크하기 위해 `if (!defined($line_buf))`를 사용하며, 이는 Python에서 `if line_buf is None:`으로 대응됩니다.
- 정규 표현식 사용에서는 Perl의 `=~ /\s*XYZ\s*:\s*(.+)/`가 Python에서는 `re.search(r"\s*XYZ\s*:\s*(.+))", line_buf)`로 대체됩니다.
- 마지막으로, Perl의 루프 종료인 `last;`는 Python에서는 `break`로 변환되며, 리턴 값은 Perl과 Python 모두에서 `return $x;`와 `return x`로 동일하게 표현됩니다.
