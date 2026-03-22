## 快速入门

### 1. 创建一个 `.ltml` 文件

```
// index.ltml
index {
    title("LiteML 示例页面", level=1);
    title("特性", level=2);
    title("这是一个三级标题", level=3);
}
```

> 文件扩展名必须是 `.ltml`，否则编译器会报错。

### 2. 编译为 HTML

```bash
# 基本调用
liteml index.ltml

# 指定输出文件名
liteml index.ltml -o out.html
```

> 编译成功后会在同目录生成 `index.html`（除非使用 `-o` 指定其它路径），并在终端打印：
>
> ```
> 已生成 out.html
> ```

### 3. 查看生成的 HTML

```HTML
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="generator" content="LiteML index">
    <title>LiteML 示例页面</title>
</head>
<body>
<h1>LiteML 示例页面</h1>
<h2>特性</h2>
<h3>这是一个三级标题</h3>
</body>
</html>
```
