# Tiny Apps · 程序分享

一些打开浏览器就能用的小程序。不用安装，没有广告，数据留在本地。

线上地址（仓库名使用 `tiny-apps` 并部署 GitHub Pages 后）：

```text
https://dottedline-2008.github.io/tiny-apps/
```

## 目录结构

一个仓库，多个程序；**每个程序一个独立目录**，根目录只放目录页和公共说明。

```text
tiny-apps/
├── index.html                     # 程序目录页（首页）
├── README.md                      # 仓库说明
├── .nojekyll                      # GitHub Pages 配置
└── apps/
    └── prefrontal-trainer/        # 一个程序 = 一个目录
        ├── index.html             # 程序入口
        ├── preview.png            # 程序预览图
        └── README.md              # 程序自己的说明
```

## 现有程序

| 程序 | 目录 | 说明 |
| --- | --- | --- |
| [前额叶训练](apps/prefrontal-trainer/) | `apps/prefrontal-trainer/` | 五项移动端认知训练：N-back、Stroop、规则切换、汉诺塔、舒尔特方格。纯 HTML，离线可用。 |

## 为什么按目录分，而不是全部堆在根目录？

- **一个程序一个目录**：文件互不干扰，复制、更新、删除都只动一个文件夹。
- **入口清晰**：每个程序都有自己的 `index.html`，地址就是 `apps/程序名/`。
- **方便以后拆分**：某个程序变复杂、需要构建或独立发布时，可以整体搬到独立仓库，目录页保留一个链接即可。
- **根目录保持干净**：只放目录页、README 和公共配置，不混入某个程序的 CSS/JS。

不建议把所有程序的 HTML 都平铺在根目录，时间一长会很难维护，也容易发生文件名冲突。

## 新增一个程序

1. 在 `apps/` 下新建一个英文小写、用连字符的目录，例如：

   ```text
   apps/timer/
   ```

2. 放入程序入口和它自己的资源：

   ```text
   apps/timer/
   ├── index.html
   ├── preview.png
   └── README.md
   ```

3. 在根目录 `index.html` 中复制一张 `.app-card`，修改：
   - 程序名、描述、标签
   - `preview.png` 路径
   - “进入程序”链接指向 `apps/timer/`
   - 序号和状态

4. 在本 README 的“现有程序”表格中补一行。

5. 把新目录和修改后的根目录页一起提交。

### 目录命名约定

- 小写英文，单词之间用连字符：`image-compressor`、`pomodoro`
- 程序目录内自带 CSS / JS / 图片，不依赖其他程序目录
- 每个程序至少有一个 `README.md`
- 预览图建议 390 × 844 或 16:10，控制在 300 KB 以内

## 部署 GitHub Pages

1. 新建 public 仓库，仓库名例如 `tiny-apps`
2. 把本目录下的所有文件上传到仓库根目录
3. 进入 **Settings → Pages**
4. Source 选择 **Deploy from a branch**
5. Branch 选择 `main`，目录选择 `/ (root)`
6. 保存后访问 `https://<用户名>.github.io/tiny-apps/`

## 数据与隐私

这些程序默认不依赖后端。训练记录、偏好等数据保存在浏览器 `localStorage` 中，不会上传到服务器。清除浏览器数据或更换设备后，记录不会自动同步。

## 说明

仓库内程序为个人作品，按现状分享，不保证适用于所有设备或场景。涉及健康、认知训练等内容的程序仅用于日常练习与自我观察，不替代专业医疗建议。
