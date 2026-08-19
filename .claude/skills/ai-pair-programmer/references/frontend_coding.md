# 前端编码范式

适用于 React / Vue / TypeScript / 小程序等前端实现。

## 1. 组件与状态

- 页面组件负责布局和数据装配
- 复杂业务判断下沉到 hook / composable / service / store 等层
- 组件单一职责，props、events、slots 语义清晰
- 跨组件共享状态尽量走项目已有的 store / query / cache 机制

## 2. TypeScript 与数据契约

- 不要为了省事使用 `any`，不要为真实不确定性做双重断言或非空断言
- API 响应要转换到视图模型，组件里不要散落字段兜底和枚举翻译
- 复用项目已有常量、路由和权限定义，不要复制魔法字符串
- 异步请求要处理 loading / error / cancel / stale response

## 3. 前端门禁

- UI 组件不要直接堆业务规则。
- 要处理空态、错误态、超时态和禁用态。
- 不要为了局部需求引入新的 UI 库或污染全局样式。
- 避免旧请求覆盖新状态造成竞态问题。

## 4. 验证

- 运行 lint / typecheck / test / build
- 页面交互/布局改动做人工浏览或截图校验
- 共享组件和全局状态改动要说明回归范围
