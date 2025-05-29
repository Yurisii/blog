### 목적
**Python 3.6.5** 설치

`Development Tools `설치 되어있다고 가정

### 1. 필요 패키지 설치
```bash
sudo yum install gcc openssl-devel bzip2-devel libffi-devel wget -y
```

### 2. 소스 코드로 Python 3.6.5 설치
```bash
cd /usr/src
sudo wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz
sudo tar xzf Python-3.6.5.tgz
cd Python-3.6.5
sudo ./configure --enable-optimizations
sudo make altinstall
```

>`make altinstall`을 사용한 이유는 기존의 `python`명령을 덮어쓰기 않기 위함

### 3. 설치 확인
```bash
python3.6 --version
```
정상적으로 나오면 설치 완료.