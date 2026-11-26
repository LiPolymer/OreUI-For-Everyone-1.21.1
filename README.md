# OreUI For Everyone (1.21.1)

[![Minecraft 1.21.1](https://img.shields.io/badge/Minecraft-1.21.1-62B47A?logo=minecraft&logoColor=white)](https://www.minecraft.net/)
[![Modrinth](https://img.shields.io/badge/Modrinth-下载-00AF5C?logo=modrinth&logoColor=white)](https://modrinth.com/resourcepack/oreuife)
[![CurseForge](https://img.shields.io/badge/CurseForge-下载-F16436?logo=curseforge&logoColor=white)](https://www.curseforge.com/minecraft/texture-packs/oreui-for-everyone)
[![GitLab Pipelines](https://img.shields.io/badge/GitLab-测试构建-FC6D26?logo=gitlab&logoColor=white)](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/pipelines)
[![License](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](LICENSE)

**让更多模组拥有统一、清爽的 AE2 OreUI 风格。**

面向 Minecraft Java Edition 1.21.1 的 OreUI For Everyone 移植与补丁项目。

## 简介

**OreUI For Everyone (1.21.1)** 是 [OreUI For Everyone](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1) 的 Minecraft 1.21.1 适配仓库，将 [Applied Energistics 2 (AE2)](https://modrinth.com/mod/ae2) 的 OreUI 视觉风格延续到 1.21.1 的原版与模组界面中。

本项目以**子模块 + 自动转换 + 补丁覆盖**的方式工作：

- 通过 Git Submodule 跟踪上游 1.20.1 仓库（`submodules/OreUIForEveryone`）。
- 构建时借助 [ShulkerRDK](https://gitlab.com/LiPolymer/ShulkerRDK) 自动排除旧版 `ae2` / `advanced_ae` 纹理、转换 `.psd` 源文件，并将资源包格式从 `15`（1.20.1）自动迁移至 `34`（1.21.1）。
- 在此基础上叠加 [`src/`](src/) 中的 1.21.1 专属修补纹理（支持 `.png`、`.aseprite`、`.psd` 等）与包元数据。

> [!NOTE]
> 实际显示效果取决于所安装的模组与版本。上游完整适配及贡献记录请查看 [`contributor.txt`](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1/blob/main/contributor.txt)（构建产物内同时附带为 `contributors.csv`）。

## 安装

1. **正式版本**请前往 [Modrinth](https://modrinth.com/resourcepack/oreuife) 或 [CurseForge](https://www.curseforge.com/minecraft/texture-packs/oreui-for-everyone) 下载适用于 Minecraft 1.21.1 的发布包；**测试构建**可前往 [GitLab Pipelines](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/pipelines) 下载最新流水线产物（注意需先解压 CI 归档包，取出 `build/` 目录内的 `.zip` 资源包）。
2. 将资源包压缩文件放入 `.minecraft/resourcepacks` 目录，无需解压资源包本身。
3. 在游戏中打开「选项 → 资源包」，启用本资源包。
4. 如果同时使用其他会修改 GUI 的资源包，请将本资源包置于更高优先级。

## 构建本项目

构建需要 **.NET 8.0**（或兼容运行环境）；首次运行 `srdk` 脚本时会自动下载构建工具链与扩展至 `shulker/local/`。

在 Windows（PowerShell）上克隆仓库并构建：

```powershell
git clone --recursive https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1.git
cd OreUI-For-Everyone-1.21.1
.\srdk.ps1 build
```

在 Linux / macOS 上（需 `bash`、`curl` 或 `wget`，以及 `jq` 或 `python3`）克隆仓库并构建：

```sh
git clone --recursive https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1.git
cd OreUI-For-Everyone-1.21.1
chmod +x srdk
./srdk build
```

> [!TIP]
> 若已克隆主仓库但未初始化子模块，可先执行 `git submodule update --init --recursive`。本项目亦同步镜像至 [GitHub 仓库](https://github.com/LiPolymer/OreUI-For-Everyone-1.21.1)。

构建产物将输出至 `build/OreUIForEveryone_1.21.1patch_<版本号>.zip`（例如 `build/OreUIForEveryone_1.21.1patch_4.0.0.zip`）。

## 参与贡献

欢迎协助完善 1.21.1 适配与补丁内容：

- **通用模组适配或纹理修改**：建议优先向 [上游 1.20.1 仓库](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1) 提交贡献，本仓库会同步上游变更并自动完成大部分资源转换。
- **1.21.1 专属修补与版本差异修复**：
  1. Fork 本仓库并创建分支（如果你有 GitLab 账户，推荐前往 [GitLab 仓库](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1) 创建 Merge Request；同样欢迎前往 [GitHub 仓库](https://github.com/LiPolymer/OreUI-For-Everyone-1.21.1) 提交 Pull Request）。
  2. 将补丁资源放入 `src/assets/<mod_id>/` 对应路径（支持 `.png`、`.aseprite`、`.psd` 等源文件）。
  3. 运行 `.\srdk.ps1 build` 或 `./srdk build` 打包，确认游戏中界面显示无误后提交请求。

问题反馈与建议请前往 [GitLab Issues](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/issues) 或 [GitHub Issues](https://github.com/LiPolymer/OreUI-For-Everyone-1.21.1/issues)。

## 相关项目

- [OreUI-For-Everyone-1.20.1](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1) - 上游主仓库，面向 Minecraft 1.20.1 的原版资源包
- [OreUI-For-Everyone-forked](https://github.com/RyanLuoJiayuan1120/OreUI-For-Everyone-forked) - 社区的另一个 1.21+ 移植
- [OreUIForEveryone-1.21.1-Extended](https://github.com/OnDreamQwQ/OreUIForEveryone-1.21.1-Extended) - 适用于 1.21.1 版本的 OreUI 扩展包
- [ShulkerRDK](https://gitlab.com/LiPolymer/ShulkerRDK) - 本项目使用的资源包构建与自动转换工具链

> [!TIP]
> 关于适用于 Windows 10/11 的 OreUI For Windows，请见 [OreUI For Windows](https://github.com/ReConstruction-127/OreUI-For-Windows)

## 致谢

感谢上游作者 **Re_Construction、Delta、AL、jihan_hanhan** 以及所有参与测试、反馈和适配工作的贡献者（完整贡献记录见上游 [`contributor.txt`](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1/blob/main/contributor.txt)）。

感谢 **LiPolymer** 负责本项目的 1.21.1 移植、自动化转换与补丁维护，以及所有提交修补的贡献者。

## 许可证

本项目基于 [GNU Affero General Public License v3.0](LICENSE) 开源，并在原项目相同的 AGPL-3.0 协议下再分发原作资源。

---
