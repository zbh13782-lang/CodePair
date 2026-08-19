# Go 编码范式

适用于 Go API、服务、repository、client、worker 和并发代码。

## 1. 包与接口

- 包名短小、语义明确，沿用项目已有分层约定
- handler / controller 只做参数绑定、校验和响应适配
- service / usecase 处理业务编排
- repository / dao 处理数据访问
- client / adapter 处理外部协议
- interface 定义在消费方一侧，且只包含真实需要的方法

## 2. Go 代码门禁

- 每个错误都要处理，保留错误链。
- 不要用 panic 表达普通业务失败。
- goroutine 需要有生命周期管理，避免泄漏。
- 共享状态访问要通过 mutex / channel / 项目现有并发封装。
- 处理 nil / empty / zero value 时要和 API 契约保持一致。
- 外部调用错误要在适配层转换，而不是直接冒泡到业务层。

## 3. 验证

- 运行 `gofmt` 与相关 `go test`
- 涉及并发或底层模块时评估 `-race`、`go vet` 或项目 lint
- 覆盖错误分支、重试、超时和状态流转场景
