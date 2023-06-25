# HSAK

## 软件说明

随着NVMe SSD、SCM等存储介质性能不断提升，介质层在IO栈中的时延开销不断缩减，软件栈的开销成为瓶颈，急需重构内核IO数据面，减少软件栈的开销，HSAK针对新型存储介质提供高带宽低时延的IO软件栈，相对传统IO软件栈，软件栈开销降低50%以上。 HSAK用户态IO引擎基于开源的SPDK基础上进行开发：

1. 对外提供统一的接口，屏蔽开源接口的差异。
2. 在开源基础上新增IO数据面增强特性，如DIF功能，磁盘格式化，IO批量下发，trim特性，动态增删盘等特性。
3. 提供磁盘设备管理，磁盘IO监测，维测工具等特性。

## 环境配置

- 硬件信息：QEMU 7.2.0，8*vCPU + 8GB RAM
- 操作系统版本：openEuler-23.03-V1-riscv64, Linux 6.1.19-2.oe2303.riscv64

## 安装方法

### 1. 下载 hsak 源码

```
git clone https://gitee.com/openeuler/hsak.git
```

### 2. 编译和运行依赖

hsak 的编译和运行依赖于 spdk、dpdk、libboundscheck 等组件。

### 安装 spdk

```
# 下载源码和子模块
git clone https://github.com/spdk/spdk
cd spdk
git submodule update --init

# 安装依赖
./scripts/pkgdep.sh

# Build
./configure
make
```

### 安装 dpdk

```
dnf install -y dpdk
```

### 安装 libboundscheck

```
dnf install -y libboundscheck
```

### 3. 编译

```
cd hsak

mkdir build

cd build

cmake ..

make
```

## 注意事项

HSAK 的安装进行到 make 时会报错。

```
[root@openeuler-riscv64 build]# make
[  1%] Building C object CMakeFiles/storage_bdev_rw.dir/src/bdev_rw.c.o
cc: error: unrecognized command-line option ‘-m64’
make[2]: *** [CMakeFiles/storage_bdev_rw.dir/build.make:76: CMakeFiles/storage_bdev_rw.dir/src/bdev_rw.c.o] Error 1
make[1]: *** [CMakeFiles/Makefile2:330: CMakeFiles/storage_bdev_rw.dir/all] Error 2
make: *** [Makefile:91: all] Error 2
[root@openeuler-riscv64 build]# 
```
原因在于hsak/CMakeLists.txt中的118行~124行没有针对 riscv64 架构的编译选项。

```
if(${ARCHITECTURE} STREQUAL "aarch64")
 target_compile_options(storage_bdev_rw PRIVATE -march=armv8-a) 
 target_compile_options(storage_ublock PRIVATE -march=armv8-a)
else()
 target_compile_options(storage_bdev_rw PRIVATE -march=core-avx-i -m64)
 target_compile_options(storage_ublock PRIVATE -march=core-avx-i -m64)
endif()
```

手动向其中添加适合 riscv64 架构的编译选项。

```
if( ${ARCHITECTURE} STREQUAL "aarch64" )
 target_compile_options(storage_bdev_rw PRIVATE -march=armv8-a)
 target_compile_options(storage_ublock PRIVATE -march=armv8-a)
elseif(${ARCHITECTURE} STREQUAL "riscv64")
 target_compile_options(storage_bdev_rw PRIVATE -march=rv64gc -mabi=lp64d)
 target_compile_options(storage_ublock PRIVATE -march=rv64gc -mabi=lp64d)
else()
 target_compile_options(storage_bdev_rw PRIVATE -march=core-avx-i -m64)
 target_compile_options(storage_ublock PRIVATE -march=core-avx-i -m64)
endif()
```

再次运行 make 的过程中会遇到如下报错。

```
[root@openeuler-riscv64 build]# make
[  1%] Building C object CMakeFiles/storage_bdev_rw.dir/src/bdev_rw.c.o
In file included from /home/openeuler/hsak/include/bdev_rw_internal.h:25,
                 from /home/openeuler/hsak/src/bdev_rw.c:16:
/home/openeuler/hsak/include/bdev_rw_common.h:18:10: fatal error: spdk_internal/bdev_stat.h: No such file or directory
   18 | #include "spdk_internal/bdev_stat.h"
      |          ^~~~~~~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
make[2]: *** [CMakeFiles/storage_bdev_rw.dir/build.make:76: CMakeFiles/storage_bdev_rw.dir/src/bdev_rw.c.o] Error 1
make[1]: *** [CMakeFiles/Makefile2:330: CMakeFiles/storage_bdev_rw.dir/all] Error 2
make: *** [Makefile:91: all] Error 2
```

无法在本地或 spdk 的仓库中找到 `bdev_stat.h`， 因此安装失败。 

## 参考资料

[HSAK开发者指南](https://docs.openeuler.org/zh/docs/22.09/docs/HSAK/introduce_hsak.html)

[https://github.com/openeuler-mirror/hsak/tree/master](https://github.com/openeuler-mirror/hsak/tree/master)