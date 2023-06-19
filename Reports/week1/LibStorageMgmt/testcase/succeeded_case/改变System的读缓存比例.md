# 改变System的读缓存比例

## 操作步骤

1. 运行 `lsmcli list --type systems -s`。
2. 运行 `lsmcli system-read-cache-pct-update --sys sim-01 --read-pct 20`。

## 预期结果

读缓存比例改变。

## 实际结果

读缓存比例改变。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type systems -s
-----------------------------------------------------
ID                    | sim-01                       
Name                  | LSM simulated storage plug-in
Status                | OK                           
Info                  |                              
FW Ver                | LSM_SIMULATOR_DATA_4.1       
Mode                  | HW RAID                      
Read Cache Percentage | 10                           
-----------------------------------------------------
[openeuler@openeuler-riscv64 ~]$ lsmcli system-read-cache-pct-update --sys sim-01 --read-pct 20
ID     | Name                          | Status | Info | FW Ver                 | Mode    | Read Cache Percentage
-----------------------------------------------------------------------------------------------------------------
sim-01 | LSM simulated storage plug-in | OK     |      | LSM_SIMULATOR_DATA_4.1 | HW RAID | 20 
```