# xbookmarks 使用帮助

这是 xbookmarks 的公开帮助文档。使用方法见 [帮助页](https://in23555.github.io/xbookmarks-help/)，数据处理见 [隐私说明](https://in23555.github.io/xbookmarks-help/privacy.html)。

本仓库仅包含公开文档，不包含收藏数据、凭据或私有项目源码。

## 加密备份

“本地导出”和手动“提交云端”会把普通收藏、隐藏收藏和速记写入一个加密 JSON 文件。备份使用当前登录口令，通过 Web Crypto AES-256-GCM 和 PBKDF2-SHA256（600,000 次）加密；每次使用新的盐和 IV。Token 与口令校验记录不在备份中。浏览器本地存储仍是明文。

“本地导入”和“拉取云端”须用与备份相同的登录口令。口令不符或文件损坏时，不会覆盖本地数据。修改登录口令后，须重新导出并提交；旧备份仍需旧口令，无法找回。

如果 GitHub 仓库中的 `data/bookmarks.json` 仍是旧版明文文件，请先下载文件，通过扩展“本地导入”确认迁移，再“提交云端”改为加密文件。新版“拉取云端”只接受加密文件；加密不会清除 Git 历史中的旧明文。

问题反馈请使用 [GitHub Issues](https://github.com/in23555/xbookmarks-help/issues)，不要公开 Token、口令或真实备份。
