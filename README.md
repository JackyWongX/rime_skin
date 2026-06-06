# Rime 小狼毫皮肤在线设计

一个纯 HTML 单文件的小狼毫皮肤颜色设计工具。打开 `index.html` 后，可以粘贴或导入 `weasel.custom.yaml`，修改颜色并实时预览候选窗效果。

## 使用方式

直接用浏览器打开：

```text
index.html
```

不需要安装依赖，不需要启动服务，也不需要编译。

## 功能

- 粘贴 `weasel.custom.yaml` 后自动解析颜色字段
- 导入 `.yaml`、`.yml`、`.txt` 文件
- 按模块分组编辑颜色字段
- 支持颜色选择器、HEX、RGB 输入
- 实时预览小狼毫候选窗
- 支持候选词横排/竖排预览切换
- 支持复制 YAML
- 支持下载 `weasel.custom.yaml`

## 支持的颜色格式

页面输入支持：

```text
#RRGGBB
0xBBGGRR
rgb(r, g, b)
r,g,b
```

注意：小狼毫配置中的 `0x......` 使用 `0xBBGGRR` 顺序，不是网页常见的 `#RRGGBB`。例如网页颜色：

```text
#FFD6E4
```

写入小狼毫 YAML 时应为：

```text
0xE4D6FF
```

本工具会自动处理这个转换。

## 适用范围

当前版本主要面向小狼毫 `weasel.custom.yaml`，重点处理 `preset_color_schemes` 中的 `_color` 字段。

不优先支持鼠须管、复杂 YAML anchor、条件合并或完整 YAML 语义校验。
