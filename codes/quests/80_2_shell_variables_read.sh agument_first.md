# 인자와 read를 함께 사용하여 변수 조합 출력

~$ 80_2_shell_variables_read.sh agument_first

 read input : read_first

input values : agument_first read_first

```shell

#nano   80_2_shell_variables_read.sh           

V_INPUT="$1"
read -p "input value : " read_first
echo input value : "$V_INPUT" "$read_first"


[hoseung@localhost quests]$ source 80_2_shell_variables_read.sh agumont_first
input value : read_first
input value : agumont_first read_first

```