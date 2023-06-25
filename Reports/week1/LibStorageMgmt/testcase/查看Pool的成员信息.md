# 查看Pool的成员信息

## 操作步骤

运行 `lsmcli pool-member-info --pool POOL_ID_00001`。

## 预期结果

输出Pool的成员信息。

## 实际结果

输出Pool的成员信息。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli pool-member-info --pool POOL_ID_00001
Pool ID       | RAID Type | Member Type | Member IDs   
-------------------------------------------------------
POOL_ID_00001 | RAID1     | Disk        | DISK_ID_00001
              |           |             | DISK_ID_00002
```