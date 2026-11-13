# IEEE Papers to Drive

按标题或 DOI 核对 IEEE 论文，通过 IEEE Xplore 的官方 Download PDFs 批量下载，逐篇核验并打包。需要时可把压缩包和索引上传到 Google Drive。

## 配套环境

| 配套 | 用途 |
| --- | --- |
| Codex 与本地技能支持 | 安装和调用本技能 |
| Ego Lite 浏览器、Ego CLI 与 ego-browser skill | 打开 IEEE Xplore、操作官方批量下载、保存下载文件。运行 ego-browser skill 可查看当前指南 |
| IEEE Xplore 访问权限 | 下载订阅论文时使用有权访问的学校或机构账户。密码和多因素认证由使用者在浏览器中完成 |
| Python 3 与 PDF 文本提取工具 | 用 pypdf 等工具核验标题、DOI 和页数，并用 Python 标准库核验 ZIP 和 SHA-256 |
| Google Drive 连接器与 google-drive:google-drive skill | 要求上传时使用。连接 Drive 后提供目标文件夹链接或 ID |

## 安装与调用

将仓库内的 ieee-papers-to-drive/ 目录复制到 Codex 个人技能目录 ~/.codex/skills/。可在本机的 references/user-defaults.md 中填写机构和目标文件夹。

在 Codex 中输入以下请求，再附上论文标题或 DOI 列表。

> 使用 $ieee-papers-to-drive 下载以下 IEEE 论文，逐篇核验 DOI，并交付 ZIP 和索引。

需要上传时，在同一请求中加上「将核验后的压缩包和索引上传到这个 Google Drive 文件夹」，并提供文件夹链接。

每批默认最多选 8 篇。成功数按实际 ZIP 中核验通过的 PDF 计算。
