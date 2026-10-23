[English](README.md) | [简体中文](README.zh-CN.md)

# PrismaticHelper

Reconstructs the room-based styleground panel port for the Shared runtime from your original Mod archive. The port provides foreground/background panels with room selection, masks, tint, opacity, scrolling and attachment support.

## Required files

- An original Celeste installation with **Everest 6580 stable**:
  [release](https://github.com/EverestAPI/Everest/releases/tag/stable-1.6580.0).
  Keep `Celeste.dll`, `FNA.dll`, `MMHOOK_Celeste.dll`,
  `MonoMod.Utils.dll` and `Mono.Cecil.dll` together.
- Original **PrismaticHelper 1.12.0**: `PrismaticHelper.zip`, available from the
  [supported archive](https://gamebanana.com/mmdl/1207039).
- The Workspace, Shared and Tools repositories. Host requirements are described
  in the [workspace README][workspace-readme].

Keep the archive intact; do not extract its DLL or edit its code. The archive and
embedded assembly hashes are recorded in [mod-rebuild.json](mod-rebuild.json).

Save the downloaded archive as `PrismaticHelper.zip` in the original installation's `Mods` directory.

## Placement

```text
Workspace/
  Shared/
  Tools/
  Mods/
    PrismaticHelper/                 # this repository

Celeste/                    # your original game installation
  Celeste.dll
  FNA.dll
  Mods/
    PrismaticHelper.zip
```

Other required Mod archives stay together in the original installation's `Mods`
directory.

## Build

From the workspace directory, use the host options in the
[Tools README][tools-readme]. For example, for Godot:

```powershell
pwsh ./Tools/Prepare.ps1 `
  -CelesteDirectory '/path/to/Celeste' `
  -AudioBankDirectory '/path/to/Desktop' `
  -Targets Godot `
  -IncludeHelpers
```

Preparation verifies the supported inputs, builds dependencies and creates the
runtime package at `Content/Celeste/Mods/PrismaticHelper.zip`. Generated source, tools and
intermediate build files remain under the workspace's ignored `artifacts/`
directory.

## License

See [LICENSE](LICENSE) and [NOTICE.md](NOTICE.md). Original game files, Mod
archives and locally generated packages are not included in this repository.

[workspace-readme]: https://github.com/CelesteResearch/Workspace/blob/main/README.md
[tools-readme]: https://github.com/CelesteResearch/Tools/blob/main/README.md
