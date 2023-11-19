# Umi-OCR 插件库

这里是存放 [Umi-OCR](https://github.com/hiroi-sora/Umi-OCR) 的插件的仓库。

Umi-OCR (v2以上) 支持以插件的形式导入OCR引擎等组件，只需将插件文件放置于软件指定目录即可。

注意，插件可能会限制平台（win7、win10……），下载插件前请检查是否与你的平台是否相符。

- [如何开发插件？](#插件开发)

## 如何安装插件

1. 在 [Releases](https://github.com/hiroi-sora/Umi-OCR_plugins/releases) 中下载插件。

2. 将下载的文件解压，放置于：`UmiOCR-data/plugins`

## OCR 文字识别 插件

### win7_x64_PaddleOCR-json

> 性能和准确率优秀的开源离线OCR组件。支持mkldnn数学库加速，能充分榨干CPU的潜力。适合高配置电脑使用。

| 源仓库     | [PaddleOCR-json](https://github.com/hiroi-sora/PaddleOCR-json)            |
| ---------- | ------------------------------------------------------------------------- |
| 下载       | [Releases](https://github.com/hiroi-sora/Umi-OCR_plugins/releases)        |
| 计算方式   | 本地，CPU                                                                 |
| 平台兼容   | win7以上，64位                                                            |
| 硬件兼容   | CPU须带AVX指令集（不支持凌动Atom，安腾Itanium，赛扬Celeron，奔腾Pentium） |
| 附带语言库 | `简, 繁, 英, 日, 韩, 俄`                                                  |

---

### win7_x64_RapidOCR-json

> 轻量、高兼容性的开源离线OCR组件。内存与CPU占用低。速度相对慢一点。适合低配置老电脑使用。

| 源仓库     | [RapidOCR-json](https://github.com/hiroi-sora/RapidOCR-json)       |
| ---------- | ------------------------------------------------------------------ |
| 下载       | [Releases](https://github.com/hiroi-sora/Umi-OCR_plugins/releases) |
| 计算方式   | 本地，CPU                                                          |
| 平台兼容   | win7以上，64位                                                     |
| 硬件兼容   | 无特殊要求                                                         |
| 附带语言库 | `简, 繁, 英, 日, 韩, 俄`                                           |

---

## 插件开发

请见 [插件开发文档及demo](demo_AbaOCR)。

# Umi-OCR 项目结构

### 各仓库：

- [主仓库](https://github.com/hiroi-sora/Umi-OCR)
- [插件库](https://github.com/hiroi-sora/Umi-OCR_plugins) 👈
- [Win 运行库](https://github.com/hiroi-sora/Umi-OCR_runtime_windows)

### 工程结构：

`**` 后缀表示本仓库(`插件库`)包含的内容。

```
Umi-OCR
├─ Umi-OCR.exe
└─ UmiOCR-data
   ├─ main.py
   ├─ version.py
   ├─ site-packages
   │  └─ python包
   ├─ runtime
   │  └─ python解释器
   ├─ qt_res
   │  └─ 项目qt资源，包括图标和qml源码
   ├─ py_src
   │  └─ 项目python源码
   ├─ plugins **
   │  └─ 插件
   └─ i18n
      └─ 翻译文件
```