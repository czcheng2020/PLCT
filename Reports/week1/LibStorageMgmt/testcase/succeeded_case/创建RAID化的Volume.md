# 创建RAID化的Volume

## 摘要

基于RAID硬件创建RAID化的Volume。

## 操作步骤

运行 `lsmcli volume-raid-create --name VOLUME_RAID --disk DISK_ID_00020 --raid-type RAID0`。

## 预期结果

成功创建Volume。

## 实际结果

成功创建Volume。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-raid-create --name VOLUME_RAID --disk DISK_ID_00020 --raid-type RAID0
ID           | Name        | SCSI VPD 0x83    | Size          | Disabled | Pool ID       | System ID | Disk Paths
-----------------------------------------------------------------------------------------------------------------
VOL_ID_00006 | VOLUME_RAID | 501d941778b6422a | 2199023254528 | No       | POOL_ID_00005 | sim-01    |    
```