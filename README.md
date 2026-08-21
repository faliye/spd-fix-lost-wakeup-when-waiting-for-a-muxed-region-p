# resource: fix lost wakeup when waiting for a muxed region

**Language / 语言 / 言語:** [简体中文](#简体中文) | [English](#english) | [日本語](#日本語)

---

## 简体中文

修复 Linux 内核 `kernel/resource.c` 中 `request_muxed_region()` 的一个丢失唤醒竞态：
等待方在解锁 `resource_lock` 之后才设置任务状态，`__release_region()` 的唤醒可能
恰好落在这个窗口里被丢弃，导致任务永久卡死。修复方式是把设置状态提前到解锁之前。

补丁见 [upstream-patches/](upstream-patches/)。

```sh
git am upstream-patches/0001-*.patch
```

---

## English

Fixes a lost-wakeup race in `request_muxed_region()` (`kernel/resource.c`):
the waiter sets its task state only after dropping `resource_lock`, so a
wakeup from `__release_region()` can land in that gap and get discarded,
leaving the task stuck forever. The fix moves the state change before the
unlock.

Patch is in [upstream-patches/](upstream-patches/).

```sh
git am upstream-patches/0001-*.patch
```

---

## 日本語

`kernel/resource.c` の `request_muxed_region()` にあるウェイクアップ消失の
競合を修正します。待機側が `resource_lock` を解放した後にタスク状態を
設定するため、`__release_region()` からのウェイクアップがその隙間で
破棄され、タスクが永久に止まってしまう問題です。状態設定をアンロックより
前に移すことで修正します。

パッチは [upstream-patches/](upstream-patches/) にあります。

```sh
git am upstream-patches/0001-*.patch
```
