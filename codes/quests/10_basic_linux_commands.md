📁 Level 1: 기본 탐색 및 폴더 조작

* 문제 1-1: 현재 위치 확인 : 
현재 작업 중인 디렉터리의 경로를 확인하세요
```shell
PS C:\Users\Administrator> pwd

Path
----
C:\Users\Administrator
```
문제 1-2: 폴더 구조 만들기

다음 폴더 구조를 생성하세요:

powershell_practice/

├── documents/

├── images/

├── backup/

└── temp/

```shell
PS C:\Users\Administrator> mkdir C:\Develops\quests\powershell_practice


    디렉터리: C:\Develops\quests


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:37                powershell_practice


PS C:\Users\Administrator> mkdir C:\Develops\quests\powershell_practice\documents


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:38                documents


PS C:\Users\Administrator> mkdir C:\Develops\quests\powershell_practice\images


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:38                images


PS C:\Users\Administrator> mkdir C:\Develops\quests\powershell_practice\backup


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:38                backup


PS C:\Users\Administrator> mkdir C:\Develops\quests\powershell_practice\temp


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:38                temp


PS C:\Users\Administrator> cd C:\Develops\quests\powershell_practice
PS C:\Develops\quests\powershell_practice> ls


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 3:38                backup
d-----      2025-07-15   오후 3:38                documents
d-----      2025-07-15   오후 3:38                images
d-----      2025-07-15   오후 3:38                temp
```

문제 1-3: 폴더 탐색

* documents 폴더로 이동하세요
* 현재 폴더의 내용을 확인하세요 (비어있을 것입니다)
* 다시 상위 폴더로 돌아가세요
```
PS C:\Develops\quests\powershell_practice> cd C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\documents> ls
PS C:\Develops\quests\powershell_practice\documents> cd ..
```


📄 Level 2: 파일 생성 및 조작

문제 2-1: 텍스트 파일 생성

* documents 폴더에 hello.txt 파일을 생성하고 "Hello PowerShell!" 내용을 입력하세요
* images 폴더에 photo1.jpg, photo2.png 빈 파일을 생성하세요

힌트: New-Item -ItemType File 또는 echo "내용" > 파일명 사용
```
PS C:\Develops\quests\powershell_practice> cd C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\documents> "Hello PowerShell!">hello.txt
PS C:\Develops\quests\powershell_practice\documents> ls


    디렉터리: C:\Develops\quests\powershell_practice\documents


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 3:51             40 hello.txt
```

문제 2-2: 파일 내용 확인

* hello.txt 파일의 내용을 출력하세요
* 현재 폴더의 모든 파일과 폴더 목록을 자세히 확인하세요

#cat이지만 powershell에서 사용하기 때문에 하지 못함.

문제 2-3: 파일 복사
* documents/hello.txt 파일을 backup 폴더에 복사하세요
* images 폴더의 모든 파일을 backup 폴더에 복사하세요
```
PS C:\Develops\quests\powershell_practice\backup> cp -r C:\Develops\quests\powershell_practice\images C:\Develops\quests\powershell_practice\backup
```

# 🔄 Level 3: 파일 이동 및 이름 변경
## 문제 3-1: 파일 이동
* temp 폴더에 test.txt 파일을 생성하세요
* 이 파일을 documents 폴더로 이동하세요
```shell
PS C:\Develops\quests\powershell_practice> cd C:\Develops\quests\powershell_practice\temp
PS C:\Develops\quests\powershell_practice\temp> "">test.txt
PS C:\Develops\quests\powershell_practice\temp> ls


    디렉터리: C:\Develops\quests\powershell_practice\temp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 4:19              6 test.txt


PS C:\Develops\quests\powershell_practice\temp> mv test.txt C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\temp> cd C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\documents> ls


    디렉터리: C:\Develops\quests\powershell_practice\documents


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 3:51             40 hello.txt
-a----      2025-07-15   오후 4:19              6 test.txt
```
## 문제 3-2: 파일 이름 변경
* documents/test.txt 파일의 이름을 moved_file.txt로 변경하세요
* images/photo1.jpg 파일의 이름을 picture1.jpg로 변경하세요


## 문제 3-3: 폴더 이름 변경
* temp 폴더의 이름을 temporary로 변경하세요
```
PS C:\Develops\quests\powershell_practice\temp> mv test.txt C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\temp> cd C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\documents> ls


    디렉터리: C:\Develops\quests\powershell_practice\documents


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 3:51             40 hello.txt
-a----      2025-07-15   오후 4:19              6 test.txt


PS C:\Develops\quests\powershell_practice\documents> mv test.txt moved_file.txt
PS C:\Develops\quests\powershell_practice\documents> ls


    디렉터리: C:\Develops\quests\powershell_practice\documents


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 3:51             40 hello.txt
-a----      2025-07-15   오후 4:19              6 moved_file.txt


PS C:\Develops\quests\powershell_practice\documents> cd C:\Develops\quests\powershell_practice\images
PS C:\Develops\quests\powershell_practice\images> "" >photo1.jpg
PS C:\Develops\quests\powershell_practice\images> ls


    디렉터리: C:\Develops\quests\powershell_practice\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 4:27              6 photo1.jpg


PS C:\Develops\quests\powershell_practice\images> mv photo1.jpg picture1.jpg
PS C:\Develops\quests\powershell_practice\images> ls


    디렉터리: C:\Develops\quests\powershell_practice\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 4:27              6 picture1.jpg


PS C:\Develops\quests\powershell_practice\images>
```

## 문제 3-3: 폴더 이름 변경
* temp 폴더의 이름을 temporary로 변경하세요
```shell
PS C:\Develops\quests\powershell_practice> rename-item temp temporary
PS C:\Develops\quests\powershell_practice> ls


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:06                backup
d-----      2025-07-15   오후 4:23                documents
d-----      2025-07-15   오후 4:28                images
d-----      2025-07-15   오후 4:21                temporary


PS C:\Develops\quests\powershell_practice>
```
# 🗑️ Level 4: 삭제 연습
## 문제 4-1: 개별 파일 삭제
* documents/moved_file.txt 파일을 삭제하세요
* images/photo2.png 파일을 삭제하세요
```
PS C:\Develops\quests\powershell_practice> rm C:\Develops\quests\powershell_practice\documents\moved_file.txt
PS C:\Develops\quests\powershell_practice> cd C:\Develops\quests\powershell_practice\documents
PS C:\Develops\quests\powershell_practice\documents> ls


    디렉터리: C:\Develops\quests\powershell_practice\documents


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 3:51             40 hello.txt


PS C:\Develops\quests\powershell_practice\images> ls


    디렉터리: C:\Develops\quests\powershell_practice\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 4:37              6 photo2.png
-a----      2025-07-15   오후 4:27              6 picture1.jpg


PS C:\Develops\quests\powershell_practice\images> rm C:\Develops\quests\powershell_practice\images\picture1.jpg
PS C:\Develops\quests\powershell_practice\images> ls


    디렉터리: C:\Develops\quests\powershell_practice\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2025-07-15   오후 4:37              6 photo2.png


PS C:\Develops\quests\powershell_practice\images>


```


## 문제 4-2: 폴더 삭제
* temporary 폴더를 삭제하세요 (비어있는 폴더)
* backup 폴더와 그 안의 모든 내용을 삭제하세요

```
```

🚀 Level 5: 종합 응용
문제 5-1: 프로젝트 구조 만들기
다음과 같은 프로젝트 구조를 생성하세요:
my_project/
├── src/
│   └── main.py (내용: "print('Hello World')")
├── docs/
│   └── readme.txt (내용: "This is my project")
├── tests/
└── build/

문제 5-2: 파일 정리
src/main.py 파일을 build 폴더에 복사하세요
docs/readme.txt 파일을 project_info.txt로 이름을 변경하세요
tests 폴더를 삭제하세요
문제 5-3: 최종 확인
my_project 폴더의 모든 하위 내용을 재귀적으로 확인하세요
각 폴더로 이동하여 파일 내용을 확인하세요

```
PS C:\Develops\quests\powershell_practice> mkdir C:\Develops\quests\powershell_practice\my_project


    디렉터리: C:\Develops\quests\powershell_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:41                my_project


PS C:\Develops\quests\powershell_practice> cd C:\Develops\quests\powershell_practice\my_project

PS C:\Develops\quests\powershell_practice\my_project> mkdir C:\Develops\quests\powershell_practice\my_project\src


    디렉터리: C:\Develops\quests\powershell_practice\my_project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:42                src


PS C:\Develops\quests\powershell_practice\my_project> mkdir C:\Develops\quests\powershell_practice\my_project\docs


    디렉터리: C:\Develops\quests\powershell_practice\my_project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:43                docs


PS C:\Develops\quests\powershell_practice\my_project> mkdir C:\Develops\quests\powershell_practice\my_project\tests


    디렉터리: C:\Develops\quests\powershell_practice\my_project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:43                tests


PS C:\Develops\quests\powershell_practice\my_project> mkdir C:\Develops\quests\powershell_practice\my_project\build


    디렉터리: C:\Develops\quests\powershell_practice\my_project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:43                build


PS C:\Develops\quests\powershell_practice\my_project> ls


    디렉터리: C:\Develops\quests\powershell_practice\my_project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-07-15   오후 4:43                build
d-----      2025-07-15   오후 4:43                docs
d-----      2025-07-15   오후 4:42                src
d-----      2025-07-15   오후 4:43                tests


PS C:\Develops\quests\powershell_practice\my_project>

PS C:\Develops\quests\powershell_practice\my_project> "print('Hello World')">main.py
PS C:\Develops\quests\powershell_practice\my_project> cd C:\Develops\quests\powershell_practice\my_project\src
PS C:\Develops\quests\powershell_practice\my_project\src> "print('Hello World')">main.py
PS C:\Develops\quests\powershell_practice\my_project\src> cd C:\Develops\quests\powershell_practice\my_project\docs
PS C:\Develops\quests\powershell_practice\my_project\docs> "This is my project">readme.txt
```