# 查看Volume的RAID信息

## 操作步骤

运行 `lsmcli volume-raid-info --vol VOL_ID_00001`。

## 预期结果

成功显示相关信息。

## 实际结果

成功显示相关信息。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-raid-info --vol VOL_ID_00001
Volume ID    | RAID Type | Strip Size | Disk Count | Minimum I/O Size | Optimal I/O Size
----------------------------------------------------------------------------------------
VOL_ID_00001 | RAID1     | 512        | 2          | 512              | 512
```