# 大医精诚 · 个性化版更新源（公开分发）

本仓库只放个性化版的更新清单与安装包，供 App 内「检查更新」匿名下载。
源码与备份在私有仓库 `cAme11ia-private01`。

- `personal.json` —— 个性化版更新清单，v1.6.3 / versionCode 67
- `yike-personal.apk` —— 对应安装包，size 293461，sha256 `9b9c09bb583efe54b48a9b3fc197df9599891b5bad7bf5479614891de42a6602`

## 为什么公开

App 的更新器是匿名 HTTPS GET，不带令牌；私有仓库的 raw 链接会返回 404，
免费账户的私有仓库也不支持 GitHub Pages。因此分发仓必须公开。
清单里只有版本号、哈希与更新说明，**没有网盘提取码等敏感信息**。

## 维护

发个性化版新包：

1. `./android/build.sh --personal`（versionCode 自动 +1）；
2. `python3 tools/release_personal.py --apk android/大医精诚-个性版.apk --notes "..."`；
3. 先把新 APK 覆盖到本仓库的 `yike-personal.apk`；
4. 再把生成的 `personal.json` 覆盖上来（先包后清单）。

App 下载后会用清单里的 `sha256` 校验，两个文件必须同时更新。
