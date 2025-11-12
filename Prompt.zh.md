## 任务1

**任务类型：** 需求实现

**提示词：**
```
为Hono.js应用添加JWT Auth Middleware支持，算法为HS256，secret为`your-256-bit-secret`。要求如下：

- 为`/api/v1/*`增加JWT验证，其他的URL放行
- 验证失败时返回401状态码和JSON格式的错误信息
- 增加基于username和password获取jwt的功能，生成的JWT token的payload的sub为username，过期时间为30天
- JWT token来自于请求头的`Authorization`字段，格式为`Bearer <token>`，同时也支持x-api-key查询字段传递JWT Token
```
