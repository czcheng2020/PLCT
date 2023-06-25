# 改变Volume大小

## 操作步骤

1. 运行 `lsmcli volume-create --name VOL_TEST3 --size 2G --pool POOL_ID_00004`。
2. 运行 `lsmcli volume-resize --vol VOL_ID_00007 --size 4G`。

## 预期结果

Volume大小从2G变为4G。

## 实际结果

Volume大小从2G变为4G。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-create --name VOL_TEST3 --size 2G --pool POOL_ID_00004           
ID           | Name      | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
------------------------------------------------------------------------------------------------------------
VOL_ID_00007 | VOL_TEST3 | 501d3fc94a309605 | 2147483648 | No       | POOL_ID_00004 | sim-01    |           
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-resize --vol VOL_ID_00007 --size 4G 
Warning: You are about to do an operation that may cause data to be lost!
Press [Y|y] to continue, any other key to abort
ID           | Name      | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
------------------------------------------------------------------------------------------------------------
VOL_ID_00007 | VOL_TEST3 | 501d3fc94a309605 | 4294967296 | No       | POOL_ID_00004 | sim-01    |           
```