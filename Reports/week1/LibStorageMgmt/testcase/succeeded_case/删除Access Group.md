# 删除Access Group

## 操作步骤

1. 运行 `lsmcli access-group-create --name test_ag --init iqn.1994-05.com.domain:01.90bd01 --sys sim-01`。
2. 运行 `lsmcli access-group-delete --ag AG_ID_00002`。
3. 运行 `lsmcli list --type access_groups`。

## 预期结果

指定Access Group被删除。

## 实际结果

指定Access Group被删除。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-create --name test_ag --init iqn.1994-05.com.domain:01.90bd01 --sys sim-01
ID          | Name    | Initiator IDs                    | System ID
--------------------------------------------------------------------
AG_ID_00002 | test_ag | iqn.1994-05.com.domain:01.90bd01 | sim-01  
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-delete --ag AG_ID_00002
[openeuler@openeuler-riscv64 ~]$ lsmcli list --type access_groups
ID          | Name       | Initiator IDs                    | System ID
-----------------------------------------------------------------------
AG_ID_00001 | example_ag | iqn.1994-05.com.domain:01.89bd01 | sim-01 
```