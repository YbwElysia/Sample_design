# Tests

单元测试目录，包含数据集、模型、工具函数的测试代码。

## 测试文件

| 文件 | 说明 |
|------|------|
| `test_dataset.py` | 数据集测试 |
| `test_model.py` | 模型测试 |
| `test_utils.py` | 工具函数测试 |
| `test_engine.py` | 训练引擎测试 |

## 运行测试

```bash
# 运行所有测试
pytest test_sample/ -v

# 运行单个测试文件
pytest test_sample/test_dataset.py -v

# 运行带覆盖率
pytest test_sample/ --cov=src/my_project --cov-report=html
```

## 测试规范

1. 测试文件以 `test_` 开头
2. 测试函数以 `test_` 开头
3. 使用 `assert` 进行断言

## 示例

```python
# test_model.py
import torch
from my_project.models import build_model

def test_model_forward():
    model = build_model('resnet50', num_classes=10)
    x = torch.randn(2, 3, 224, 224)
    output = model(x)
    assert output.shape == (2, 10)
```