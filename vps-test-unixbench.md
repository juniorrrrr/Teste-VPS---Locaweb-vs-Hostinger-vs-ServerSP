# Testing VPS performance using `unixbench`

Init:
```sh
wget https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/byte-unixbench/UnixBench5.1.3.tgz
tar zxf ./UnixBench5.1.3.tgz
cd ./UnixBench
./Run
```

### Locaweb
- 2 core / 1 GB RAM / 40 GB SSD

```
Benchmark Run: Fri Sep 27 2019 13:51:24 - 14:19:39
2 CPUs in system; running 1 parallel copy of tests

Dhrystone 2 using register variables       17757337.6 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                     3550.6 MWIPS (9.8 s, 7 samples)
Execl Throughput                               1212.6 lps   (29.8 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks        308778.8 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks           86974.0 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks        775831.7 KBps  (30.0 s, 2 samples)
Pipe Throughput                              595565.5 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                  19377.4 lps   (10.0 s, 7 samples)
Process Creation                               2921.7 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                   4279.9 lpm   (60.1 s, 2 samples)
Shell Scripts (8 concurrent)                    866.9 lpm   (60.1 s, 2 samples)
System Call Overhead                         624143.6 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0   17757337.6   1521.6
Double-Precision Whetstone                       55.0       3550.6    645.6
Execl Throughput                                 43.0       1212.6    282.0
File Copy 1024 bufsize 2000 maxblocks          3960.0     308778.8    779.7
File Copy 256 bufsize 500 maxblocks            1655.0      86974.0    525.5
File Copy 4096 bufsize 8000 maxblocks          5800.0     775831.7   1337.6
Pipe Throughput                               12440.0     595565.5    478.8
Pipe-based Context Switching                   4000.0      19377.4     48.4
Process Creation                                126.0       2921.7    231.9
Shell Scripts (1 concurrent)                     42.4       4279.9   1009.4
Shell Scripts (8 concurrent)                      6.0        866.9   1444.9
System Call Overhead                          15000.0     624143.6    416.1
                                                                   ========
System Benchmarks Index Score                                         530.4

------------------------------------------------------------------------
Benchmark Run: Fri Sep 27 2019 14:19:39 - 14:47:46
2 CPUs in system; running 2 parallel copies of tests

Dhrystone 2 using register variables       32895658.0 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                     7039.7 MWIPS (9.2 s, 7 samples)
Execl Throughput                               4334.0 lps   (29.8 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks        435467.5 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks          132399.5 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks       1116341.8 KBps  (30.0 s, 2 samples)
Pipe Throughput                             1197962.2 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                 165934.4 lps   (10.0 s, 7 samples)
Process Creation                              10307.2 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                   7499.9 lpm   (60.0 s, 2 samples)
Shell Scripts (8 concurrent)                    974.8 lpm   (60.1 s, 2 samples)
System Call Overhead                        1146973.7 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0   32895658.0   2818.8
Double-Precision Whetstone                       55.0       7039.7   1279.9
Execl Throughput                                 43.0       4334.0   1007.9
File Copy 1024 bufsize 2000 maxblocks          3960.0     435467.5   1099.7
File Copy 256 bufsize 500 maxblocks            1655.0     132399.5    800.0
File Copy 4096 bufsize 8000 maxblocks          5800.0    1116341.8   1924.7
Pipe Throughput                               12440.0    1197962.2    963.0
Pipe-based Context Switching                   4000.0     165934.4    414.8
Process Creation                                126.0      10307.2    818.0
Shell Scripts (1 concurrent)                     42.4       7499.9   1768.8
Shell Scripts (8 concurrent)                      6.0        974.8   1624.7
System Call Overhead                          15000.0    1146973.7    764.6
                                                                   ========
System Benchmarks Index Score                                        1131.9
```
:snail: A Locaweb tem *2 cores*, devido a isso é feito um teste com apenas 1 core e outro teste com os 2 cores, o resultado é de assustar, nem com 2 cores ela consegue superar os outros.  


### ServerSP
- 1 core / 1 GB RAM / 25 GB SSD

```
Benchmark Run: Fri Sep 27 2019 13:03:21 - 13:31:25
1 CPU in system; running 1 parallel copy of tests

Dhrystone 2 using register variables       32730708.5 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                     4611.8 MWIPS (9.8 s, 7 samples)
Execl Throughput                               5124.8 lps   (30.0 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks       1033023.9 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks          299427.1 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks       2055630.8 KBps  (30.0 s, 2 samples)
Pipe Throughput                             2474628.9 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                 288633.6 lps   (10.0 s, 7 samples)
Process Creation                              15163.4 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                   9454.8 lpm   (60.0 s, 2 samples)
Shell Scripts (8 concurrent)                   1206.4 lpm   (60.0 s, 2 samples)
System Call Overhead                        3716832.9 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0   32730708.5   2804.7
Double-Precision Whetstone                       55.0       4611.8    838.5
Execl Throughput                                 43.0       5124.8   1191.8
File Copy 1024 bufsize 2000 maxblocks          3960.0    1033023.9   2608.6
File Copy 256 bufsize 500 maxblocks            1655.0     299427.1   1809.2
File Copy 4096 bufsize 8000 maxblocks          5800.0    2055630.8   3544.2
Pipe Throughput                               12440.0    2474628.9   1989.3
Pipe-based Context Switching                   4000.0     288633.6    721.6
Process Creation                                126.0      15163.4   1203.4
Shell Scripts (1 concurrent)                     42.4       9454.8   2229.9
Shell Scripts (8 concurrent)                      6.0       1206.4   2010.6
System Call Overhead                          15000.0    3716832.9   2477.9
                                                                   ========
System Benchmarks Index Score                                        1762.7

```
