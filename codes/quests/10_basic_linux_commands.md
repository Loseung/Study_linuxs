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
