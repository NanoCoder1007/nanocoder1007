## 项目概述

LiteML 是基于 Rust 实现的单文件编译器，由以下三个核心模块组成：

| 模块    | 作用                                       | 关键文件         |
| :------ | :----------------------------------------- | :--------------- |
| lexer   | 将源代码切分为 token，跳过空白与 `//` 注释 | `src/lexer.rs`   |
| parser  | 递归下降解析 token，构建 AST（抽象语法树） | `src/parser.rs`  |
| codegen | 将 AST 译为完整的 HTML 文本                | `src/codegen.rs` |

整个编译流程如下：

```
.ltml 文件 → lexer → token 序列 → parser → AST → codegen → .html 文件
```

