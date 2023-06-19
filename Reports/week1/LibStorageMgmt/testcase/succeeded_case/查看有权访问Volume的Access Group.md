# 查看有权访问Volume的Access Group

## 操作步骤

运行 `lsmcli volume-access-group --vol VOL_ID_00001`。

## 预期结果

列出有权访问 `VOL_ID_00001` 的Access Group。

## 实际结果

列出有权访问 `VOL_ID_00001` 的Access Group。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-access-group --vol VOL_ID_00001
ID          | Name       | Initiator IDs                    | System ID
-----------------------------------------------------------------------
AG_ID_00001 | example_ag | iqn.1994-05.com.domain:01.89bd01 | sim-01  
```