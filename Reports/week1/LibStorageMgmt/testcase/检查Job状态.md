# 检查Job状态

## 摘要

异步执行命令并检查Job状态。

## 操作步骤

1. 运行 `lsmcli volume-create --name async_created --size 4G --pool POOL_ID_00001 -b`，异步执行。
2. 运行 `lsmcli job-status --job JOB_ID_00001`。

## 预期结果

返回Job状态，Job已经完成则返回正常输出。

## 实际结果

返回正常输出。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli job-status --job JOB_ID_00001
ID           | Name          | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
----------------------------------------------------------------------------------------------------------------
VOL_ID_00002 | async_created | 5072102c9cdc7960 | 4294967296 | No       | POOL_ID_00001 | sim-01    | 
```