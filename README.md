# RIME-LMDG-tracker

## 背景

由于 [amzxyz/RIME-LMDG#22](https://github.com/amzxyz/RIME-LMDG/issues/22), [Nix](https://nixos.org/) 等包管理器无法顺利完成对 `RIME-LMDG` 的打包，致使 [rime-wanxiang](https://github.com/NixOS/nixpkgs/blob/master/pkgs/by-name/ri/rime-wanxiang/package.nix) 等包需要手动调整才能使用。

## 实现

本仓库使用 [GitHub Actions](.github/workflows/ci.yml) 定时抓取 [amzxyz/RIME-LMDG/releases/tag/LTS](https://github.com/amzxyz/RIME-LMDG/releases/tag/LTS) 中 `wanxiang-lts-zh-hans.gram`，并发布在 [jetcookies/RIME-LMDG-tracker/releases](https://github.com/jetcookies/RIME-LMDG-tracker/releases)，供有需要的用户下载使用。

## 集成

本仓库 tag 命名遵循 [nixpkgs versioning guidelines](https://github.com/NixOS/nixpkgs/blob/master/pkgs/README.md#versioning)。考虑到这是一个个人项目，且代码质量很差 (AI 生成)，暂不保证任何兼容性。本仓库的示例打包在 [github:jetcookies/nur-packages#rime-lmdg](https://github.com/jetcookies/nur-packages/blob/main/pkgs/rime-lmdg/default.nix), 并可通过 [NUR](https://nur.nix-community.org/repos/jetcookies/) 导入使用。