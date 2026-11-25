## 改动说明

<!-- 说明改了什么、为什么改。 -->

## 影响范围

- 相关 Issue：<!-- Closes #123 -->
- 涉及仓库 / 机型 / 版本：
- 是否影响已发布模型：

## 验证

<!-- 贴出实际执行的命令与结果，不要只写"已验证"。 -->

```bash
# 例如
python scripts/validate_model.py yita_gr3mini/v300
python scripts/parallel_check.py --samples 5
```

## 检查项

- [ ] 改动范围聚焦，未包含无关格式化或调试代码
- [ ] 已更新受影响机型目录下的 `model.yaml` 与 `CHANGELOG.md`（如适用）
- [ ] 执行器参数可追溯到 YITA 硬件资料或实测标定（如适用）
- [ ] 未提交数据集、模型权重、密钥或内网地址
- [ ] 新增大文件已走 Git LFS / DVC（如适用）
