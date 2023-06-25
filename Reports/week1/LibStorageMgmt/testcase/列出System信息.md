# 列出System信息

## 操作步骤

运行 `lsmcli -u 'sim://' list --type SYSTEMS`。

## 预期结果

输出 `System` 信息。

## 实际结果

输出 `System` 信息。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli -u 'sim://' list --type SYSTEMS
ID     | Name                          | Status | Info | FW Ver                 | Mode    | Read Cache
 Percentage
------------------------------------------------------------------------------------------------------
-----------
sim-01 | LSM simulated storage plug-in | OK     |      | LSM_SIMULATOR_DATA_4.1 | HW RAID | 10  
```