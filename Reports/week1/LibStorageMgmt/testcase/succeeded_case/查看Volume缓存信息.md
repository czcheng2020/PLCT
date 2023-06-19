# 查看Volume缓存信息

## 摘要

查看指定Volume与缓存相关的策略和配置。

## 操作步骤

运行 `lsmcli volume-cache-info --vol VOL_ID_00001`。

## 预期结果

成功输出信息。

## 实际结果

成功输出信息。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-cache-info --vol VOL_ID_00001
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Enabled           | Enabled    | Disabled 
```