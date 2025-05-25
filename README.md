此仓库用来发布个人使用的MIUI EU (Hyper OS) magisk 本地化模块，原作者为[MinaMichita](https://github.com/MinaMichita/MiuiEULocalizationToolsBox)，我在TA的基础上为我自用的小米13 (fuxi)进行了修改：
- 从国内版系统提取并更新了部分系统应用到新版
- 添加了适用于Android 14 (API 34)的钱包应用
- 部分功能修改为默认开启

<details>

Fonts=true
  
Mipay=true

ContentExtension=true

VirtualSim=true

PersonalAssistant=true

Calendar=true

MiuiIme=true

SogouInput=true

Mms=true

YellowPage=true

AiAsst=true

VoiceAssist=true

VoiceTrigger=true

Weather=true

ThemeManager=true

GboardTheme=true

VideocallBeautify=true

NotificationFilter=true

SoundRecorder=true

RemoveMod=true
</details>

在修改和制作此模块时，我使用的系统包版本为：
- EU: `xiaomi.eu_FUXI_OS2.0.108.0.VMCCNXM_15`
- 国内版: `fuxi-ota_full-OS2.0.104.0.VMCCNXM-user-15.0-0558a46bb0`

## 注意事项
- 此模块未在其他机型、其他系统版本上进行过测试，使用此模块代表你接受并自行承担可能的风险
- 建议提前做好数据备份工作

## 安装和使用

建议先阅读[原作者的使用说明](https://blog.minamigo.moe/archives/184)

1. [从Release页面下载模块](https://github.com/waitingsnow/MiuiEULocalizationToolsBox/releases/latest/download/MiuiLocalization.zip)然后使用magisk刷入

## 已知问题

## 模块结构与打包

本仓库新增 `module/` 目录用于存放 Magisk 模块文件，目录结构示例：

```
module/
├── module.prop
├── service.sh
├── system/
│   └── app/ 或 priv-app/  # 放置系统应用
└── tools/
    └── repairPermissions.sh
```

将需要预置的系统应用按 MIUI 目录结构放入 `module/system/app/` 或 `module/system/priv-app/` 中，每个应用一个文件夹，内含 APK 文件。安装过程中的权限设置可在 `tools/repairPermissions.sh` 中实现，也可以在 `service.sh` 或 `customize.sh` 编写其他逻辑。

完成内容准备后，在 `module` 目录下打包为 Zip 即可：

```bash
cd module
zip -r ../MiuiLocalization.zip *
```

生成的 `MiuiLocalization.zip` 便可在 Magisk 中刷入。
