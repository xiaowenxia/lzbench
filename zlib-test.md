### 使用 git 的 packfile 来测试

zlib
```sh
$ ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack 
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  11772 MB/s 11923 MB/s  2138971096 100.00 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -1           55.0 MB/s   450 MB/s  1918339132  89.69 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -2           54.1 MB/s   449 MB/s  1915742359  89.56 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -3           53.3 MB/s   449 MB/s  1913367586  89.45 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -4           50.0 MB/s   443 MB/s  1904758916  89.05 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -5           48.3 MB/s   444 MB/s  1900011411  88.83 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -6           46.6 MB/s   445 MB/s  1898720097  88.77 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-ng
```sh
LD_LIBRARY_PATH=/opt/zlib-ng/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack 
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  11726 MB/s 11714 MB/s  2138971096 100.00 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -1            214 MB/s   636 MB/s  2043080488  95.52 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -2           85.3 MB/s   594 MB/s  1912360057  89.41 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -3           83.7 MB/s   596 MB/s  1908661510  89.23 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -4           56.6 MB/s   598 MB/s  1901911606  88.92 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -5           56.2 MB/s   599 MB/s  1900506323  88.85 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -6           55.9 MB/s   599 MB/s  1900119181  88.83 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-cloudflare
```sh
➜  lzbench LD_LIBRARY_PATH=/opt/zlib-cloudflare/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  11811 MB/s 11934 MB/s  2138971096 100.00 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -1           75.6 MB/s   563 MB/s  1913219371  89.45 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -2           75.0 MB/s   564 MB/s  1910856191  89.34 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -3           73.8 MB/s   563 MB/s  1909118054  89.25 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -4           69.2 MB/s   564 MB/s  1904695698  89.05 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -5           67.3 MB/s   566 MB/s  1899725803  88.81 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -6           66.3 MB/s   565 MB/s  1899224182  88.79 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-dougallj
```sh
LD_LIBRARY_PATH=/opt/zlib-dougallj/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack 
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  11815 MB/s 11890 MB/s  2138971096 100.00 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -1           76.2 MB/s   591 MB/s  1913219371  89.45 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -2           75.6 MB/s   592 MB/s  1910856191  89.34 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -3           74.9 MB/s   592 MB/s  1909118054  89.25 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -4           69.9 MB/s   592 MB/s  1904695698  89.05 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -5           68.5 MB/s   594 MB/s  1899725803  88.81 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
zlib 1.2.11 -6           67.3 MB/s   593 MB/s  1899224182  88.79 ./linux.git/objects/pack/pack-c166dd1bf13545f5413d6f9fb05f2b7941152b7a.pack
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```


### 使用通用的 silesia.tar 测试

```sh
$ ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./silesia.tar 
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  12588 MB/s 12561 MB/s   211957760 100.00 ./silesia.tar
zlib 1.2.11 -1            113 MB/s   476 MB/s    77259073  36.45 ./silesia.tar
zlib 1.2.11 -2            104 MB/s   491 MB/s    75002641  35.39 ./silesia.tar
zlib 1.2.11 -3           81.5 MB/s   506 MB/s    72967276  34.43 ./silesia.tar
zlib 1.2.11 -4           75.6 MB/s   488 MB/s    71003088  33.50 ./silesia.tar
zlib 1.2.11 -5           56.7 MB/s   492 MB/s    69161924  32.63 ./silesia.tar
zlib 1.2.11 -6           38.4 MB/s   501 MB/s    68228590  32.19 ./silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-cloudflare 
```sh
$ LD_LIBRARY_PATH=/opt/zlib-cloudflare/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./silesia.tar                                                   
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  12576 MB/s 12573 MB/s   211957760 100.00 ./silesia.tar
zlib 1.2.11 -1            181 MB/s   722 MB/s    75880072  35.80 ./silesia.tar
zlib 1.2.11 -2            169 MB/s   744 MB/s    74183403  35.00 ./silesia.tar
zlib 1.2.11 -3            144 MB/s   756 MB/s    72839815  34.37 ./silesia.tar
zlib 1.2.11 -4            130 MB/s   772 MB/s    70925978  33.46 ./silesia.tar
zlib 1.2.11 -5            101 MB/s   773 MB/s    69106398  32.60 ./silesia.tar
zlib 1.2.11 -6           75.4 MB/s   779 MB/s    68564217  32.35 ./silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-ng
```sh
$ LD_LIBRARY_PATH=/opt/zlib-ng/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./silesia.tar
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  12540 MB/s 12591 MB/s   211957760 100.00 ./silesia.tar
zlib 1.2.11 -1            340 MB/s   698 MB/s   100931163  47.62 ./silesia.tar
zlib 1.2.11 -2            182 MB/s   730 MB/s    75289332  35.52 ./silesia.tar
zlib 1.2.11 -3            143 MB/s   763 MB/s    72491203  34.20 ./silesia.tar
zlib 1.2.11 -4            115 MB/s   784 MB/s    69803598  32.93 ./silesia.tar
zlib 1.2.11 -5            105 MB/s   792 MB/s    69235436  32.66 ./silesia.tar
zlib 1.2.11 -6           87.1 MB/s   799 MB/s    68913632  32.51 ./silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

zlib-dougallj
```sh
LD_LIBRARY_PATH=/opt/zlib-dougallj/lib ./lzbench -t16,16 -ezlib,1,2,3,4,5,6 ./silesia.tar
lzbench 1.8 (64-bit Linux)  AMD Ryzen 5 5600X 6-Core Processor             
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                  12429 MB/s 12461 MB/s   211957760 100.00 ./silesia.tar
zlib 1.2.11 -1            182 MB/s   959 MB/s    75880072  35.80 ./silesia.tar
zlib 1.2.11 -2            171 MB/s   988 MB/s    74183403  35.00 ./silesia.tar
zlib 1.2.11 -3            146 MB/s  1010 MB/s    72839815  34.37 ./silesia.tar
zlib 1.2.11 -4            132 MB/s  1035 MB/s    70925978  33.46 ./silesia.tar
zlib 1.2.11 -5            102 MB/s  1049 MB/s    69106398  32.60 ./silesia.tar
zlib 1.2.11 -6           76.4 MB/s  1059 MB/s    68564217  32.35 ./silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```


nvcomp_deflate
```
[root@xxwGPU lzbench]#  ./lzbench -envcomp_deflate/zlib -t16,16 /disk1/silesia.tar
lzbench 1.8 (64-bit Linux)  Intel(R) Xeon(R) Platinum 8163 CPU @ 2.50GHz
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                   6000 MB/s  5945 MB/s   211957760 100.00 /disk1/silesia.tar
nvcomp_deflate 2.3 -0     883 MB/s      ERROR    88711038  41.85 /disk1/silesia.tar
nvcomp_deflate 2.3 -1    71.9 MB/s      ERROR    69638189  32.85 /disk1/silesia.tar
zlib 1.2.11 -1           73.2 MB/s   233 MB/s    77257276  36.45 /disk1/silesia.tar
zlib 1.2.11 -2           64.8 MB/s   240 MB/s    75000804  35.38 /disk1/silesia.tar
zlib 1.2.11 -3           48.7 MB/s   248 MB/s    72970496  34.43 /disk1/silesia.tar
zlib 1.2.11 -4           45.8 MB/s   242 MB/s    70998310  33.50 /disk1/silesia.tar
zlib 1.2.11 -5           31.3 MB/s   244 MB/s    69158092  32.63 /disk1/silesia.tar
zlib 1.2.11 -6           20.9 MB/s   249 MB/s    68225177  32.19 /disk1/silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```

```
[root@xxwGPU lzbench]#  ./lzbench -envcomp_lz4/lz4 -t16,16 /disk1/silesia.tar
lzbench 1.8 (64-bit Linux)  Intel(R) Xeon(R) Platinum 8163 CPU @ 2.50GHz
Assembled by P.Skibinski

Compressor name         Compress. Decompress. Compr. size  Ratio Filename
memcpy                   6038 MB/s  6000 MB/s   211957760 100.00 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -0      1188 MB/s      ERROR   110662127  52.21 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -1      1089 MB/s      ERROR   107532249  50.73 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -2       999 MB/s      ERROR   106588123  50.29 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -3       944 MB/s      ERROR   106008710  50.01 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -4       822 MB/s      ERROR   105707886  49.87 /disk1/silesia.tar
nvcomp_lz4 1.2.2 -5       568 MB/s      ERROR   105549308  49.80 /disk1/silesia.tar
lz4 1.9.3                 106 MB/s   755 MB/s   100881382  47.60 /disk1/silesia.tar
done... (cIters=1 dIters=1 cTime=16.0 dTime=16.0 chunkSize=1706MB cSpeed=0MB)
```