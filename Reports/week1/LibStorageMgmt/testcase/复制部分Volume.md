# 复制部分Volume

## 摘要

将指定Volume的一部分复制到另一Volume。

## 操作步骤

1. 运行 `lsmcli list --type volumes`，查看Volume信息。
2. 运行 `lsmcli volume-replicate-range --src-vol VOL_ID_00001 --dst-vol VOL_ID_00002 --rep-type CLONE --src-start 0 --dst-start 0 --count 512`。

## 预期结果

复制成功，返回复制结果。

## 实际结果

复制成功，返回复制结果。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type volumes
ID           | Name       | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1       | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00002 | VOL_TEST   | 50768e0613eb3bec | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00003 | VOL_CLONE  | 5018efebff716b1b | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00004 | VOL_CREATE | 50f1c2c1ac0b0afa | 2147483648 | No       | POOL_ID_00001 | sim-01    | 
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-replicate-range --src-vol VOL_ID_00001 --dst-vol VOL_ID_00002 --rep-type CLONE --src-start 0 --dst-start 0 --count 512
Warning: You are about to do an operation that may cause data to be lost!
Press [Y|y] to continue, any other key to abort
[openeuler@openeuler-riscv64 ~]$  
```