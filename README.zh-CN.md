[English](README.md) | [简体中文](README.zh-CN.md)

# PrismaticHelper

从用户提供的原始 Mod 压缩包重建 Shared 运行库的房间背景面板移植。提供前景／背景面板，以及房间选择、遮罩、染色、透明度、滚动和附着功能。

## 所需文件

- 已安装 [Everest 6580 稳定版](https://github.com/EverestAPI/Everest/releases/tag/stable-1.6580.0)的原始 Celeste 目录，保留其中的
  `Celeste.dll`、`FNA.dll`、`MMHOOK_Celeste.dll`、`MonoMod.Utils.dll` 和 `Mono.Cecil.dll`。
- 原始 **PrismaticHelper 1.12.0** 压缩包 `PrismaticHelper.zip`，可从
  [支持的版本压缩包](https://gamebanana.com/mmdl/1207039)获取。
- Workspace、Shared 和 Tools 仓库；宿主环境要求见
  [工作区 README][workspace-readme-zh-cn]。

保持压缩包完整，无需提取 DLL 或修改代码。支持的压缩包及内部程序集哈希记录在
[mod-rebuild.json](mod-rebuild.json)。

将下载的压缩包命名为 `PrismaticHelper.zip`，放在原始游戏安装目录的 `Mods` 下。

## 文件摆放

```text
Workspace/
  Shared/
  Tools/
  Mods/
    PrismaticHelper/                 # 本仓库

Celeste/                    # 原始游戏安装目录
  Celeste.dll
  FNA.dll
  Mods/
    PrismaticHelper.zip
```

其他所需 Mod 压缩包也放在原始游戏安装目录的 `Mods` 下。

## 构建

在工作区目录使用 [Tools README][tools-readme-zh-cn] 中的宿主准备参数。
以下以 Godot 为例：

```powershell
pwsh ./Tools/Prepare.ps1 `
  -CelesteDirectory '/path/to/Celeste' `
  -AudioBankDirectory '/path/to/Desktop' `
  -Targets Godot `
  -IncludeHelpers
```

准备流程校验支持的输入版本、构建依赖，并将运行包放到
`Content/Celeste/Mods/PrismaticHelper.zip`。生成源码、工具和构建中间文件均保存在工作区已忽略的
`artifacts/` 目录内。

## 许可

见 [LICENSE](LICENSE) 和 [NOTICE.md](NOTICE.md)。本仓库不包含原游戏文件、Mod 原始压缩包
或本地生成的运行包。

[workspace-readme-zh-cn]: https://github.com/CelesteResearch/Workspace/blob/main/README.zh-CN.md
[tools-readme-zh-cn]: https://github.com/CelesteResearch/Tools/blob/main/README.zh-CN.md
