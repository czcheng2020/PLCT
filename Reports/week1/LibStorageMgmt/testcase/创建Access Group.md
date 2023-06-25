# 创建Access Group

## 操作步骤

运行 `lsmcli access-group-create --name example_ag --init iqn.1994-05.com.domain:01.89bd01 --sys sim-01`。

## 预期结果

创建一个 `name` 为 `example_ag`，`Initiator ID` 为 `iqn.1994-05.com.domain:01.89bd01` 的 `Access Group`。

## 实际结果

创建一个 `name` 为 `example_ag`，`Initiator ID` 为 `iqn.1994-05.com.domain:01.89bd01` 的 `Access Group`。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli access-group-create --name example_ag --init iqn.1994-05.com.domain:01.89bd01 --sys sim-01
ID          | Name       | Initiator IDs                    | System ID
-----------------------------------------------------------------------
AG_ID_00001 | example_ag | iqn.1994-05.com.domain:01.89bd01 | sim-01 |  
```