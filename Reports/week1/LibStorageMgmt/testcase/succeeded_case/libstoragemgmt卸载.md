# libstoragemgmt卸载

## 操作步骤

运行 `sudo dnf remove -y libstoragemgmt`。

## 预期结果

`libstoragemgmt` 卸载成功。

## 实际结果

`libstoragemgmt` 卸载成功。

```log
Dependencies resolved.
================================================================================
 Package                        Arch      Version             Repository   Size
================================================================================
Removing:
 libstoragemgmt                 riscv64   1.9.6-1.oe2303      @mainline   584 k
Removing unused dependencies:
 libconfig                      riscv64   1.7.3-2.oe2303      @mainline   208 k
 python3-libstoragemgmt         riscv64   1.9.6-1.oe2303      @mainline   775 k
 python3-libstoragemgmt-clibs   riscv64   1.9.6-1.oe2303      @mainline   161 k

Transaction Summary
================================================================================
Remove  4 Packages

Freed space: 1.7 M
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                        1/1 
  Running scriptlet: python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    1/1 
  Erasing          : python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    1/4 
  Running scriptlet: libstoragemgmt-1.9.6-1.oe2303.riscv64                  2/4 
Removed /etc/systemd/system/multi-user.target.wants/libstoragemgmt.service.

  Erasing          : libstoragemgmt-1.9.6-1.oe2303.riscv64                  2/4 
  Running scriptlet: libstoragemgmt-1.9.6-1.oe2303.riscv64                  2/4 
  Erasing          : python3-libstoragemgmt-1.9.6-1.oe2303.riscv64          3/4 
  Erasing          : libconfig-1.7.3-2.oe2303.riscv64                       4/4 
  Running scriptlet: libconfig-1.7.3-2.oe2303.riscv64                       4/4 
  Verifying        : libconfig-1.7.3-2.oe2303.riscv64                       1/4 
  Verifying        : libstoragemgmt-1.9.6-1.oe2303.riscv64                  2/4 
  Verifying        : python3-libstoragemgmt-1.9.6-1.oe2303.riscv64          3/4 
  Verifying        : python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64    4/4 

Removed:
  libconfig-1.7.3-2.oe2303.riscv64                                              
  libstoragemgmt-1.9.6-1.oe2303.riscv64                                         
  python3-libstoragemgmt-1.9.6-1.oe2303.riscv64                                 
  python3-libstoragemgmt-clibs-1.9.6-1.oe2303.riscv64                           

Complete!
```