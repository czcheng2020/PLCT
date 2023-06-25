# 查看Access Group有权访问的Volume

## 操作步骤

运行 `lsmcli access-group-volumes --ag AG_ID_00001`。

## 预期结果

列出 `AG_ID_00001` 有权访问的Volume。

## 实际结果

列出 `AG_ID_00001` 有权访问的Volume。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-volumes --ag AG_ID_00001
ID           | Name | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1 | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    | 
```