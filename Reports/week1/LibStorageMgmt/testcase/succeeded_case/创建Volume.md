# 创建Volume

## 操作步骤

运行 `lsmcli volume-create --name VOL_CREATE --size 2G --pool POOL_ID_00001`。

## 预期结果

创建一个 `name` 为 `VOL_CREATE` 的 `Volume`。

## 实际结果

创建一个 `name` 为 `VOL_CREATE` 的 `Volume`。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-create --name VOL_CREATE --size 2G --pool POOL_ID_00001
ID           | Name       | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------------
VOL_ID_00004 | VOL_CREATE | 50f1c2c1ac0b0afa | 2147483648 | No       | POOL_ID_00001 | sim-01    |            
```