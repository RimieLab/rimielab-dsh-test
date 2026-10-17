# dsh-rimielab 共同作者插件 · 冒烟测试

本文件用于验证 `dsh-rimielab-bot` 插件在全新仓库上的行为，属于一次性测试产物。

## 期望

- 提交的 author / committer 仍是仓库所有者
  `Rimrose <44104592+SirTamago@users.noreply.github.com>`。
- 提交信息末尾包含：

  ```text
  Co-authored-by: DeepSeek Harness <342685585+dsh-rimielab[bot]@users.noreply.github.com>
  ```

- 推送到 `main` 后，`.github/workflows/devlog.yml` 以 `dsh-rimielab[bot]`
  身份向 devlog issue 追加一条记录。

## 验证

```console
$ git log -1 --format='author:    %an <%ae>%ncommitter: %cn <%ce>%n%n%B'
$ git check-mailmap 'Rimrose <git@rimrose.work>'
$ git check-mailmap 'DeepSeek Harness <dsh@deepseek-harness.invalid>'
```
