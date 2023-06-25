# 复制Volume

## 操作步骤

1. 运行 `lsmcli list --type volumes`，查看Volume信息。
2. 运行 `lsmcli volume-replicate --vol VOL_ID_00001 --name VOL_CLONE --rep-type CLONE`。

## 预期结果

复制成功，返回复制结果。

## 实际结果

复制成功，返回复制结果。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-replicate --vol\
>  VOL_ID_00001 --name VOL_CLONE --rep-type CLONE
ID           | Name      | SCSI VPD 0x83    | Size       | Disabled | Pool ID       | System ID | Disk Paths
------------------------------------------------------------------------------------------------------------
VOL_ID_00003 | VOL_CLONE | 5018efebff716b1b | 2147483648 | No       | POOL_ID_00001 | sim-01    |   
```