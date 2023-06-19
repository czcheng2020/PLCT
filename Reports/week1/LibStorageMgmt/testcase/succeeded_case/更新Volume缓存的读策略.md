# 更新Volume缓存的读策略

## 操作步骤

1. 运行 `lsmcli volume-cache-info --vol VOL_ID_00001`。
2. 运行 `lsmcli volume-read-cache-policy-update --vol VOL_ID_00001 --policy DISABLE`。
3. 运行 `lsmcli volume-read-cache-policy-update --vol VOL_ID_00001 --policy ENABLE`。

## 预期结果

成功更新缓存的读策略。

## 实际结果

成功更新缓存的读策略。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-cache-info --vol VOL_ID_00001
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Enabled           | Enabled    | Disabled
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-read-cache-policy-update --vol VOL_ID_00001 --policy DISABLE
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Disabled          | Disabled   | Disabled  
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-read-cache-policy-update --vol VOL_ID_00001 --policy ENABLE
Volume ID    | Write Cache Policy | Write Cache | Read Cache Policy | Read Cache | Physical Disk Cache
------------------------------------------------------------------------------------------------------
VOL_ID_00001 | Auto               | Write Back  | Enabled           | Enabled    | Disabled  
```