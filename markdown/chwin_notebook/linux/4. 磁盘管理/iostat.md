iostat


**** iostat
     其各项的含义分别是：

     rrqm/s: 每秒进行 merge 的读操作数目.即 delta(rmerge)/s
     wrqm/s: 每秒进行 merge 的写操作数目.即 delta(wmerge)/s
     r/s: 每秒完成的读 I/O 设备次数.即 delta(rio)/s
     w/s: 每秒完成的写 I/O 设备次数.即 delta(wio)/s
     rsec/s: 每秒读扇区数.即 delta(rsect)/s
     wsec/s: 每秒写扇区数.即 delta(wsect)/s
     rkB/s: 每秒读K字节数.是 rsect/s 的一半,因为每扇区大小为512字节.(需要计算)
     wkB/s: 每秒写K字节数.是 wsect/s 的一半.(需要计算)
     avgrq-sz: 平均每次设备I/O操作的数据大小 (扇区).delta(rsect+wsect)/delta(rio+wio)
     avgqu-sz: 平均I/O队列长度.即 delta(aveq)/s/1000 (因为aveq的单位为毫秒).
     await: 平均每次设备I/O操作的等待时间 (毫秒).即 delta(ruse+wuse)/delta(rio+wio)
     svctm: 平均每次设备I/O操作的服务时间 (毫秒).即 delta(use)/delta(rio+wio)
     %util: 一秒中有百分之多少的时间用于 I/O 操作,或者说一秒中有多少时间 I/O 队列是非空的.即 delta(use)/s/1000 (因为use的单位为毫秒)
     如果 %util 接近 100%,说明产生的I/O请求太多,I/O系统已经满负荷,该磁盘可能存在瓶颈。

     idle小于70% IO压力就较大了,一般读取速度有较多的wait。

     同时可以结合vmstat查看查看b参数(等待资源的进程数)和wa参数(IO等待所占用的CPU时间的百分比,高过30%时IO压力高)，另外 await 的参数也要多和 svctm 来参考。差的过高就一定有 IO 的问题。

     avgrq-sz 也是个做 IO 调优时需要注意的地方,这个就是直接每次操作的数据的大小,如果次数多,但数据拿的小的话,其实 IO 也会很小.如果数据拿的大,才IO 的数据会高.也可以通过 avgqu-sz × ( r/s or w/s ) = rsec/s or wsec/s.也就是讲,读定速度是这个来决定的。

     svctm 一般要小于 await (因为同时等待的请求的等待时间被重复计算了),svctm 的大小一般和磁盘性能有关,CPU/内存的负荷也会对其有影响,请求过多也会间接导致 svctm 的增加.await 的大小一般取决于服务时间(svctm) 以及 I/O 队列的长度和 I/O 请求的发出模式.如果 svctm 比较接近 await,说明 I/O 几乎没有等待时间；如果 await 远大于 svctm,说明 I/O 队列太长,应用得到的响应时间变慢,如果响应时间超过了用户可以容许的范围,这时可以考虑更换更快的磁盘,调整内核 elevator 算法,优化应用,或者升级 CPU。

     队列长度(avgqu-sz)也可作为衡量系统 I/O 负荷的指标,但由于 avgqu-sz 是按照单位时间的平均值,所以不能反映瞬间的 I/O 洪水。

     有时间的话，我会单独写几个帖子来说说iostat。
