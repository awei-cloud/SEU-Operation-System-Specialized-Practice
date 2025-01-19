# SEU 2024年 操作系统专题实践张竞慧老师课程实验
0本课程为实验课程，共安排三个综合实验，分别为：
 -
 -实验1：Linux进程管理及其扩展；
 -实验2：Shell的实现；
 -实验3：文件系统的实现，其中实验3为选做。
 -0

将文件下载后导入自己的虚拟机中即可
 
# 实验一
1.实验要求
 -
 - (1).实现系统调用int hide(pid_t pid, int on)，在进程pid有效的前提下，如果on置1，进程被隐藏，用户无法通过ps或top观察到进程状态；如果on置0且此前为隐藏状态，则恢复正常状态。
 - (2).考虑权限问题，只有根用户才能隐藏进程。
 - (3).设计一个新的系统调用int hide_user_processes(uid_t uid, char *binname)，参数uid为用户ID号，当binname参数为NULL时，隐藏该用户的所有进程；否则，隐藏二进制映像名为binname的用户进程。该系统调用应与hide系统调用共存。
 - (4).在/proc目录下创建一个文件/proc/hidden，该文件可读可写，对应一个全局变量hidden_flag，当hidden_flag为0时，所有进程都无法隐藏，即便此前进程被hide系统调用要求隐藏。只有当hidden_flag为1时，此前通过hide调用要求被屏蔽的进程才隐藏起来。（选做）
 - (5).在/proc目录下创建一个文件/proc/hidden_process，该文件的内容包含所有被隐藏进程的pid，各pid之间用空格分开。（选做）

2.具体实现
  -
  -在seu's home中两个文件hide_user.c和hide_user_processes.c，对应两个必做的测试文件，都需要在管理员模式下运行（实验一有要求，只有管理员才可以修改）
  -打开一个terminal终端，并进入管理员模式，该终端用来执行测试文件
  <img width="336" alt="image" src="https://github.com/user-attachments/assets/222c0996-0a1e-435b-96af-0a0386c16d8f" />

  -再打开一个terminal终端，进入后输入top-u seu，用来监看进程状态
  -4
  
# 实验二
1.实验要求
 -
 -实现具有管道、重定向功能的shell，能够执行一些简单的基本命令，如进程执行、列目录等。
 
2.具体实现
-

# 实验三
