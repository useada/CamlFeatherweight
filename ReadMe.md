http://maskray.me/blog/2014-12-24-caml-compiler-overview


#工具链使用说明

在项目目录下执行make生成字节码编译器camlfwc、字节码解释器camlfwrun、字节码查看器camlfwod。
###编译并链接源文件得到可执行的字节码文件：
```
% ./camlfwc -v /tmp/a.ml -o /tmp/a.out
Compiling /tmp/a.ml
-: unit
Linking /tmp/a.zo -> /tmp/a.out
```
###使用camlfwrun执行：
```
% ./camlfwrun /tmp/a.out
```

###camlfwod可以显示目标文件或字节码可执行文件的指令列表。
```
% ./camlfwod /tmp/a.zo
%File /tmp/a.zo
Relocatable file

Offset 8
Length 33
0008: PUSHMARK
...

% ./camlfwod /tmp/a.out
File /tmp/a.out
Executable

Length 34
000c: PUSHMARK
%File /tmp/a.zo
Relocatable file

Offset 8
Length 33
0008: PUSHMARK
...
```
