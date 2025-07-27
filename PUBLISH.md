# 发布到npm指南

## 发布步骤

1. **确保你有npm账号**
   ```bash
   npm login
   ```

2. **检查包名是否可用**
   ```bash
   npm view create-userscript
   ```
   如果显示404错误，说明包名可用。

3. **发布到npm**
   ```bash
   npm publish
   ```

4. **验证发布成功**
   ```bash
   npm view create-userscript
   ```

## 使用方式

发布成功后，用户可以通过以下方式使用：

```bash
# 方式1：使用npm create
npm create @javascript-reverse-engineering-infrastructure/userscript my-project

# 方式2：使用npx
npx @javascript-reverse-engineering-infrastructure/create-userscript my-project
```

## 更新版本

当需要更新模板时：

1. 修改代码
2. 更新版本号：
   ```bash
   npm version patch  # 补丁版本 (0.0.1 -> 0.0.2)
   npm version minor  # 次版本 (0.0.1 -> 0.1.0)
   npm version major  # 主版本 (0.0.1 -> 1.0.0)
   ```
3. 重新发布：
   ```bash
   npm publish
   ```

## 注意事项

- 包名 `create-userscript` 需要在npm上是唯一的
- 如果包名已被占用，需要修改 `package.json` 中的 `name` 字段
- 建议使用语义化版本号
- 发布前确保所有文件都在 `files` 字段中正确配置
