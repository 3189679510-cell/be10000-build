# ImmortalWrt 编译 - Xiaomi BE10000

## 用途
GitHub Actions 云端编译 ImmortalWrt，包含：
- 128KiB NAND 的 UBI（解决"刷不进"）
- luci-app-dockerman + 缺的 3 个内核模块
- Docker / ttyd / Samba / hd-idle

## 使用
1. 在 GitHub 新建仓库（Public）
2. 把本目录所有文件上传
3. 点 Actions → 左侧 "Build ImmortalWrt for Xiaomi BE10000" → Run workflow
4. 等 2-4 小时
5. 下载 artifact，取 `*.bin` 用 LuCI 刷机（保留 / 不保留配置都行）

## 注意
- 首次编译会下载大量包，可能跑 3-5 小时
- 如果 `CONFIG_TARGET_...` 名字不对，编译会在 make defconfig 时报 unknown symbol，把日志发出来改
