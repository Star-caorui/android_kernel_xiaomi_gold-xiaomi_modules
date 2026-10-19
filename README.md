# Xiaomi's kernel modules for gold

Xiaomi's Millet, the framework that freezes apps in the background, as stock OS3.0.5.0.VNQMIXM of the Redmi Note 13 5G (`gold`) builds it. Stock ships it as seven modules and Xiaomi published no 6.6 source for them; these are Xiaomi's 5.10 sources ([MiCode/Xiaomi_Kernel_OpenSource](https://github.com/MiCode/Xiaomi_Kernel_OpenSource) `xaga-s-oss` as first published, `4299bdb995f8`, `drivers/mihw/millet/`) brought to 6.6 after stock's modules, one commit per module.

| Module | Against stock's |
| --- | --- |
| `millet_oem_cgroup.ko`, `millet_core.ko`, `millet_hs.ko`, `millet_sig.ko`, `millet_pkg.ko`, `millet_binder.ko` | byte for byte but the build ID |
| `binder_gki.ko` | three functions differ in how the compiler lays them out |

Stock's Millet modules were built against an unpublished 6.6.30 kernel (`6.6.30-android15-8-g41085fa58973-4k`); these are built against the Android common kernel `android15-6.6-2024-07_r1` with that release string. The directory is checked out at `vendor/xiaomi/kernel_modules`, and only the comparison with stock's modules builds it: Millet works with MIUI's user space, so the LineageOS build leaves it out. How it is built and compared is in [android_kernel_xiaomi_gold_manifest](https://github.com/Star-caorui/android_kernel_xiaomi_gold_manifest/tree/OS3.0.5.0.VNQMIXM).
