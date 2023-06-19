# 允许Access Group访问指定Volume

## 操作步骤

1. 运行 `lsmcli volume-mask --ag AG_ID_00001 --vol VOL_ID_00001`。
2. 运行 `lsmcli access-group-volumes --ag AG_ID_00001`。

## 预期结果

`AG_ID_00001` 成功绑定 `VOL_ID_00001`。

## 实际结果

`AG_ID_00001` 成功绑定 `VOL_ID_00001`。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-volumes --ag AG_ID_00001
ID           | Name | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1 | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    |  
```