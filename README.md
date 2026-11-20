# Flux Panel downloads

公开分发仓库，仅提供面板/节点安装脚本、部署模板和已编译资源；不包含面板业务源码或 GitHub 凭证。此仓库不使用 CI，资源由维护者在本机验证后发布。

## 面板安装与更新

```bash
curl -fL https://raw.githubusercontent.com/pkhosn/flux-panel-downloads/refs/heads/main/panel_install.sh -o panel_install.sh
chmod +x panel_install.sh
./panel_install.sh
```

在现有部署目录执行，选择 **2 更新面板**。每次隐藏输入具有 `pkhosn/flux-panel` 仓库 **Contents: Read-only** 权限的 GitHub Token；Token 仅本次下载使用，不保存。无需先运行 git pull。源码按固定提交下载，后端从本地目录构建，前端下载固定版本静态包并校验 SHA256。下载或构建失败时保留运行服务。

首次切换私有部署前，先使用上方公开入口更新一次面板，刷新浏览器后再将源码仓库改私有。

## 节点与探针

请在面板生成完整的一键安装命令；节点服务器不需要 GitHub Token。已安装在线的 Agent 无需为仓库迁移而重装。Agent Linux amd64/arm64 二进制与 SHA256SUMS 在 Releases 中发布，前端资源使用独立 `frontend-*` Release。

## 发布范围

Git 文件仅限本说明、`panel_install.sh`、`install.sh`、`docker-compose-v4.yml`、`docker-compose-v6.yml`。前端和 Agent 二进制仅作为 Release 附件发布。公开仓库中的自动生成 Source code 压缩包仅包含这些公开文件。
