# 移除Volume的依赖

## 操作步骤

1. 运行 `lsmcli volume-dependants --vol VOL_ID_00001`。
2. 运行 `lsmcli volume-dependants-rm --vol VOL_ID_00001`。
3. 运行 `lsmcli volume-dependants --vol VOL_ID_00001`。

## 预期结果

`lsmcli volume-dependants --vol VOL_ID_00001` 的输出从True变为False。

## 实际结果

`lsmcli volume-dependants --vol VOL_ID_00001` 的输出从True变为False。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-dependants --vol VOL_ID_00001
True
[openeuler@openeuler-riscv64 ~]$ 
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-dependants-rm --vol VOL_ID_00001
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-dependants --vol VOL_ID_00001
False
```