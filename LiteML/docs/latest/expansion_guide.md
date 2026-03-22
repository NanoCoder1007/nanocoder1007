## 扩展指南

LiteML 采用模块化设计，添加新语句只需在三个层面实现对应功能。

### 1. 词法层

- 在 `TokenKind` 中新增 token（如 `BoldStart`, `BoldEnd`）。
- 在正则表达式中加上对应捕获组，并在 `lex` 中解析为新的 `TokenKind`。

示例（添加 `**` 用作粗体标记）：

```
// 在 token regex 中加入：
|(?P<bold>\*\*)          # 粗体标记

// 在 lex 中：
} else if caps.name("bold").is_some() {
    Some(Token { kind: TokenKind::Bold, span: pos..pos+2 })
```

### 2. 语法层

- 在 `Stmt` 枚举里加入新变体（如 `Bold(BoldStmt)`），并新增对应 AST 结构。
- 在 `parse_stmt` 中匹配新的关键字并调用专属解析函数。
- 编写 `parse_bold_stmt` 类似 `parse_title_stmt`，处理其语法规则。

### 3. 代码生成层

- 在 `generate_html` 中匹配新 `Stmt`，生成对应 HTML（例如 `<strong>`）。
- 注意保持 安全性：对用户输入进行 HTML 逃逸（目前 `StringLit` 只做了基本转义）。

### 4. 单元测试

- 在 `tests/` 中添加对应的 lexer / parser / codegen 测试，确保新特性不破坏旧行为。

------

## 贡献者指南

1. Fork 本仓库 并创建你的分支（如 `feature/bold`）。
2. 保持代码风格：使用 `rustfmt`，遵守 `clippy` 建议。
3. 提交规范：在 PR 描述中说明：
    - 新增/修改的功能点
    - 关联的 Issue 编号（若有）
    - 运行 `cargo test` 并确认所有测试通过
4. 文档更新：任何对语言特性的改动务必同步更新本 官方文档（`README.md` / `docs/`）。
5. 发布：当 master 达到可用状态时，打 `v0.x` Tag 并在 GitHub Releases 页面上传对应二进制。

------

## 许可证

本项目遵循 MIT 许可证。详情请参见根目录下的 `LICENSE` 文件。