# 个人网站：通过 GitHub 网页部署

使用 Academic Pages 模板，页面结构已准备好，个人内容待补充。
构建和发布在 GitHub 上完成，不需要本地 Docker 或 Ruby。

## 首次部署

1. 登录 GitHub，创建公开仓库，命名为「Yixin-59.github.io」。
2. 将整理后的模板文件上传到仓库根目录，不要多套一层文件夹，也不要上传 local 备份目录。
3. 确保仓库包含 .github/workflows/jekyll-build.yml。如果网页上传遗漏隐藏目录，可在仓库中通过 Add file → Create new file 创建这个路径，粘贴本地同名文件的完整内容。
4. 在仓库 Settings → Pages → Build and deployment → Source 中选择 GitHub Actions。
5. 打开 Actions → Deploy personal website to GitHub Pages → Run workflow，选择默认分支运行。
6. 等待 build 和 deploy 都成功后，从部署结果或 Settings → Pages 打开网站。

工作流会在默认分支更新时自动发布，也可以手动触发。
网站地址和仓库路径会从 GitHub Pages 设置自动读取，兼容个人主页仓库和普通项目仓库。
若首次上传时尚未开启 Pages，第一次工作流可能失败；完成第 4 步后重新运行即可。
当前只完成本地配置，尚未上传到仓库，也尚未执行云端构建。

官方说明：https://docs.github.com/zh/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages

## 填充内容

- 网站标题、姓名、头像、单位、邮箱和个人链接：_config.yml
- 导航：_data/navigation.yml
- 简介、研究方向和近期动态：_pages/about.md
- 简历：_pages/cv.md
- 联系方式：_pages/contact.md
- 论文条目：_publications/
- 项目条目：_portfolio/

默认使用中文；可以根据需要统一改成英文。
当前头像为模板自带的匿名剪影。
网页上打开对应文件后点击编辑，保存提交即可自动更新网站。

## 原始模板备份

修改前的配置、页面、工作流和示例条目保存在 local/template-backup/。
这是仅供本地保留的备份，不要通过网页上传这个目录；网页上传不会自动应用 .gitignore。
其他演示页面已设为不发布。
示例附件目录 files 暂不发布；放入自己的附件后，应从 _config.yml 的 exclude 列表移除 files。
原模板自动关闭 PR 和自动生成演讲地图的工作流已停用。

## 验证状态

已检查本地 YAML 配置和工作流结构。
真实构建、发布和网页显示需要在目标 GitHub 仓库中验证。

