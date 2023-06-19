# 查看Volume的依赖

## 摘要

查看Volume是否有依赖于它的子Volume。

## 操作步骤

1. 运行 `lsmcli volume-dependants --vol VOL_ID_00001`。
2. 运行 `lsmcli volume-dependants --vol VOL_ID_00003`（`VOL_ID_00003` 是 `VOL_ID_00001` 的 `CLONE`）。

## 预期结果

对于 `VOL_ID_00001` 结果为True。对于 `VOL_ID_00003` 结果为False。

## 实际结果

对于 `VOL_ID_00001` 结果为True。对于 `VOL_ID_00003` 结果为False。

```log
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-dependants --vol VOL_ID_00001
True
[openeuler@openeuler-riscv64 ~]$ lsmcli volume-dependants --vol VOL_ID_00003
False
```