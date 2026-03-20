# 使用方法
## 4.1 基础用法
自动根据源文件名生成同名 HTML 文件：
```bash
./liteml demo.liteml
```

## 4.2 指定输出路径
自定义 HTML 输出文件名：
```bash
./liteml demo.liteml index.html
```

### 4.3 错误提示
编译器内置严格校验机制，常见错误提示：
- 未找到 `page {}` 块
- `level` 超出 1~6 范围
- 文件读取/写入权限异常
- 语法格式不合法
