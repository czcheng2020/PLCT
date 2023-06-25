# 使能Volume

## 操作步骤

1. 运行 `lsmcli list --type volumes`，查看Volume状态。
2. 运行 `lsmcli volume-enable --vol VOL_ID_00001`。
3. 运行 `lsmcli list --type volumes`。

## 预期结果

`VOL_ID_00001` 从 `disabled` 变为 `enabled`。

## 实际结果

`VOL_ID_00001` 从 `disabled` 变为 `enabled`。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type volumes
ID           | Name       | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1       | 5080562dfafbaec6 | 2147483648 | Yes      | POOL_ID_00001 | sim-01    |           
VOL_ID_00002 | VOL_TEST   | 50768e0613eb3bec | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00003 | VOL_CLONE  | 5018efebff716b1b | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00004 | VOL_CREATE | 50f1c2c1ac0b0afa | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-enable --vol VOL_ID_00001
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type volumes
ID           | Name       | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1       | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00002 | VOL_TEST   | 50768e0613eb3bec | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00003 | VOL_CLONE  | 5018efebff716b1b | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00004 | VOL_CREATE | 50f1c2c1ac0b0afa | 2147483648 | No       | POOL_ID_00001 | sim-01    |          
```