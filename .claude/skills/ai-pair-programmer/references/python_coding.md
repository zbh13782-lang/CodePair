# Python 编码范式

适用于 Python API、服务层、脚本、任务处理和数据处理代码。

## 1. 职责边界

- route / handler / CLI 只做参数解析、权限校验、路由和响应适配
- 业务逻辑下沉到 service / domain / usecase 等层
- 外部 HTTP、数据库、缓存、RPC 调用放在 client / repository / adapter / gateway
- 数据结构尽量复用已有 model、dataclass、Pydantic 或 TypedDict

## 2. Python 代码门禁

- 不要在入口层堆业务判断和大量协议转换逻辑。
- 新增公共函数时补类型标注，返回可能为空时明确表达。
- 不要使用裸 `except:`，不要吞掉异常后继续返回成功值。
- 外部调用失败要转换为项目统一错误语义，并保留可定位日志。
- 文件、连接、锁和异步任务要使用适当的 context manager 与 await 语义。
- 常量、状态和关键配置不要散落魔法字符串。

## 3. 测试与验证

- 优先补 pytest / unittest 中已有风格的测试
- 覆盖正常路径、边界输入、依赖失败、异常语义
- 相关类型检查、linter 和格式化按项目已有工具执行
- 异步和 I/O 逻辑要补充失败分支验证
