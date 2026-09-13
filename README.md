[README.md](https://github.com/user-attachments/files/32160389/README.md)
# 许廷伟 · 个人主页

纯 HTML + CSS + 一点点原生 JS，没有构建步骤、没有依赖。改内容只需要编辑 `index.html`。

## 文件说明

| 文件 | 作用 |
| --- | --- |
| `index.html` | 页面本体，样式和脚本都写在里面 |
| `favicon.svg` | 浏览器标签页小图标 |
| `.nojekyll` | 告诉 GitHub Pages 别用 Jekyll 处理，保持原样发布 |
| `README.md` | 本文件 |

## 本地预览

双击 `index.html` 用浏览器打开即可。或者起个本地服务：

```bash
# 任选一个，在项目目录下执行
python -m http.server 8000
npx serve
```

然后访问 <http://localhost:8000>。

## 部署到 GitHub Pages

### 方式一：`<用户名>.github.io`（推荐，地址最短）

访问地址会是 `https://<用户名>.github.io`，不带任何子路径。

1. 在 GitHub 新建仓库，仓库名必须是 **`<你的用户名>.github.io`**（用户名完全一致，大小写敏感）。
2. 推代码上去：

   ```bash
   git init
   git add .
   git commit -m "add personal homepage"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<你的用户名>.github.io.git
   git push -u origin main
   ```

3. 等 1~2 分钟，访问 `https://<用户名>.github.io`。

### 方式二：普通仓库

仓库名随意，比如 `homepage`，访问地址是 `https://<用户名>.github.io/homepage/`。

推到 GitHub 后，进仓库 **Settings → Pages**，把 **Source** 设为 `Deploy from a branch`，
分支选 `main`、目录选 `/ (root)`，保存，等一两分钟。

## ⚠️ 发布前必须核对的内容

页面是公开的，招聘方会看到。下面这些是**我推测或代写的草稿**，请逐条核实后再发布：

- [ ] **四段实习的时间** —— 按「2026.09 读研一」倒推的：得物 2026.01–05、Shopee 2025.07–09、
      安永 2025.01–03、税务局 2023.07–08。**大概率不准，改成真实时间**，
      并且要和你简历上的时间一致 —— 两边对不上比不写更糟
- [ ] **四段实习的描述** —— 按岗位常见职责写的草稿，**没有编任何具体数字**。
      逐条过一遍：没做过的事删掉，做过的事改成你真实做的
- [ ] **补充数字** —— 描述里能加量化结果的地方都空着（比如「处理 XX 份资料」「覆盖 XX 家客户」）。
      只有你知道真实数字，加上去说服力会强很多
- [ ] **税务局岗位名** —— 现在只写「实习生」，建议补科室，比如「纳税服务科 · 实习生」
- [ ] **教育时间** —— 复旦 2026.09–2028.06、上财 2022.09–2026.06，同样要核对
- [ ] **实习排序** —— 现在是倒序（最近的在上）。改成真实时间后顺序可能还要调
- [ ] **领英** —— `index.html` 里那行是注释掉的，有账号再取消注释填地址；
      没有就别加，坏链接比没有更难看

邮箱已经填成 `nelsonlie21@163.com`。

## 其他可改的地方

- **头像** —— 把 `<div class="avatar" aria-hidden="true">许</div>` 换成
  `<img class="avatar" src="avatar.jpg" alt="许廷伟">`，图片放同目录
- **主题色** —— `:root` 里的 `--accent`（当前 `#4f46e5` 靛蓝）和 `--accent-bg`；
  深色模式的颜色在同一文件下面的 `@media (prefers-color-scheme: dark)` 里，记得一起改
- **favicon** —— 编辑 `favicon.svg` 里的文字和 `fill`
- **侧栏头衔** —— 搜 `复旦大学 · 保险专硕研一`，可以改成别的（比如「求职中 · 保险/精算方向」）

## 已经内置的东西

- 左侧栏在桌面端固定，右侧内容滚动；滚动时左侧导航自动高亮当前区块
- 窄屏（≤860px）自动变成顶部横栏，手机能正常看
- 跟随系统的深色模式
- 键盘焦点样式、`aria` 标注、支持 `prefers-reduced-motion`
- 页脚年份自动更新

## 想加更多板块

在 `<main>` 里照着已有 `<section>` 复制一份，改 `id`，然后在左侧 `<nav>` 里加一个
`<a class="nav-link" href="#新id">标题</a>`，滚动高亮会自动生效。

`<ol class="entries">` + `<li class="entry">` 那套结构（教育、实习在用）适合放任何
「标题 + 时间 + 描述」的条目，比如校园经历、证书、获奖。
