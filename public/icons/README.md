# HD-Icons 图标库（自托管副本）

本目录是 [xushier/HD-Icons](https://github.com/xushier/HD-Icons) 的完整镜像副本，用于给仪表盘 / 导航页提供稳定的图标直链。

## 目录

| 目录 | 数量 | 说明 |
|---|---|---|
| `border-radius/` | 1085 | 1024×1024 圆角矩形 PNG |
| `circle/` | 126 | 1024×1024 圆形 PNG |
| `svg/` | 604 | SVG 矢量 |
| `icons.json` | — | 索引文件，`{name, ext, style, path}` |
| `index.html` | — | 可视化浏览页，点击图标复制链接 |
| `LICENSE` | — | 上游 MIT 许可证原文 |

三种风格的文件名一一对应，同一个名字可在不同目录下都取到。

## 用法

浏览页：`https://<你的域名>/icons/`

直链格式：

```
https://<你的域名>/icons/border-radius/图标名.png
https://<你的域名>/icons/circle/图标名.png
https://<你的域名>/icons/svg/图标名.svg
```

`<你的域名>` 用 `telegraph-image-b91.pages.dev` 或你绑定的自定义域名。

在页面里想批量取名字，直接读 `/icons/icons.json`：

```js
const { icons } = await fetch('/icons/icons.json').then(r => r.json());
// icons: [{ name: "docker-1", ext: "png", style: "border-radius", path: "/icons/border-radius/docker-1.png" }, ...]
```

## 授权与免责

- 代码与编排：**MIT License, Copyright (c) 2022 xushier**，许可证原文见 `LICENSE`。
- 图标中的产品名称、商标、注册商标归**各自所有者**，此处仅用于识别目的（上游 README 的免责声明同样适用）。
- 上游作者在 README 中注明「项目批量使用请告知」，本项目为个人自托管使用。

## 更新方式

上游仓库更新后，重新下载并覆盖本目录即可：

```bash
curl -L -o hd-icons.tar.gz https://codeload.github.com/xushier/HD-Icons/tar.gz/refs/heads/main
tar -xzf hd-icons.tar.gz -C /tmp --strip-components=1
cp -r /tmp/border-radius /tmp/circle /tmp/svg public/icons/
# 然后重新生成 icons.json
```
