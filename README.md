# Yuan Mi | Academic Homepage

基于用户提供的 Minimal Light 静态 HTML 版本，保留其固定左侧个人栏、右侧正文和简洁学术配色；仅移植用户指定的三项效果：论文分类筛选与作者展开、3D 项目词云、全宽火星背景渐变页脚。纯 HTML/CSS/JS，无需 Jekyll 或 Node；字体可选用原模板的 Google Fonts，加载失败时自动回退至系统衬线字体。

## 发布到 GitHub Pages

1. 在 GitHub 新建 Public 仓库，命名为 `你的GitHub用户名.github.io`（不要直接使用别人用户名）。
2. 解压本 ZIP，将其中 **全部文件和 assets 文件夹** 上传至仓库根目录（`index.html` 必须在根目录，而不是另一个子目录内）。`.nojekyll` 是隐藏文件，建议一并上传；也可以在 GitHub 上新建该空文件。
3. 打开 Settings → Pages → Build and deployment，选择 Deploy from a branch → main（或实际默认分支）→ /(root) → Save。
4. 部署成功后访问 `https://你的GitHub用户名.github.io/`。

## 本地预览

在解压后的目录中执行 `python3 -m http.server 8000`，打开 `http://localhost:8000/`；也可双击 index.html（剪贴板在本地文件协议下可能受限）。

## 日常维护

- `index.html`：所有个人资料、论文、教育经历、项目、服务及荣誉。新增论文时复制一个 `<article class="paper">` 区块，修改标题、作者、年份、会议、链接及 `data-tags`。可用标签为 `lead`、`graph`、`physics`、`applied`，空格分隔；筛选计数自动更新。作者列表超出一行时自动显示展开按钮。项目词云中的链接可直接修改为真实项目或仓库地址，目前跳转至本站的研究项目及论文。
- `assets/css/minimal-light.css`：原始 Minimal Light 静态样式；`assets/css/homepage.css`：三项指定效果、响应式布局。
- `assets/js/homepage.js`：标签筛选、作者列表展开、3D 旋转词云（悬停/键盘聚焦暂停，离屏暂停，支持减少动态效果设置）、返回顶部。
- `assets/img/avatar.jpg`：从用户提供的简历中提取的证件照；可用同名图片替换。
- `assets/img/*.svg`：原创抽象主题示意，并非论文的真实方法图；可用自己的论文图替换相应文件并修改图片引用。
- `assets/img/background-*.webp`：来自用户上传的 academic-homepage-template 的原始火星背景。该模板压缩包没有明确许可文件；公开部署前请确认该图片使用授权，或替换成自己的图片（保留对应文件名即可）。

## 发布前核对

- 简历没有确认武汉大学博士后实际入职日期，当前显示已获中国人民大学博士学位，不将武汉大学写成已入职单位。如已入职，修改顶部 position / affiliation 及 About Me，并增加经历。
- 公开邮箱和照片均来自提供的简历；如不希望公开可替换。未公开电话、生日、原始完整简历、在审及备投论文、涉军项目。
- 论文数据依据所提供简历，未独立核验书目信息；CCF/CAS/CSSCI 标签亦沿用简历，未附引用次数以避免过时。Find paper 为按标题搜索，不是假造 DOI 或论文直链。可补充真实的 Paper、Code、Google Scholar、GitHub 和 DBLP 主页链接。
- 静态 Minimal Light 样式及其许可见 LICENSE-minimal-light。第一个模板来源为 https://github.com/w-r-s/academic-homepage-template ，仅参考交互并重写相关代码，保留其提供的火星背景图片以供用户预览和确认使用授权。

## 本版验证

使用 Chromium 内联页面测试通过：8 篇论文默认展示、一作/通讯筛选为 5 篇、作者展开收起、词云自动旋转与悬停暂停、1440px 全宽页脚、390px 手机无横向溢出。本地文件导航受运行环境限制，未实际发布至 GitHub Pages。

## V3 更新

- 顶部粘性导航、当前栏目高亮；移动端导航可横向滚动。
- About Me 学院、导师链接及 Email / CV / Google Scholar / GitHub 联系栏。
- `cv.html` 为公开学术简历网页，支持打印或另存 PDF，不包含出生日期、私人手机号或未公开论文。
- News 使用简历中已知的日期；仅知道年份时不编造月份。
- Publications 删除每篇论文的简介，保留论文标题、作者、会议/期刊、级别及作者角色；新增 Homepage / Code / Paper 链接行。未确认的项目主页、代码链接以灰色显示，待补充；没有确认正式论文页面时使用标明的 Scholar 搜索入口。
- 已核实的链接：学院/导师官方网站、KDD 2026 DBLP 记录、CiGNN arXiv 和 GitHub 仓库、HSSC DOI、ICML PMLR、AAAI 论文页、CPC DOI。
- 更新个人链接：在 `index.html` 搜索 `contact-links`；Google Scholar 目前为搜索入口，GitHub 未填写。更新论文资源：搜索 `paper-links`，将 `<span class="pending-link">` 改成实际 `<a href="...">` 链接。
- 保留 V2 的论文筛选、作者展开、词云和火星页脚。
