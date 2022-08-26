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