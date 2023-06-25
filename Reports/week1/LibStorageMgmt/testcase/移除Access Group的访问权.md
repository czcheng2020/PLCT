# 移除Access Group的访问权

## 摘要

移除Access Group对指定Volume的访问权。

## 操作步骤

1. 运行 `lsmcli volume-access-group --vol VOL_ID_00001`。
2. 运行 `lsmcli volume-unmask --ag AG_ID_00001 --vol VOL_ID_00001`，移除访问权。
3. 运行 `lsmcli volume-access-group --vol VOL_ID_00001`。

## 预期结果

`AG_ID_00001` 无法访问 `VOL_ID_00001`。

## 实际结果

`AG_ID_00001` 无法访问 `VOL_ID_00001`。

移除前

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-volumes --ag AG_ID_00001
ID           | Name | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
-------------------------------------------------------------------------------------------------------
VOL_ID_00001 | myv1 | 5080562dfafbaec6 | 2147483648 | No       | POOL_ID_00001 | sim-01    | 
```

移除后

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-volumes --ag AG_ID_00001
[openeuler@openeuler-riscv64 ~]$ 
```