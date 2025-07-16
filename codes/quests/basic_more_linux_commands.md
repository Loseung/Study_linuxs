# 연습문제 1: 기본 파일 시스템 탐색
## 1-1. 현재 위치 확인 및 이동
* 현재 작업 디렉터pw리의 절대 경로를 출력하시오.
```shell
[hoseung@localhost ~]$ pwd
```
* 홈 디렉터리로 이동하시오.
```shell
[hoseung@localhost ~]$ cd ~
```
* 루트 디렉터리(/)로 이동하시오.
```shell
[hoseung@localhost ~]$ cd /
```
* 다시 홈 디렉터리로 돌아가시오.
```shell
[hoseung@localhost /]$ cd ~
```
## 1-2. 디렉터리 내용 확인
* 현재 디렉터리의 파일과 폴더 목록을 출력하시오.
```shell
[hoseung@localhost ~]$ ls
```
* 숨김 파일을 포함한 모든 파일의 상세 정보를 출력하시오.
```shell
[hoseung@localhost ~]$ ls -al
```
* /etc 디렉터리의 내용을 확인하시오.


# 연습문제 2: 디렉터리 및 파일 생성
## 2-1. 디렉터리 구조 생성
다음과 같은 디렉터리 구조를 생성하시오:

practice/

├── documents/

│   ├── reports/ls

│   └── notes/

├── images/

└── backup/
```shell
[hoseung@localhost ~]$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
[hoseung@localhost ~]$ mkdir practice
[hoseung@localhost ~]$ ls
Desktop    Downloads  Pictures  Public     Videos
Documents  Music      practice  Templates
[hoseung@localhost ~]$ pwd
/home/hoseung
[hoseung@localhost ~]$ cd /home/hoseung/practice
[hoseung@localhost practice]$ pwd
/home/hoseung/practice
[hoseung@localhost practice]$ mkdir documents
[hoseung@localhost practice]$ mkdir images
[hoseung@localhost practice]$ mkdir backup
[hoseung@localhost practice]$ ls
backup  documents  images
[hoseung@localhost practice]$ cd /home/hoseung/practice/documents/reports
bash: cd: /home/hoseung/practice/documents/reports: No such file or directory
[hoseung@localhost practice]$ cd /home/hoseung/practice/documents
[hoseung@localhost documents]$ mkdir reports
[hoseung@localhost documents]$ notes
bash: notes: command not found...
[hoseung@localhost documents]$ mkdir notes
[hoseung@localhost documents]$ cd /home/hoseung/practice/documents/reports
[hoseung@localhost reports]$ mkidr ls
bash: mkidr: command not found...
Similar command is: 'mkdir'
[hoseung@localhost reports]$ ls
[hoseung@localhost reports]$ pwd
/home/hoseung/practice/documents/reports
[hoseung@localhost reports]$ mkdir ls

```
## 2-2. 파일 생성 및 내용 작성
* practice/documents/ 디렉터리에 readme.txt 파일을 생성하고 "Hello Linux!"라는 내용을 작성하시오. (Pass)
* practice/notes/ 디렉터리에 memo.txt 파일을 생성하고 "Linux 명령어 연습 중"이라는 내용을 작성하시오.
```shell
[hoseung@localhost reports]$ pwd
/home/hoseung/practice/documents/reports
[hoseung@localhost reports]$ cd /home/hoseung/practice/documents
[hoseung@localhost documents]$ touch readme.txt
[hoseung@localhost documents]$ ls
notes  readme.txt  reports
[hoseung@localhost documents]$ cd /home/hoseung/practice/notes
bash: cd: /home/hoseung/practice/notes: No such file or directory
[hoseung@localhost documents]$ cd /home/hoseung/practice/documents/notes
[hoseung@localhost notes]$ touch memo.txt
[hoseung@localhost notes]$ ls
memo.txt

```
# 연습문제 3: 파일 내용 확인 및 조작
## 3-1. 파일 내용 출력
* 앞서 생성한 readme.txt 파일의 내용을 출력하시오.
* memo.txt 파일의 내용을 출력하시오.
```shell
[hoseung@localhost documents]$ cd /home/hoseung/practice/documents
[hoseung@localhost documents]$ cat readme.txt
#내용을 입력하지 않아 내용이 보이지 않음.
[hoseung@localhost documents]$ cd /home/hoseung/practice/documents/notes
[hoseung@localhost notes]$ cat memo.txt

```
## 3-2. 파일 복사
* readme.txt 파일을 backup/ 디렉터리에 복사하시오.
* documents/ 디렉터리 전체를 backup/ 디렉터리에 복사하시오.
```shell
[hoseung@localhost notes]$ ls
memo.txt
[hoseung@localhost notes]$ cd ..
[hoseung@localhost documents]$ ls
notes  readme.txt  reports
[hoseung@localhost documents]$ cd /home/hoseung/practice/backup/
[hoseung@localhost backup]$ pwd
/home/hoseung/practice/backup
[hoseung@localhost backup]$ cd /home/hoseung/practice/documents
[hoseung@localhost documents]$ cp readme.txt /home/hoseung/practice/backup
[hoseung@localhost documents]$ cd /home/hoseung/practice/backup/
[hoseung@localhost backup]$ ls
readme.txt
[hoseung@localhost documents]$ cp -r /home/hoseung/practice/documents/ /home/hoseung/practice/backup
```
# 연습문제 4: 파일 이동 및 이름 변경
## 4-1. 파일 이동
* memo.txt 파일을 documents/ 디렉터리로 이동하시오.
* images/ 디렉터리를 practice/media/로 이름을 변경하시오.
```shell
[hoseung@localhost documents]$ pwd
/home/hoseung/practice/documents
[hoseung@localhost documents]$ cd /home/hoseung/practice/documents/notes/
[hoseung@localhost notes]$ mv memo.txt /home/hoseung/practice/documents/
[hoseung@localhost notes]$ cd /home/hoseung/practice/
[hoseung@localhost practice]$ mv images/ media/
```
## 4-2. 파일 이름 변경
* readme.txt를 introduction.txt로 이름을 변경하시오.
* memo.txt를 study_notes.txt로 이름을 변경하시오.
```shell
[hoseung@localhost documents]$ mv readme.txt introduction.txt

[hoseung@localhost documents]$ mv memo.txt study_notes.txt

```
# 연습문제 5: 종합 실습
## 5-1. 프로젝트 디렉터리 생성
* 다음 요구사항에 따라 프로젝트 디렉터리를 생성하시오:
* my_project/라는 최상위 디렉터리 생성
1. 하위에 src/, docs/, tests/, config/ 디렉터리 생성
2. src/ 디렉터리에 main.py 파일 생성 (내용: "# Main Python File")
3. docs/ 디렉터리에 README.md 파일 생성 (내용: "# My Project Documentation")
4. config/ 디렉터리에 settings.conf 파일 생성 (내용: "# Configuration File")
```shell
[hoseung@localhost ~]$ mkdir my_project/
[hoseung@localhost ~]$ cd /home/hoseung/my_project/
[hoseung@localhost my_project]$ mkdir src
[hoseung@localhost my_project]$ mkdir docs
[hoseung@localhost my_project]$ mkdir tests
[hoseung@localhost my_project]$ mkdir config
[hoseung@localhost my_project]$ cd /home/hoseung/my_project/src/
[hoseung@localhost src]$ touch main.py
[hoseung@localhost src]$ cd /home/hoseung/my_project/docs/
[hoseung@localhost docs]$ touch README.md
[hoseung@localhost docs]$ cd /home/hoseung/my_project/config/
[hoseung@localhost config]$ touch settings.conf

```
## 5-2. 백업 및 정리
* 전체 my_project/ 디렉터리를 my_project_backup/으로 복사하시오.
* my_project/src/main.py 파일을 my_project/src/app.py로 이름을 변경하시오.
* my_project/docs/README.md 파일을 my_project/ 디렉터리로 이동하시오.
```shell
[hoseung@localhost ~]$ mkdir my_project_backup/
[hoseung@localhost ~]$ cp -r /home/hoseung/my_project/ /home/hoseung/my_project_backup/
[hoseung@localhost src]$ cd /home/hoseung/my_project/src/
[hoseung@localhost src]$ mv main.py app.py
[hoseung@localhost src]$ cd /home/hoseung/my_project/docs/
[hoseung@localhost docs]$ mv README.md /home/hoseung/my_project/
```