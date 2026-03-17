# Models

模型定义模块，包含项目中使用的所有深度学习模型。

## 目录结构

```
models/
├── __init__.py      # 模型注册和导出
├── baseline.py      # 基线模型
├── resnet.py        # ResNet 变体
├── vit.py           # Vision Transformer
└── custom.py        # 自定义模型
```

## 添加新模型

### 1. 创建模型文件

```python
# models/my_model.py
import torch.nn as nn

class MyModel(nn.Module):
    def __init__(self, num_classes=10, **kwargs):
        super().__init__()
        # 模型定义
        
    def forward(self, x):
        # 前向传播
        return x
```

### 2. 在 `__init__.py` 中注册

```python
from .my_model import MyModel

__all__ = ['MyModel']

def build_model(name, **kwargs):
    if name == 'my_model':
        return MyModel(**kwargs)
    raise ValueError(f"Unknown model: {name}")
```

## 模型接口规范

所有模型应遵循以下接口：

```python
class BaseModel(nn.Module):
    def __init__(self, num_classes: int, **kwargs):
        """初始化模型"""
        pass
    
    def forward(self, x: torch.Tensor) -> torch.Tensor:
        """前向传播，返回 logits"""
        pass
    
    def get_features(self, x: torch.Tensor) -> torch.Tensor:
        """提取特征向量（可选）"""
        pass
```

## 预训练权重

预训练权重统一放置在 `checkpoints/pretrained/` 目录下。