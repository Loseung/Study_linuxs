# 리눅스 상대 주소 실습 문제
## 사전 준비: 실습 환경 설정
### 다음 명령어로 실습 환경을 준비하세요:
1. mkdir -p ~/practice/project/{src,docs,tests,config}
2. mkdir -p ~/practice/project/src/{main,utils}
3. mkdir -p ~/practice/project/docs/{user,dev}
4. mkdir -p ~/practice/project/tests/unit
5. touch ~/practice/project/README.md
6. touch ~/practice/project/src/main/app.py
7. touch ~/practice/project/src/utils/helper.py
8. touch ~/practice/project/docs/user/manual.txt
9. touch ~/practice/project/docs/dev/api.md
10. touch ~/practice/project/tests/test_main.py
11. touch ~/practice/project/config/settings.conf

완성된 디렉토리 구조:

~/practice/project/

├── README.md<br>
├── src/<br>
│   ├── main/<br>
│   │   └── app.py<br>
│   └── utils/<br>
│       └── helper.py<br>
├── docs/<br>
│   ├── user/<br>
│   │   └── manual.txt<br>
│   └── dev/<br>
│       └── api.md<br>
├── tests/<br>
│   ├── unit/<br>
│   └── test_main.py<br>
└── config/<br>
    └── settings.conf


## 연습문제 1: 기본 상대 주소 이해
### 1-1. 현재 위치에서 상대 주소 작성
현재 위치가 ~/practice/project/src/main/일 때, 다음 파일들로 이동하는 상대 주소를 작성하시오:<br>
1. helper.py 파일
```shell
[hoseung@localhost project]$ cd ./src/main/
[hoseung@localhost main]$ cd ../utils/
```
2. README.md 파일
```shell
[hoseung@localhost main]$ cd ../../
```
3. manual.txt 파일
```shell
[hoseung@localhost main]$ cd ../../docs/user/
```
4. settings.conf 파일
```shell
[hoseung@localhost main]$ cd ../../config/
```
### 1-2. 상대 주소 검증
위에서 작성한 상대 주소가 정확한지 다음 명령어로 확인하시오:

* cd ~/practice/project/src/main/
* ls [상대주소]

1. helper.py 파일
```shell
[hoseung@localhost main]$ ls ../utils/
helper.py
```
2. README.md 파일
```shell
[hoseung@localhost main]$ ls ../../
config  docs  README.md  src  tests
```
3. manual.txt 파일
```shell
[hoseung@localhost main]$ ls ../../docs/user/
manual.txt
```
4. settings.conf 파일
```shell
[hoseung@localhost main]$ ls ../../config/
settings.conf
```


## 연습문제 2: 다양한 시작점에서의 상대 주소
### 2-1. 시작점 변경 실습
현재 위치가 ~/practice/project/docs/user/일 때:

1. app.py 파일로 이동하는 상대 주소를 작성하시오.
```shell
[hoseung@localhost user]$ cd ../../src/main/
```
2. test_main.py 파일을 상대 주소를 작성하시오.
```shell
[hoseung@localhost user]$ cd ../../tests/
```
3. src/utils/ 디렉토리로 이동하는 상대 주소를 작성하시오.
```shell
[hoseung@localhost user]$ cd ../../src/utils/
```
### 2-2. 역방향 상대 주소
현재 위치가 ~/practice/project/tests/unit/일 때:

1. 프로젝트 루트(~/practice/project/)로 이동하는 상대 주소를 작성하시오.
```shell
[hoseung@localhost unit]$ cd ../../
```
2. api.md 파일로 이동하는 상대 주소를 작성하시오.
```shell
[hoseung@localhost unit]$ ../../docs/dev/
```
3. helper.py 파일로 이동하는 상대 주소를 작성하시오.
```shell
[hoseung@localhost unit]$ cd ../../src/utils/
```

## 연습문제 3: 파일 내용 확인 및 조작
### 3-1. 상대 주소를 이용한 파일 내용 출력
현재 위치가 ~/practice/project/src/utils/일 때:

1. 프로젝트 루트의 README.md 파일 내용을 출력하시오.
```shell
[hoseung@localhost utils]$ cat ../../README.md
```
2. docs/user/manual.txt 파일 정보 자세히 출력하시오.
```shell
[hoseung@localhost utils]$ ls -l ../../docs/user/manual.txt 
-rw-r--r--. 1 hoseung hoseung 0 Jul 16 16:34 ../../docs/user/manual.txt
```
3. config/settings.conf 파일 정보 자세히 출력하시오.
```shell
[hoseung@localhost utils]$ ls -l ../../config/settings.conf 
-rw-r--r--. 1 hoseung hoseung 0 Jul 16 16:34 ../../config/settings.conf
```
### 3-2. 상대 주소를 이용한 파일 생성
현재 위치가 ~/practice/project/src/main/일 때:

1. 현재 디렉토리에 config.py 파일을 생성하고 "# Configuration module"이라는 내용을 작성하시오.
```shell
[hoseung@localhost main]$ echo "#Configuration module" > config.py 
```
2. tests/ 디렉토리에 test_app.py 파일을 생성하고 "# App test file"이라는 내용을 작성하시오.
```shell
[hoseung@localhost main]$ echo "# App test file" > ../../tests/test_app.py
```

## 연습문제 4: 파일 복사 및 이동
### 4-1. 상대 주소를 이용한 파일 복사
현재 위치가 ~/practice/project/docs/dev/일 때:

1. api.md 파일을 docs/user/ 디렉토리에 api_copy.md로 복사하시오.
```shell
[hoseung@localhost dev]$ cp api.md ../user/api_copy.md
```
2. src/utils/helper.py 파일을 현재 디렉토리에 복사하시오.
```shell
[hoseung@localhost dev]$ cp ../../src/utils/helper.py ./
```
3. config/settings.conf 파일을 tests/unit/ 디렉토리에 복사하시오.
```shell
[hoseung@localhost dev]$ cp ../../src/main/config.py ../../tests/unit/
```
### 4-2. 상대 주소를 이용한 파일 이동
현재 위치가 ~/practice/project/tests/일 때:

1. test_main.py 파일을 tests/unit/ 디렉토리로 이동하시오.
```shell
[hoseung@localhost tests]$ mv test_main.py ./unit/
```
2. src/main/config.py 파일을 config/ 디렉토리로 이동하시오.
```shell
[hoseung@localhost tests]$ mv ../src/main/config.py ../config/
```

## 연습문제 5: 복합 상대 주소 활용
### 5-1. 다중 파일 조작
현재 위치가 ~/practice/project/일 때:

1. src/main/ 디렉토리의 모든 파일을 docs/dev/ 디렉토리에 복사하시오.
```shell
[hoseung@localhost project]$ cp ./src/main/app.py ./docs/dev/
```
2. docs/user/ 디렉토리의 모든 파일을 tests/unit/ 디렉토리로 이동하시오.
```shell
[hoseung@localhost project]$ mv ./docs/user/{api_copy.md,manual.txt} tests/unit/
```
3. config/ 디렉토리 전체를 backup_config/로 복사하시오.
```shell
[hoseung@localhost project]$ cp -r ./config/ ./backup_config/
```

## 연습문제 6: 에러 찾기 및 수정
### 6-1. 잘못된 상대 주소 찾기
현재 위치가 ~/practice/project/docs/user/일 때, 다음 명령어들 중 에러가 있는 것을 찾고 올바른 명령어로 수정하시오:

## A
ls ../../../project/src/main/


## B
cat ../../src/utils/helper.py


## C
cd ../dev/../../config/


## D
cp manual.txt ../../tests/unit/backup.txt
```shell
cp: cannot stat 'manual.txt': No such file or directory
```

## E
mv api_copy.md ../../../src/main/
```shell
mv: cannot stat 'api_copy.md': No such file or directory
```

### 6-2. 경로 최적화
다음 상대 주소를 더 간단하게 최적화하시오:
현재 위치: ~/practice/project/tests/unit/<br>

../../src/main/../utils/helper.py
```shell
../../src/utils/helper.py 
```
../../docs/user/../dev/api.md
```shell
../../docs/dev/api.md
```
../../config/../README.md
```shell
../../README.md
```


## 연습문제 7: 종합 실습
### 7-1. 프로젝트 구조 재정리
현재 위치가 ~/practice/project/일 때, 다음 작업을 수행하시오:

1. src/main/ 디렉토리에 models/ 하위 디렉토리를 생성하시오.
```shell
[hoseung@localhost project]$ mkdir -p ./src/main/models/
```
2. docs/ 디렉토리에 README.md 파일을 생성하고 "# Project Documentation"이라는 내용을 작성하시오.
```shell
[hoseung@localhost project]$ echo "# Project Documentation" > ./docs/README.md
```
3. tests/unit/ 디렉토리의 모든 파일을 tests/ 디렉토리로 이동하시오.
```shell
[hoseung@localhost project]$ mv ./tests/unit/{api_copy.md,config.py,manual.txt,test_main.py} ./tests/
```
4. config/ 디렉토리의 모든 파일을 src/ 디렉토리에 복사하시오.
```shell
[hoseung@localhost project]$ cp ./config/{config.py,settings.conf} ./src/
```
### 7-2. 백업 및 정리
현재 위치가 ~/practice/project/src/main/일 때:

1. 현재 내용을 ../../project_backup/으로 복사하시오..
```shell
[hoseung@localhost main]$ cp -r ./ ../../project_backup/
```
2. utils/ 디렉토리의 모든 .py 파일을 현재 디렉토리의 models/ 디렉토리로 복사하시오.
```shell
[hoseung@localhost main]$ cp ../utils/*.py ./models/
```
3. 프로젝트 루트의 README.md 파일을 현재 디렉토리에 PROJECT_INFO.md로 복사하시오.
```shell
[hoseung@localhost main]$ cp ../../README.md ./PROJECT_INFO.md
```

