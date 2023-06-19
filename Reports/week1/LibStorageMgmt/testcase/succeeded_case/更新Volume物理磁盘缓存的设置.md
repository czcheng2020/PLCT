# 更新Volume物理磁盘缓存的设置

## 操作步骤

1. 运行 `lsmcli volume-cache-info --vol VOL_ID_00001`。
2. 运行 `lsmcli volume-phy-disk-cache-update --vol VOL_ID_00001 --policy ENABLE`。

## 预期结果

成功更新。

## 实际结果

成功更新。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-cache-info --vol VOL_ID_00001
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Enabled           | Enabled    | Disabled           
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-phy-disk-cache-update --vol VOL_ID_00001 --policy ENABLE
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Enabled           | Enabled    | Enabled 
```