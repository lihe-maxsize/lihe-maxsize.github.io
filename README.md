# 个人学术主页（GitHub Pages / Jekyll）

这个仓库是一套“学术展示型”个人主页模板（版式参考 jemdoc 风格）。**你只需要改 `_config.yml`** 就能更新姓名、单位、简介、论文、获奖等信息。

## 目录结构

- `_config.yml`：你的所有信息配置（最重要）
- `index.html`：主页模板（从 `_config.yml` 渲染）
- `assets/css/jemdoc.css`：主样式（jemdoc 风格）
- `assets/css/custom.css`：少量自定义（照片、移动端、BibTeX）
- `assets/img/`：图片目录（放你的头像/照片）

## 如何放照片

1. 把你的照片命名为 `profile.jpg`（或 `png`）
2. 放到 `assets/img/profile.jpg`
3. 修改 `_config.yml`：

```yml
photo:
  path: "/assets/img/profile.jpg"
  alt: "Your photo"
  width: 260
```

> 现在默认使用 `assets/img/profile-placeholder.svg` 作为占位图。

## 如何部署到 GitHub Pages

### 方式 A：用户主页（推荐）

1. 新建仓库：`<你的GitHub用户名>.github.io`
2. 把本目录所有文件提交到该仓库 `main` 分支根目录
3. GitHub 仓库 → Settings → Pages
   - **Source**：Deploy from a branch
   - **Branch**：`main` / root
4. 等待 1–2 分钟，访问 `https://<用户名>.github.io/`

此方式 `_config.yml` 中保持：

```yml
baseurl: ""
```

### 方式 B：项目页（`https://<用户名>.github.io/<repo>/`）

1. 新建仓库：任意名字（如 `homepage`）
2. 提交到 `main` 分支
3. Settings → Pages 选择 `main` / root
4. 把 `_config.yml` 的 `baseurl` 改成你的仓库名：

```yml
baseurl: "/homepage"
```

## 如何更新内容

直接编辑 `_config.yml`：

- **顶部信息**：`author.*`（姓名、职位、单位、地址、邮箱、链接）
- **简介**：`sections.short_bio`（支持 Markdown）
- **经历**：`sections.research_experience`
- **论文**：`sections.publications.preprints / conferences / journals`
  - 每条论文建议填 `id`，这样 `[BibTeX]` 折叠能正常工作
  - `authors` 支持直接写 HTML（例如把你自己加粗：`<b>你的名字</b>`）
- **报告/获奖/服务/教学/指导**：对应 `sections.*`
- **页脚**：`footer.*`

## 本地预览（可选）

若你本机装了 Ruby/Jekyll，可以在仓库根目录运行：

```bash
bundle exec jekyll serve
```

然后访问终端提示的本地地址。

