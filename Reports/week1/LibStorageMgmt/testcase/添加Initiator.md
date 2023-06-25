# 添加Initiator

## 摘要

向现有的Access Group中加入Initiator。

## 操作步骤

1. 运行 `lsmcli access-group-add --ag AG_ID_00001 --init iqn.1994-05.com.domain:01.5d8644`。
2. 运行 `lsmcli list --type access_groups`。

## 预期结果

Access Group中加入指定的initiator。

## 实际结果

Access Group中加入指定的initiator。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-add --ag AG_ID_00001 --init iqn.1994-05.com.domain:01.5d8644
ID          | Name       | Initiator IDs                    | System ID
-----------------------------------------------------------------------
AG_ID_00001 | example_ag | iqn.1994-05.com.domain:01.89bd01 | sim-01    
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type access_groups
ID          | Name       | Initiator IDs                    | System ID
-----------------------------------------------------------------------
AG_ID_00001 | example_ag | iqn.1994-05.com.domain:01.5d8644 | sim-01   
            |            | iqn.1994-05.com.domain:01.89bd01 |     
```