# 修复 CI：ubuntu-26.04 runner 不再提供 Python 3.9

## 失败信息
- python-package workflow 在 ubuntu-latest（Ubuntu 26.04）上，
  Python 3.9 相关 job 失败（runner 不再内置 3.9，且部分依赖无 3.9 wheel）。

## 原因分析
- ubuntu-26.04 runner 移除 Python 3.9；矩阵仍包含 3.9 → 失败。

## 修复内容
- `.github/workflows/python-package.yml`: python-version 矩阵改为 ["3.10", "3.11"]。

## 验证记录
| Run | 结果 |
|---|---|
| 42427295510 | ✅ success |
