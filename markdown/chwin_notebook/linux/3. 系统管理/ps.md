ps


**** ps
     标准语法格式：
     ps -e # 查看所有的进程信息
     ps -ef # 全格式显示进程信息
     ps -ef | grep rsync # 查看rsync进程
     BSD语法格式：
     ps -ax
     ps -aux
     UID或USER代表进程执行用户
     PID为进程的唯一编号
     PPID为父进程ID编号
     %CPU代表CPU占用率
     %MEM代表内存点用率
     VSZ代表进程所使用的虚拟内存大小（单位为KB）
     RSS代表进程所使用的物理内存大小（单位为KB）
     TTY代表终端
     STIME或START代表进程启动时间
     STAT代表进程状态（D：不可中断的进程、R：正在运行的进程、S正在睡眠的进程、T：停止或被追踪的进程、X：死掉的进程、Z：僵尸进程）
     TIME代表进程占有CPU的总时间
     CMD或 COMMAND代表进程命令


     ps aux
     ps auxf
     ps -ef
     ps -le | grep mysql 查看有没有启动
     ps 可以查看使用的哪个shell程序
     ps -C apache2  #通过名字或者进程id显示进程
     ps -f -u www-data # 使用"-u"选项后跟用户名来过滤所属用户的进程。多个用户名可以用逗号分隔。

     ps不加参数，只显示当前控制台当前进程
     a显示每一个控制台当前进程
     u类似top显示方式，显示更多的项目
     x显示后台进程，[]括号中的不是进程，是内核线程。不占用用户空间的内存。
     f显示进程父子关系。


名称：ps
使用权限：所有使用者
使用方式：ps [options] [--help]
说明：显示瞬间行程 (process) 的动态
参数：
ps 的参数非常多, 在此仅列出几个常用的参数并大略介绍含义
-A 列出所有的行程
-w 显示加宽可以显示较多的资讯
-au 显示较详细的资讯
-aux 显示所有包含其他使用者的行程
au(x) 输出格式 :
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
USER: 行程拥有者
PID: pid
%CPU: 占用的 CPU 使用率
%MEM: 占用的记忆体使用率
VSZ: 占用的虚拟记忆体大小
RSS: 占用的记忆体大小
TTY: 终端的次要装置号码 (minor device number of tty)
STAT: 该行程的状态:
D: 不可中断的静止 (通悸□□缜b进行 I/O 动作)
R: 正在执行中
S: 静止状态
T: 暂停执行
Z: 不存在但暂时无法消除
W: 没有足够的记忆体分页可分配
<: 高优先序的行程
N: 低优先序的行程
L: 有记忆体分页分配并锁在记忆体内 (实时系统或捱A I/O)
START: 行程开始时间
TIME: 执行的时间
COMMAND:所执行的指令
范例：
ps
PID TTY TIME CMD
2791 ttyp0 00:00:00 tcsh
3092 ttyp0 00:00:00 ps
% ps -A
PID TTY TIME CMD
1 ? 00:00:03 init
2 ? 00:00:00 kflushd
3 ? 00:00:00 kpiod
4 ? 00:00:00 kswapd
5 ? 00:00:00 mdrecoveryd
.......
% ps -aux
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
root 1 0.0 0.7 1096 472 ? S Sep10 0:03 init [3]
root 2 0.0 0.0 0 0 ? SW Sep10 0:00 [kflushd]
root 3 0.0 0.0 0 0 ? SW Sep10 0:00 [kpiod]
root 4 0.0 0.0 0 0 ? SW Sep10 0:00 [kswapd]
........

ps aux
ps auxf
ps -ef
ps -le | grep mysql 查看有没有启动
ps 可以查看使用的哪个shell程序

ps不加参数，只显示当前控制台当前进程
a显示每一个控制台当前进程
u类似top显示方式
x显示后台进程
f显示进程父子关系。


名称：ps
使用权限：所有使用者
使用方式：ps [options] [--help]
说明：显示瞬间行程 (process) 的动态
参数：
ps 的参数非常多, 在此仅列出几个常用的参数并大略介绍含义
-A 列出所有的行程
-w 显示加宽可以显示较多的资讯
-au 显示较详细的资讯
-aux 显示所有包含其他使用者的行程
au(x) 输出格式 :
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
USER: 行程拥有者
PID: pid
%CPU: 占用的 CPU 使用率
%MEM: 占用的记忆体使用率
VSZ: 占用的虚拟记忆体大小
RSS: 占用的记忆体大小
TTY: 终端的次要装置号码 (minor device number of tty)
STAT: 该行程的状态:
D: 不可中断的静止 (通悸□□缜b进行 I/O 动作)
R: 正在执行中
S: 静止状态
T: 暂停执行
Z: 不存在但暂时无法消除
W: 没有足够的记忆体分页可分配
<: 高优先序的行程
N: 低优先序的行程
L: 有记忆体分页分配并锁在记忆体内 (实时系统或捱A I/O)
START: 行程开始时间
TIME: 执行的时间
COMMAND:所执行的指令
范例：
ps
PID TTY TIME CMD
2791 ttyp0 00:00:00 tcsh
3092 ttyp0 00:00:00 ps
% ps -A
PID TTY TIME CMD
1 ? 00:00:03 init
2 ? 00:00:00 kflushd
3 ? 00:00:00 kpiod
4 ? 00:00:00 kswapd
5 ? 00:00:00 mdrecoveryd
.......
% ps -aux
USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
root 1 0.0 0.7 1096 472 ? S Sep10 0:03 init [3]
root 2 0.0 0.0 0 0 ? SW Sep10 0:00 [kflushd]
root 3 0.0 0.0 0 0 ? SW Sep10 0:00 [kpiod]
root 4 0.0 0.0 0 0 ? SW Sep10 0:00 [kswapd]
........
