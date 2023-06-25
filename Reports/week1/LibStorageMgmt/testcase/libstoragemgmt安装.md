# libstoragemgmt安装

## 操作步骤

运行 `sudo dnf install -y libstoragemgmt`。

## 预期结果

`libstoragemgmt` 及其依赖安装成功。

## 实际结果

`libstoragemgmt` 及其依赖安装成功。

```log
Dependencies resolved.
================================================================================
 Package                         Arch       Version           Repository   Size
================================================================================
Installing:
 libstoragemgmt                  riscv64    1.9.6-1.oe2303    mainline    199 k
Installing dependencies:
 libconfig                       riscv64    1.7.3-2.oe2303    mainline     63 k
 python3-libstoragemgmt          riscv64    1.9.6-1.oe2303    mainline    160 k
 python3-libstoragemgmt-clibs    riscv64    1.9.6-1.oe2303    mainline     25 k

Transaction Summary
================================================================================
Install  4 Packages

Total download size: 447 k
Installed size: 1.7 M
Downloading Packages:
(1/4): libconfig-1.7.3-2.oe2303.riscv64.rpm      27 kB/s |  63 kB     00:02    
(2/4): libstoragemgmt-1.9.6-1.oe2303.riscv64.rp  79 kB/s | 199 kB     00:02    
(3/4): python3-libstoragemgmt-1.9.6-1.oe2303.ri  60 kB/s | 160 kB     00:02    
(4/4): python3-libstoragemgmt-clibs-1.9.6-1.oe2 105 kB/s |  25 kB     00:00    
--------------------------------------------------------------------------------
Total                                           154 kB/s | 447 kB     00:02     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                        1/1 
  Installing       : libconfig-1.7.3-2.oe2303.riscv64                       1/4 
  Running scriptlet: libconfig-1.7.3-2.oe2303.riscv64                       1/4 
  Installing       : python3-libstoragemgmt-1.9.6-1.oe2303.riscv64          2/4 
  Running scriptlet: libstoragemgmt-1.9.6-1.oe2303.riscv64                  3/4 
  Installing       : libstoragemgmt-1.9.6-1.oe2303.riscv64                  3/4 
  Running scriptlet: libstoragemgmt-1.9.6-1.oe2303.riscv64                  3/4 
Created symlink /etc/systemd/system/multi-user.target.wants/libstoragemgmt.service → /usr/lib/systemd/
system/libstoragemgmt.service.

  Installing       : python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    4/4 
  Running scriptlet: python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    4/4 
/usr/lib/tmpfiles.d/dbus.conf:13: Line references path below legacy directory /var/run/, updating /var
/run/dbus/containers → /run/dbus/containers; please update the tmpfiles.d/ drop-in file accordingly.
/usr/lib/tmpfiles.d/multipath.conf:1: Line references path below legacy directory /var/run/, updating 
/var/run/multipath → /run/multipath; please update the tmpfiles.d/ drop-in file accordingly.

  Verifying        : libconfig-1.7.3-2.oe2303.riscv64                       1/4 
  Verifying        : libstoragemgmt-1.9.6-1.oe2303.riscv64                  2/4 
  Verifying        : python3-libstoragemgmt-1.9.6-1.oe2303.riscv64          3/4 
  Verifying        : python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    4/4 

Installed:
  libconfig-1.7.3-2.oe2303.riscv64                                              
  libstoragemgmt-1.9.6-1.oe2303.riscv64                                         
  python3-libstoragemgmt-1.9.6-1.oe2303.riscv64                                 
  python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64                           

Complete!
```