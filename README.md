# OreUI For Everyone (1.21.1)

[![Minecraft 1.21.1](https://img.shields.io/badge/Minecraft-1.21.1-62B47A?logo=minecraft&logoColor=white)](https://www.minecraft.net/)
[![Modrinth](https://img.shields.io/badge/Modrinth-下载-00AF5C?logo=modrinth&logoColor=white)](https://modrinth.com/resourcepack/oreuife)
[![CurseForge](https://img.shields.io/badge/CurseForge-下载-F16436?logo=curseforge&logoColor=white)](https://www.curseforge.com/minecraft/texture-packs/oreui-for-everyone)
[![GitLab Pipelines](https://img.shields.io/badge/GitLab-测试构建-FC6D26?logo=gitlab&logoColor=white)](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/pipelines)
[![License](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](LICENSE)

**让更多模组拥有统一、清爽的 AE2 OreUI 风格。**

面向 Minecraft Java Edition 1.21.1 的 OreUI For Everyone 移植补丁，已并入 [OreUIForEveryone-1.21.1-Extended](https://github.com/OnDreamQwQ/OreUIForEveryone-1.21.1-Extended) 扩展材质。

## 简介

**OreUI For Everyone** 将 [Applied Energistics 2 (AE2)](https://modrinth.com/mod/ae2) 的 OreUI 视觉风格移植到原版与其他模组的界面中。本项目基于 [1.20.1 上游仓库](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1) 自动转换并补充 1.21.1 所需的资源修补，同时集成 [Extended 扩展包](https://github.com/OnDreamQwQ/OreUIForEveryone-1.21.1-Extended)，无需手动叠加多个包。

> [!NOTE]
> 实际显示效果取决于所安装的模组与版本，完整上游适配记录请查看 [`contributor.txt`](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1/blob/main/contributor.txt)。

## 安装

1. 正式版请从 [Modrinth](https://modrinth.com/resourcepack/oreuife) 或 [CurseForge](https://www.curseforge.com/minecraft/texture-packs/oreui-for-everyone) 下载对应 1.21.1 的版本；测试构建可前往 [GitLab Pipelines](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/pipelines) 获取。
2. 将资源包压缩文件放入 `.minecraft/resourcepacks` 目录，无需解压（若下载的是 GitLab CI 归档包，需先取出其中的 `.zip`）。
3. 在游戏中打开「选项 → 资源包」，启用本资源包。
4. 如果同时使用其他会修改 GUI 的资源包，请将本资源包置于更高优先级。

## 构建本项目

构建需要 [.NET 10.0](https://dotnet.microsoft.com/download/dotnet/10.0) 运行环境。

Windows（PowerShell）：

```powershell
git clone --recursive https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1.git
cd OreUI-For-Everyone-1.21.1
./srdk build
```

Linux / macOS：

```sh
git clone --recursive https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1.git
cd OreUI-For-Everyone-1.21.1
chmod +x srdk
./srdk build
```

构建产物输出至 `build/` 目录。

## 参与贡献

通用材质适配建议直接提交到 [1.20.1 上游仓库](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1)；针对 1.21.1 的修补欢迎在本仓库提交：

1. Fork 本仓库并创建分支（推荐在 [GitLab](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1) 提交 Merge Request，也接受 [GitHub](https://github.com/LiPolymer/OreUI-For-Everyone-1.21.1) 的 Pull Request）。
2. 将修补资源放入 `src/assets/<mod_id>/` 对应路径。
3. 构建并确认游戏内显示无误后提交请求。

问题反馈请前往 [GitLab Issues](https://gitlab.com/LiPolymer/OreUI-For-Everyone-1.21.1/-/issues) 或 [GitHub Issues](https://github.com/LiPolymer/OreUI-For-Everyone-1.21.1/issues)。

## 相关项目

- [OreUI-For-Everyone-1.20.1](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1) - 上游主项目（1.20.1）
- [OreUIForEveryone-1.21.1-Extended](https://github.com/OnDreamQwQ/OreUIForEveryone-1.21.1-Extended) - 1.21.1 扩展包（已并入本项目构建）
- [ShulkerRDK](https://github.com/LiPolymer/ShulkerRDK) - 本项目使用的资源包构建工具

## 致谢

感谢 **Re_Construction、Delta、AL、jihan_hanhan、OnDreamQwQ** 以及所有参与测试、反馈和适配工作的贡献者。详细贡献记录见上游 [`contributor.txt`](https://github.com/ReConstruction-127/OreUI-For-Everyone-1.20.1/blob/main/contributor.txt)。

## 许可证

本项目基于 [GNU Affero General Public License v3.0](LICENSE) 开源，并在原项目相同协议下再分发上游资源。
