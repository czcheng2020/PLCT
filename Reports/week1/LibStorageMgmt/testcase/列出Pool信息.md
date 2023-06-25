# 列出Pool信息

## 操作步骤

运行 `lsmcli -u 'sim://' list --type POOLS -H`。

## 预期结果

输出 `Pool` 信息。

## 实际结果

输出 `Pool` 信息。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli -u 'sim://' list --type POOLS -H
ID            | Name                       | Element Type                         | Total Space | Free
 Space | Status | Info | System ID
------------------------------------------------------------------------------------------------------
----------------------------------
POOL_ID_00001 | Pool 1                     | POOL,VOLUME,FS,SYSTEM_RESERVED,DELTA | 2.00 TiB    | 1.50
 TiB   | OK     |      | sim-01   
POOL_ID_00002 | Pool 2(sub pool of Pool 1) | VOLUME,FS,DELTA                      | 512.00 GiB  | 512.
00 GiB | OK     |      | sim-01   
POOL_ID_00003 | Pool 3                     | VOLUME,FS,DELTA                      | 512.00 GiB  | 512.
00 GiB | OK     |      | sim-01   
POOL_ID_00004 | lsm_test_aggr              | VOLUME,FS,DELTA                      | 2.00 EiB    | 2.00
 EiB   | OK     |      | sim-01   
```