# My Project 源码

主项目包，包含核心代码实现。

## 模块说明

| 模块 | 说明 |
|------|------|
| `models/` | 模型定义 |
| `datasets/` | 数据集加载 |
| `engine/` | 训练/评估/推理引擎 |
| `transforms/` | 数据增强 |
| `utils/` | 工具函数 |

## 入口脚本

- `train.py` - 训练入口
- `evaluate.py` - 评估入口
- `inference.py` - 推理入口

## 快速使用

```python
from my_project.models import build_model
from my_project.datasets import build_dataset
from my_project.engine import Trainer

# 构建模型和数据集
model = build_model('resnet50', num_classes=10)
train_dataset, val_dataset = build_dataset('imagenet', root='data/')

# 训练
trainer = Trainer(model, device='cuda')
trainer.train(train_dataset, val_dataset, epochs=100)
```