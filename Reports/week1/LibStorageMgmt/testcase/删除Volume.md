# 删除Volume

## 操作步骤

1. 运行 `lsmcli list --type volumes`。
2. 运行 `lsmcli volume-delete --vol VOL_ID_00002`。
3. 运行 `lsmcli list --type volumes`。

## 预期结果

成功删除指定Volume。

## 实际结果

成功删除指定Volume。

删除前

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type volumes
ID           | Name          | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
----------------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1          | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    |           
VOL_ID_00002 | async_created | 5072102c9cdc7960 | 4294967296 | No       | POOL_ID_00001 | sim-01    | 
```
删除后

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type volumes
ID           | Name | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1 | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    | 
```