## **✅ 문제 : 간단한 서버 관리 스크립트 작성**

### **🔧 요구사항**

* `start`: 포트 8000에서 `http.server`를 백그라운드로 실행 (`nohup`, 로그는 `server.log`)

* `stop`: 실행 중인 프로세스를 찾아 종료

* `status`: 프로세스가 실행 중인지 확인하여 출력

* `restart`: 중지 후 다시 실행

  ### **🎯 실행 예시**

  $ ./webserver.sh start  
  서버가 백그라운드에서 시작되었습니다.  


  $ ./webserver.sh status  
  서버 실행 중입니다. PID: 13579  
    
  $ ./webserver.sh stop  
  서버가 종료되었습니다.  
    
  $ ./[webserver.sh](http://webserver.sh) tail\_log  
  … log message 확인


문제 모두 조건에 따라:

* `if [ "$1" == "start" ]` 식으로 흐름 제어

* 변수 `PORT`, `PID`, `LOGFILE` 등을 정의해 구성 가능


```shell
#vim
#!/bin/bash

V_PORT="8000"
V_PID="$(ps aux | grep "[h]ttp" | tr -s ' ' | cut -d " " -f2 | head -n1)"
V_LOGFILE=http_server.log

if [ "$1" = "start" ]; then
       nohup python3 -m http.server "$V_PORT" --bind 0.0.0.0 &>> "$V_LOGFILE" &
       echo "서버가 백그라운드에서 시작되었습니다."
elif [ "$1" = "status" ]; then
        if [ -z "$V_PID" ]; then
                echo "서버가 실행중이지 않습니다."
        else
                echo "서버 실행 중입니다. PID: $V_PID"
        fi
elif [ "$1" = "stop" ]; then
        kill "$V_PID"
        echo "서버가 종료되었습니다."
elif [ "$1" = "tail_log" ]; then
        cat http_server.log
else
        echo "xxxx"
fi

[hoseung@192.168.0.37 ~/quests]$ bash webserver.sh start
서버가 백그라운드에서 시작되었습니다.
nohup: redirecting stderr to stdout

[hoseung@192.168.0.37 ~/quests]$ bash webserver.sh status
서버 실행 중입니다. PID: 7419

[hoseung@192.168.0.37 ~/quests]$ bash webserver.sh stop
서버가 종료되었습니다.

#서버 종료 후 status
[hoseung@192.168.0.37 ~/quests]$ bash webserver.sh status
서버가 실행중이지 않습니다.

[hoseung@192.168.0.37 ~/quests]$ bash webserver.sh tail_log
Traceback (most recent call last):
  File "/usr/lib64/python3.9/runpy.py", line 197, in _run_module_as_main
    return _run_code(code, main_globals, None,
  File "/usr/lib64/python3.9/runpy.py", line 87, in _run_code
    exec(code, run_globals)
  File "/usr/lib64/python3.9/http/server.py", line 1308, in <module>
    test(
  File "/usr/lib64/python3.9/http/server.py", line 1259, in test
    with ServerClass(addr, HandlerClass) as httpd:
  File "/usr/lib64/python3.9/socketserver.py", line 452, in __init__
    self.server_bind()
  File "/usr/lib64/python3.9/http/server.py", line 1302, in server_bind
    return super().server_bind()
  File "/usr/lib64/python3.9/http/server.py", line 137, in server_bind
    socketserver.TCPServer.server_bind(self)
  File "/usr/lib64/python3.9/socketserver.py", line 466, in server_bind
    self.socket.bind(self.server_address)


```