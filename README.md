# Mul-Zram
## Introduction
We know that Zram is a module used for memory compression in Linux systems, and the number of instances of Zram is statically configured. When the Zram module compresses different data sizes, the number of statically configured Zram instances may not achieve the best compression effect. To solve this problem, we propose Mul-Zram.
Mul-Zram is implemented as follows:
1) Establish a zram instance pool, which is composed of 8 zram instances.
2) The fitting formula is obtained through the linear regression method. The fitting formula can estimate the number of zram instances to be compressed according to the amount of data that the system needs to compress currently.
3) Select a corresponding number of zram instances in the zram instance pool for memory compression.
Depending on the objective, Mul-Zram can improve the compression speed of memory compression or CPU utilization compared with the default Zram module.
## Configuration 
The system configuration for developing Mul Zram is as follows:
* CPU Model：FT-2000/4
* Operating System Version：OpenEuler-20.03-LTS-SP3
* Linux Kernel Version：linux-5.18.14
* Compression algorithm used by Zram：Zstandard(zstd)
