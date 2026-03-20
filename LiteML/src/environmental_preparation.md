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

## 2.2 克隆并构建项目
```bash
# 克隆仓库
git clone https://github.com/NanoCoder1007/LiteML.git
cd LiteML

# 以 Release 模式编译（性能最优）
cargo build --release

# 或直接通过 Cargo 运行（开发调试）
cargo run -- test.liteml
```

编译完成后，生成的二进制文件位于：
```
target/release/liteml
```

---