---
title: 释放一个正在运行的端口
tags: 
  - 日常
---

### <font color=FFC0CB> 第一步: </font> 查看你要关闭的端口的*PID*
`netstat -a -n -o | findstr :<Port Number>` (参数顺序可自定义)
 
### <font color=FFC0CB> 第二步: </font> 杀进程!
`taskkill /f /pid <PID>`


<br><br>

<span style="color: #1E90FF"> parameter的功能: </span>

```
-a => Displays all connections and listening ports.
-n => Displays addresses and port numbers in numerical form.
-o => Displays the owning process ID associated with each connection.
/F => Specifies to forcefully terminate the process(es).
/PID(processid) => Specifies the PID of the process to be terminated.   (Use TaskList to get the PID)
```

<span style="color: #1E90FF"> 管道符: </span>

```
pipe operator => The pipe operator (|) takes the output (by default, STDOUT) of one command and directs it into the input (by default, STDIN) of another command.
```
