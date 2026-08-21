# upstream-patches

**Language / 语言 / 言語:** [简体中文](#简体中文) | [English](#english) | [日本語](#日本語)

---

## 简体中文

准备提交给 Linux 内核上游的补丁，`git format-patch` 格式，可直接 `git am` 应用。

| 文件 | 说明 |
| --- | --- |
| [`0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch`](0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch) | 修复 `request_muxed_region()` 丢失唤醒问题，详见根目录 [README.md](../README.md) |

```sh
git am upstream-patches/0001-*.patch
```

---

## English

Patches prepared for the upstream Linux kernel, in `git format-patch`
form, ready to be applied with `git am`.

| File | Description |
| --- | --- |
| [`0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch`](0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch) | Fixes a lost wakeup in `request_muxed_region()`, see top-level [README.md](../README.md) |

```sh
git am upstream-patches/0001-*.patch
```

---

## 日本語

Linux カーネル上流向けに準備したパッチです。`git format-patch` 形式で、
`git am` でそのまま適用できます。

| ファイル | 説明 |
| --- | --- |
| [`0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch`](0001-resource-fix-lost-wakeup-when-waiting-for-a-muxed-reg.patch) | `request_muxed_region()` のウェイクアップ消失を修正します。詳細はルートの [README.md](../README.md) を参照してください |

```sh
git am upstream-patches/0001-*.patch
```
