# 触控风向标网站

网站地址：http://www.miaocf.cn。网站仓库：miaocf/touch-radar-site。

2026-10-31 检查：HTTP 返回 200；HTTPS 证书域名不匹配，尚未通过校验。状态为该次检查结果，并非实时监测。

本目录是公开发布目录，仅含 index.html、release.json、CNAME、.nojekyll 及本说明。评论和收藏在浏览器本地；作者源代码与采集脚本不放入此公开仓库。

在项目根目录双击「更新看板.command」会采集、运行检查、构建并同步所有本地交付目录。它不会自动推送网站。只修改页面、不采集时运行 `python3 collector/update.py --skip-collect`。

发布前运行 `python3 collector/release.py verify`。将本目录公开文件提交到网站仓库 main 分支；保留现有 CNAME 和 Pages 设置。发布后核对网站 /release.json 的 version，以及 /index.html 的 SHA-256 是否与本地一致。只有两者匹配才算上线完成。

每次更新的本地备份在 .releases/<version>/。撤回当前本地页面：`python3 collector/release.py rollback --version <version>`。回滚只恢复本地交付页面，不修改作者源代码；线上回滚需要将恢复后的网站文件重新发布。首次回滚可能恢复到没有 release.json 的旧版本。
