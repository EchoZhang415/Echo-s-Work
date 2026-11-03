# 向上 · 双班级任务看板

无需安装依赖、无需编译的静态网页。支持两个班级独立记录、导入学生名单、多任务同屏、完成/优秀状态、批量标记、撤销、大屏模式、CSV 导出和 JSON 备份恢复。

## 文件说明

- `index.html`：网页入口，必须放在仓库根目录。
- `style.css`：页面样式，与 index.html 放在同一层。
- `app.js`：完整交互逻辑，与 index.html 放在同一层。
- `.nojekyll`：静态发布标记。
- `README.md`：本说明。

## 上传到 GitHub

1. 先将下载的 ZIP 解压。不要把 ZIP 文件本身当作网页上传。
2. 登录 GitHub，创建一个仓库，例如 `class-task-board`。使用免费账号部署此网页时，可选择 Public（公开仓库）。
3. 打开仓库，选择 Add file → Upload files；新建的空仓库也可点击 uploading an existing file。
4. 将解压后的 index.html、style.css、app.js、README.md 和 .nojekyll 上传到仓库根目录。不要在外面再套一层文件夹。
5. 点击 Commit changes 保存。
6. 确认仓库首页能直接看到 index.html、style.css、app.js。

## 开启 GitHub Pages

1. 进入仓库 Settings → Pages。
2. 在 Build and deployment 下，将 Source 设为 Deploy from a branch。
3. Branch 选择实际上传文件的分支（通常为 main），文件夹选择 / (root)。
4. 点击 Save，等待部署完成。
5. 回到 Pages 页面，点击 Visit site 打开网页。以后上传修改后的文件并提交，网站会重新部署。

官方说明：
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 使用方法

1. 在顶部切换两个班级，点击标题旁的铅笔图标修改当前班名。
2. 点击“导入名单”，粘贴 Excel 的姓名列（每行一人），或选择 UTF-8 编码的 CSV/TXT 文件。暂不直接读取 XLSX。
3. 点击“添加任务”，每行输入一项任务。
4. 点击状态按钮，依次切换：未完成 → 完成 → 优秀 → 未完成。
5. 点击任务标题，可修改名称、全班批量标记或删除任务。
6. 点击“大屏模式”和“紧凑显示”，用于课堂投屏。任务很多时可横向滚动，姓名列保持固定。
7. 点击“备份全部班级”下载 JSON 文件；在其他电脑点击“恢复备份”导入。

## 从原来的网页迁移数据

先在原网页点击“备份全部班级”，然后到 GitHub Pages 新网址点击“恢复备份”。不同网址的数据不会自动转移。

## 数据保存说明

- 名单与完成记录只保存在当前浏览器的 localStorage 中，不上传 GitHub，不会跨设备同步。
- 代码包不包含真实学生名单或现有完成记录。示例按钮生成的姓名仅用于演示。
- 不要把学生名单或 JSON 备份提交到公开仓库；请使用网页上的导入和恢复功能。
- 清理网站数据、换浏览器或使用无痕模式，可能导致记录不保留。建议定期下载备份。
- GitHub Pages 版本不包含原平台的账号访问控制；打开网站的人各自看到其浏览器中保存的数据。
- 导出 CSV 只包含当前班级；导出备份包含两个班级。旧的单班备份可恢复到当前班级。

## 本地预览

可直接双击 index.html 查看页面；日常记录建议使用固定的 GitHub Pages 网址，确保保存位置一致。
如已安装 Python，也可在此目录运行 `python -m http.server 8000`，然后打开 http://localhost:8000。
