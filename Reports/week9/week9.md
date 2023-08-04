## week 9

### 本周工作

1. 逐个验证已有的测试步骤文档，并进一步细化补充。

目前已验证：

- [AnghaBench](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/compilers/AnghaBench) 
- [Csmith](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/compilers/csmith)
- [DejaGnu ](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/compilers/dejagnu)
- [Jotai](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/compilers/jotai)
- [YARPGen ](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/compilers/yarpgen)
- [LTP](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/function/LTP)
- [Trinity](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/kernel/trinity)
- [ltpstress](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/long_stress/LTPstress)
- [fio](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/fio)
- [libMicro](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/libMicro)
- [lmbench ](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/lmbench)
- [Netperf](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/netperf)
- [stream](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/stream)
- [UnixBench](https://gitee.com/yunxiangluo/oerv-2303-test/tree/master/BasicTest/performance/unixbench)

2. 汇总目前 23.03 版本性能测试结果，作为 23.09 性能测试的基线。

#### fio 

主要指标：带宽BW，IOPS

QEMU 测试结果：

| 测试类型  | 块大小  | 测试结果                                      |
|-----------|---------|-----------------------------------------------|
| read      | 4096B   | [r=56.9MiB/s][r=14.6k IOPS]                   |
| read      | 16.0KiB | [r=217MiB/s][r=13.9k IOPS]                    |
| read      | 32.0KiB | [r=267MiB/s][r=8543 IOPS]                     |
| read      | 64.0KiB | [r=586MiB/s][r=9377 IOPS]                     |
| read      | 128KiB  | [r=849MiB/s][r=6794 IOPS]                     |
| read      | 256KiB  | [r=838MiB/s][r=3350 IOPS]                     |
| read      | 512KiB  | [r=675MiB/s][r=1350 IOPS]                     |
| read      | 1024KiB | [r=576MiB/s][r=576 IOPS]                      |
| write     | 4096B   | [w=45.4MiB/s][w=11.6k IOPS]                   |
| write     | 16.0KiB | [w=182MiB/s][w=11.6k IOPS]                    |
| write     | 32.0KiB | [w=90.2MiB/s][w=2885 IOPS]                    |
| write     | 64.0KiB | [w=407MiB/s][w=6515 IOPS]                     |
| write     | 128KiB  | [w=580MiB/s][w=4640 IOPS]                     |
| write     | 256KiB  | [w=796MiB/s][w=3183 IOPS]                     |
| write     | 512KiB  | [w=739MiB/s][w=1477 IOPS]                     |
| write     | 1024KiB | [w=731MiB/s][w=730 IOPS]                      |
| randread  | 4096B   | [r=49.7MiB/s][r=12.7k IOPS]                   |
| randread  | 16.0KiB | [r=200MiB/s][r=12.8k IOPS]                    |
| randread  | 32.0KiB | [r=224MiB/s][r=7183 IOPS]                     |
| randread  | 64.0KiB | [r=728MiB/s][r=11.6k IOPS]                    |
| randread  | 128KiB  | [r=822MiB/s][r=6579 IOPS]                     |
| randread  | 256KiB  | [r=731MiB/s][r=2922 IOPS]                     |
| randread  | 512KiB  | [r=782MiB/s][r=1563 IOPS]                     |
| randread  | 1024KiB | [r=698MiB/s][r=698 IOPS]                      |
| randwrite | 4096B   | [w=46.6MiB/s][w=11.9k IOPS]                   |
| randwrite | 16.0KiB | [w=185MiB/s][w=11.9k IOPS]                    |
| randwrite | 32.0KiB | [w=150MiB/s][w=4808 IOPS]                     |
| randwrite | 64.0KiB | [w=473MiB/s][w=7571 IOPS]                     |
| randwrite | 128KiB  | [w=428MiB/s][w=3425 IOPS]                     |
| randwrite | 256KiB  | [w=921MiB/s][w=3683 IOPS]                     |
| randwrite | 512KiB  | [w=755MiB/s][w=1509 IOPS]                     |
| randwrite | 1024KiB | [w=655MiB/s][w=654 IOPS]                      |
| randrw    | 4096B   | [r=34.6MiB/s,w=14.5MiB/s][r=8862,w=3706 IOPS] |
| randrw    | 16.0KiB | [r=134MiB/s,w=56.3MiB/s][r=8560,w=3604 IOPS]  |
| randrw    | 32.0KiB | [r=208MiB/s,w=88.7MiB/s][r=6659,w=2838 IOPS]  |
| randrw    | 64.0KiB | [r=397MiB/s,w=165MiB/s][r=6353,w=2637 IOPS]   |
| randrw    | 128KiB  | [r=672MiB/s,w=281MiB/s][r=5372,w=2251 IOPS]   |
| randrw    | 256KiB  | [r=671MiB/s,w=298MiB/s][r=2682,w=1192 IOPS]   |
| randrw    | 512KiB  | [r=506MiB/s,w=224MiB/s][r=1012,w=448 IOPS]    |
| randrw    | 1024KiB | [r=459MiB/s,w=215MiB/s][r=458,w=215 IOPS]     |

#### libMicro

主要指标：usecs/call

QEMU 测试结果：

| 测试类型       | 测试结果   |
|----------------|------------|
| getpid         | 0.67073    |
| getenv         | 0.37343    |
| getenvT2       | 0.46494    |
| gettimeofday   | 0.14568    |
| log            | 0.11214    |
| exp            | 0.10909    |
| lrand48        | 0.08267    |
| memset_10      | 0.0344     |
| memset_256     | 0.0596     |
| memset_256_u   | 0.08256    |
| memset_1k      | 0.17467    |
| memset_4k      | 0.62755    |
| memset_4k_uc   | 0.64496    |
| memset_10k     | 1.52392    |
| memset_1m      | 216.1712   |
| memset_10m     | 2122.4781  |
| memsetP2_10m   | 1809.3656  |
| memrand        | 0.04708    |
| isatty_yes     | 14.60078   |
| isatty_no      | 0.88149    |
| malloc_10      | 0.16545    |
| malloc_100     | 0.16314    |
| malloc_1k      | 0.19309    |
| malloc_10k     | 0.42279    |
| malloc_100k    | 50.36765   |
| mallocT2_10    | 0.19258    |
| mallocT2_100   | 0.29533    |
| mallocT2_1k    | 0.24117    |
| mallocT2_10k   | 0.42774    |
| mallocT2_100k  | 116.02743  |
| close_bad      | 0.83432    |
| close_tmp      | 3.4937     |
| close_usr      | 3.61695    |
| close_zero     | 3.65453    |
| memcpy_10      | 0.06905    |
| memcpy_1k      | 0.29666    |
| memcpy_10k     | 2.24735    |
| memcpy_1m      | 340.257    |
| memcpy_10m     | 3463.779   |
| strcpy_10      | 0.10979    |
| strcpy_1k      | 0.52546    |
| strlen_10      | 0.03598    |
| strlen_1k      | 0.22201    |
| strchr_10      | 0.03514    |
| strchr_1k      | 0.24746    |
| strcmp_10      | 0.05169    |
| strcmp_1k      | 1.95037    |
| scasecmp_10    | 0.08753    |
| scasecmp_1k    | 4.03543    |
| strtol         | 0.06781    |
| getcontext     | 7.23285    |
| setcontext     | 7.44894    |
| mutex_st       | 0.09808    |
| mutex_mt       | 0.1073     |
| mutex_T2       | 0.46267    |
| longjmp        | 0.07944    |
| siglongjmp     | 8.8504     |
| getrusage      | 15.61567   |
| times          | 13.99382   |
| time           | 0.09088    |
| localtime_r    | 0.60086    |
| strftime       | 2.16471    |
| mktime         | 54.85351   |
| mktimeT2       | 181.71974  |
| c_mutex_1      | 0.32444    |
| c_mutex_10     | 834.5394   |
| c_mutex_200    | 29593.3885 |
| c_cond_1       | 0.54692    |
| c_cond_10      | 882.52482  |
| c_cond_200     | 31148.46   |
| c_lockf_1      | 80.62813   |
| c_lockf_10     | 2464.268   |
| c_lockf_200    | 55704.329  |
| c_flock        | 10.14958   |
| c_flock_10     | 38.16631   |
| c_flock_200    | 8421.7995  |
| c_fcntl_1      | 83.97908   |
| c_fcntl_10     | 1983.666   |
| c_fcntl_200    | 64221.8295 |
| file_lock      | 41.61326   |
| getsockname    | 20.30389   |
| getpeername    | 20.08867   |
| chdir_tmp      | 145.64949  |
| chdir_usr      | 159.03835  |
| chgetwd_tmp    | 159.14785  |
| chgetwd_usr    | 172.36297  |
| realpath_tmp   | 419.14488  |
| realpath_usr   | 459.71718  |
| stat_tmp       | 101.05903  |
| stat_usr       | 113.61963  |
| fcntl_tmp      | 0.8907     |
| fcntl_usr      | 0.88891    |
| fcntl_ndelay   | 0.97494    |
| lseek_t8k      | 0.79785    |
| lseek_u8k      | 0.80246    |
| open_tmp       | 113.85532  |
| open_usr       | 126.38236  |
| open_zero      | 70.51538   |
| dup            | 1.24409    |
| socket_u       | 16.64439   |
| socket_i       | 18.14846   |
| socketpair     | 77.09223   |
| setsockopt     | 13.93984   |
| bind           | 31.39889   |
| listen         | 1.5198     |
| connection     | 310.57028  |
| poll_10        | 49.72951   |
| poll_100       | 363.08824  |
| poll_1000      | 3778.33285 |
| poll_w10       | 49.53175   |
| poll_w100      | 358.89344  |
| poll_w1000     | 3790.969   |
| select_10      | 27.38444   |
| select_100     | 55.82885   |
| select_1000    | 346.67435  |
| select_w10     | 36.39447   |
| select_w100    | 65.47642   |
| select_w1000   | 358.162    |
| semop          | 26.81363   |
| sigaction      | 15.66602   |
| signal         | 106.37982  |
| sigprocmask    | 14.86985   |
| pthread_16     | 347.12631  |
| pthread_32     | 364.96253  |
| pthread_128    | 365.61662  |
| pthread_512    | 365.24367  |
| fork_10        | 634.9897   |
| fork_100       | 598.31896  |
| fork_1000      | 1059.40566 |
| exit_10        | 317.602    |
| exit_100       | 194.27663  |
| exit_1000      | 745.42294  |
| exit_10_nolibc | 242.5963   |
| exec           | 5652.1767  |
| system         | 44190.815  |
| recurse        | 2.03268    |
| read_t1k       | 16.51213   |
| read_t10k      | 40.72991   |
| read_t100k     | 297.2339   |
| read_u1k       | 16.5178    |
| read_u10k      | 33.61815   |
| read_u100k     | 218.74195  |
| read_z1k       | 12.05136   |
| read_z10k      | 24.46379   |
| read_z100k     | 162.89527  |
| read_zw100k    | 167.17023  |
| write_t1k      | 28.17841   |
| write_t10k     | 75.6695    |
| write_t100k    | 592.265    |
| write_u1k      | 31.24399   |
| write_u10k     | 82.76836   |
| write_u100k    | 644.8988   |
| write_n1k      | 0.96981    |
| write_n10k     | 0.98492    |
| write_n100k    | 0.98181    |
| writev_t1k     | 146.01389  |
| writev_t10k    | 662.9954   |
| writev_t100k   | 5751.844   |
| writev_u1k     | 153.64695  |
| writev_u10k    | 711.5762   |
| writev_u100k   | 6311.004   |
| writev_n1k     | 15.73667   |
| writev_n10k    | 15.60274   |
| writev_n100k   | 15.81987   |
| pread_t1k      | 16.68011   |
| pread_t10k     | 39.74444   |
| pread_t100k    | 296.93755  |
| pread_u1k      | 16.25066   |
| pread_u10k     | 32.8888    |
| pread_u100k    | 218.69105  |
| pread_z1k      | 11.94098   |
| pread_z10k     | 25.03351   |
| pread_z100k    | 165.97596  |
| pread_zw100k   | 171.72063  |
| pwrite_t1k     | 28.02989   |
| pwrite_t10k    | 76.34017   |
| pwrite_t100k   | 583.0682   |
| pwrite_u1k     | 31.16967   |
| pwrite_u10k    | 81.99788   |
| pwrite_u100k   | 645.5872   |
| pwrite_n1k     | 0.94781    |
| pwrite_n10k    | 0.94576    |
| pwrite_n100k   | 0.94766    |
| mmap_z8k       | 11.95771   |
| mmap_z128k     | 11.91229   |
| mmap_t8k       | 12.71108   |
| mmap_t128k     | 12.80791   |
| mmap_u8k       | 12.84026   |
| mmap_u128k     | 12.47335   |
| mmap_a8k       | 6.57173    |
| mmap_a128k     | 6.56148    |
| mmap_rz8k      | 61.37702   |
| mmap_rz128k    | 469.77629  |
| mmap_rt8k      | 61.99838   |
| mmap_rt128k    | 266.7872   |
| mmap_ru8k      | 61.56851   |
| mmap_ru128k    | 282.0966   |
| mmap_ra8k      | 48.72884   |
| mmap_ra128k    | 439.5956   |
| mmap_wz8k      | 104.79791  |
| mmap_wz128k    | 941.96425  |
| mmap_wt8k      | 118.02371  |
| mmap_wt128k    | 1081.49375 |
| mmap_wu8k      | 112.31151  |
| mmap_wu128k    | 1073.22637 |
| mmap_wa8k      | 80.7693    |
| mmap_wa128k    | 883.1145   |
| unmap_z8k      | 13.97458   |
| unmap_z128k    | 13.51706   |
| unmap_t8k      | 13.70967   |
| unmap_t128k    | 13.57467   |
| unmap_u8k      | 13.94956   |
| unmap_u128k    | 13.50678   |
| unmap_a8k      | 22.53939   |
| unmap_a128k    | 22.74451   |
| unmap_rz8k     | 41.89202   |
| unmap_rz128k   | 47.51404   |
| unmap_rt8k     | 49.42864   |
| unmap_rt128k   | 84.78311   |
| unmap_ru8k     | 47.99408   |
| unmap_ru128k   | 85.81497   |
| unmap_ra8k     | 54.31694   |
| unmap_ra128k   | 58.42469   |
| conn_connect   | 93.10533   |
| unmap_wz8k     | 69.19459   |
| unmap_wz128k   | 163.47196  |
| unmap_wt8k     | 69.40855   |
| unmap_wt128k   | 154.3338   |
| unmap_wu8k     | 68.87259   |
| unmap_wu128k   | 165.99485  |
| unmap_wa8k     | 83.13392   |
| unmap_wa128k   | 184.49125  |
| mprot_z8k      | 12.79491   |
| mprot_z128k    | 11.90954   |
| mprot_wz8k     | 41.43372   |
| mprot_wz128k   | 41.53393   |
| mprot_twz8k    | 43.13524   |
| mprot_tw128k   | 42.61739   |
| mprot_tw4m     | 149.7892   |
| pipe_pst1      | 33.315     |
| pipe_pmt1      | 201.71956  |
| pipe_pmp1      | 199.81492  |
| pipe_pst4k     | 35.22354   |
| pipe_pmt4k     | 205.6927   |
| pipe_pmp4k     | 203.5169   |
| pipe_sst1      | 53.52482   |
| pipe_smt1      | 288.99442  |
| pipe_smp1      | 287.21742  |
| pipe_sst4k     | 73.29448   |
| pipe_smt4k     | 352.69816  |
| pipe_smp4k     | 350.05626  |
| pipe_tst1      | 139.08884  |
| pipe_tmt1      | 376.81752  |
| pipe_tmp1      | 373.9358   |
| pipe_tst4k     | 118.83441  |
| pipe_tmt4k     | 386.33556  |
| pipe_tmp4k     | 380.96058  |
| conn_accept    | 63.98824   |
| close_tcp      | 45.1465    |

#### lmbench

主要指标：latencies，bandwidths

QEMU 测试结果：

```
                 L M B E N C H  3 . 0   S U M M A R Y
                 ------------------------------------
		 (Alpha software, do not distribute)


Context switching - times in microseconds - smaller is better
-------------------------------------------------------------------------
Host                 OS  2p/0K 2p/16K 2p/64K 8p/16K 8p/64K 16p/16K 16p/64K
                         ctxsw  ctxsw  ctxsw ctxsw  ctxsw   ctxsw   ctxsw
--------- ------------- ------ ------ ------ ------ ------ ------- -------
openeuler Linux 6.1.19-   59.9   62.0   61.2   74.4   75.5    80.9    86.1

*Local* Communication latencies in microseconds - smaller is better
---------------------------------------------------------------------
Host                 OS 2p/0K  Pipe AF     UDP  RPC/   TCP  RPC/ TCP
                        ctxsw       UNIX         UDP         TCP conn
--------- ------------- ----- ----- ---- ----- ----- ----- ----- ----
openeuler Linux 6.1.19-  59.9            316.2       294.6       394.

File & VM system latencies in microseconds - smaller is better
-------------------------------------------------------------------------------
Host                 OS   0K File      10K File     Mmap    Prot   Page   100fd
                        Create Delete Create Delete Latency Fault  Fault  selct
--------- ------------- ------ ------ ------ ------ ------- ----- ------- -----
openeuler Linux 6.1.19-  208.0  159.6  559.0  231.7  875.3K                    

*Local* Communication bandwidths in MB/s - bigger is better
-----------------------------------------------------------------------------
Host                OS  Pipe AF    TCP  File   Mmap  Bcopy  Bcopy  Mem   Mem
                             UNIX      reread reread (libc) (hand) read write
--------- ------------- ---- ---- ---- ------ ------ ------ ------ ---- -----
openeuler Linux 6.1.19- 105. 178. 297.  381.5 6047.5 3239.4 2048.8 2978 3063.

Memory latencies in nanoseconds - smaller is better
    (WARNING - may not be correct, check graphs)
------------------------------------------------------------------------------
Host                 OS   Mhz   L1 $   L2 $    Main mem    Rand mem    Guesses
--------- -------------   ---   ----   ----    --------    --------    -------
openeuler Linux 6.1.19-  8988 2.6290 3.5840   26.1       139.1
```

#### netperf

主要指标：throughput，transaction rate

QEMU 测试结果：

| 测试项目                     | 测试结果 |
|------------------------------|----------|
| TCP STREAM                   | 0.31     |
| TCP STREAM                   | 19.29    |
| TCP STREAM                   | 34.05    |
| TCP STREAM                   | 55.68    |
| TCP STREAM                   | 87.81    |
| TCP STREAM                   | 143.09   |
| TCP STREAM                   | 172.2    |
| TCP STREAM                   | 231.84   |
| TCP STREAM                   | 503.5    |
| TCP STREAM                   | 682.53   |
| TCP STREAM                   | 802.42   |
| TCP STREAM                   | 711.28   |
| TCP STREAM                   | 738.58   |
| UDP STREAM                   | 0.12     |
| UDP STREAM                   | 7.38     |
| UDP STREAM                   | 15.2     |
| UDP STREAM                   | 30.13    |
| UDP STREAM                   | 59.97    |
| UDP STREAM                   | 119      |
| UDP STREAM                   | 132.26   |
| UDP STREAM                   | 179.85   |
| UDP STREAM                   | 299.44   |
| UDP STREAM                   | 389.76   |
| UDP STREAM                   | 479.16   |
| UDP STREAM                   | 566.07   |
| TCP REQUEST/RESPONSE         | 2041.68  |
| TCP Connect/Request/Response | 726.03   |
| UDP REQUEST/RESPONSE         | 1890.8   |

#### stream

主要指标：rate，time

QEMU 测试结果：

```
-------------------------------------------------------------
STREAM version $Revision: 5.10 $
-------------------------------------------------------------
This system uses 8 bytes per array element.
-------------------------------------------------------------
Array size = 10000000 (elements), Offset = 0 (elements)
Memory per array = 76.3 MiB (= 0.1 GiB).
Total memory required = 228.9 MiB (= 0.2 GiB).
Each kernel will be executed 10 times.
 The *best* time for each kernel (excluding the first iteration)
 will be used to compute the reported bandwidth.
-------------------------------------------------------------
Number of Threads requested = 8
Number of Threads counted = 8
-------------------------------------------------------------
Your clock granularity/precision appears to be 1 microseconds.
Each test below will take on the order of 22462 microseconds.
   (= 22462 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function    Best Rate MB/s  Avg time     Min time     Max time
Copy:           23081.3     0.007845     0.006932     0.008717
Scale:          10794.8     0.018168     0.014822     0.020507
Add:            13298.5     0.021114     0.018047     0.023301
Triad:          10068.4     0.026150     0.023837     0.029336
-------------------------------------------------------------
Solution Validates: avg error less than 1.000000e-13 on all three arrays
-------------------------------------------------------------
```

#### unixbench

主要指标：index value

QEMU 测试结果：

```
8 CPUs in system; running 8 parallel copies of tests

Dhrystone 2 using register variables       20449485.9 lps   (10.1 s, 7 samples)
Double-Precision Whetstone                     4876.5 MWIPS (10.1 s, 7 samples)
Execl Throughput                                301.2 lps   (29.6 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks         91327.7 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks           23040.9 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks        332662.0 KBps  (30.0 s, 2 samples)
Pipe Throughput                              126947.2 lps   (10.1 s, 7 samples)
Pipe-based Context Switching                  28651.2 lps   (10.1 s, 7 samples)
Process Creation                               1751.8 lps   (30.2 s, 2 samples)
Shell Scripts (1 concurrent)                    619.8 lpm   (60.4 s, 2 samples)
Shell Scripts (8 concurrent)                     85.5 lpm   (62.8 s, 2 samples)
System Call Overhead                         791249.9 lps   (10.2 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0   20449485.9   1752.3
Double-Precision Whetstone                       55.0       4876.5    886.6
Execl Throughput                                 43.0        301.2     70.1
File Copy 1024 bufsize 2000 maxblocks          3960.0      91327.7    230.6
File Copy 256 bufsize 500 maxblocks            1655.0      23040.9    139.2
File Copy 4096 bufsize 8000 maxblocks          5800.0     332662.0    573.6
Pipe Throughput                               12440.0     126947.2    102.0
Pipe-based Context Switching                   4000.0      28651.2     71.6
Process Creation                                126.0       1751.8    139.0
Shell Scripts (1 concurrent)                     42.4        619.8    146.2
Shell Scripts (8 concurrent)                      6.0         85.5    142.6
System Call Overhead                          15000.0     791249.9    527.5
                                                                   ========
System Benchmarks Index Score                                         230.4
```