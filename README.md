# gitee-json-generator

一个通过定时缓存 Gitee API 数据的工具，解决了直接调用 Gitee API 频率有限制以及速度过慢的问题。

## 使用方法

1. 把本仓库 fork 到您的 GitHub 中。
2. 修改 `config.yml` 中的配置信息，添加需要爬取的 Gitee API 链接。
3. 前往 Settings -> Secrets and variables -> Actions，添加 `GITEE_TOKEN`（您的 Gitee 私人令牌）。
4. 前往 Actions 页面，点击绿色的「enable workflows」按钮。
5. 刷新 Actions 页面，点击左侧「Generator」选项卡，再点击右侧的「enable workflow」按钮。
6. 点击 Star 以主动触发 Action 进行测试。

等待 Action 运行完毕，生成 output 路径以及文件就说明配置成功了。

## Gitee API 文档

- Gitee API v5 文档: https://gitee.com/api/v5/swagger
- 私人令牌获取: https://gitee.com/profile/personal_access_tokens

## 示例 API 链接

```yaml
links:
  # 获取用户仓库列表
  - https://gitee.com/api/v5/users/yourname/repos?type=all&per_page=100
  # 获取仓库 issues
  - https://gitee.com/api/v5/repos/owner/repo/issues?state=all&per_page=20
```
