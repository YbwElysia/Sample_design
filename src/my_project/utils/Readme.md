# Utils

工具函数模块，提供项目中通用的工具类和函数。

## 目录结构

```
utils/
├── __init__.py
├── checkpoint.py    # 检查点管理
├── logger.py        # 日志工具
├── metrics.py       # 评估指标
├── seed.py          # 随机种子
├── visualization.py # 可视化工具
└── Readme.md
```

## 使用示例

### Checkpoint

```python
from my_project.utils import save_checkpoint, load_checkpoint

# 保存
save_checkpoint(model, optimizer, epoch, path='checkpoint.pth')

# 加载
load_checkpoint('checkpoint.pth', model, optimizer)
```

### Logger

```python
from my_project.utils import get_logger

logger = get_logger('train')
logger.info('Training started...')
```

### Metrics

```python
from my_project.utils import compute_metrics

metrics = compute_metrics(predictions, labels)
# {'accuracy': 0.95, 'f1': 0.94, ...}
```

### Seed

```python
from my_project.utils import set_seed

set_seed(42)  # 设置所有随机种子
```

### Visualization

```python
from my_project.utils import plot_confusion_matrix, plot_loss_curve

plot_confusion_matrix(cm, save_path='cm.png')
plot_loss_curve(train_losses, val_losses, save_path='loss.png')
```