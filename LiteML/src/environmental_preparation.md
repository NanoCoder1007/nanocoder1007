# 环境准备
## 2.1 安装 Rust 工具链
LiteML 基于标准 Rust 生态开发，需先配置 Rust 编译环境：
```bash
# Windows/Linux/macOS 通用安装命令
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

安装完成后执行以下命令验证环境：
```bash
rustc --version
cargo --version
```

## 2.2 安装与验证
```bash
cargo install liteml
```

验证安装：
```
liteml
```

---