# Engine

训练引擎模块，包含训练、评估、推理的核心逻辑。

## 目录结构

```
engine/
├── __init__.py
├── trainer.py       # 训练器
├── evaluator.py     # 评估器
├── inferencer.py    # 推理器
└── Readme.md
```

## Trainer

训练器负责模型的训练循环：

```python
from my_project.engine import Trainer

trainer = Trainer(
    model=model,
    optimizer=optimizer,
    scheduler=scheduler,
    criterion=criterion,
    device=device,
)

trainer.train(
    train_loader=train_loader,
    val_loader=val_loader,
    epochs=100,
    checkpoint_dir='checkpoints/',
)
```

### 主要功能

- 训练/验证循环
- 梯度裁剪
- 混合精度训练 (AMP)
- 检查点保存/加载
- TensorBoard/WandB 日志
- 早停机制

## Evaluator

评估器负责模型评估：

```python
from my_project.engine import Evaluator

evaluator = Evaluator(model, device=device)
metrics = evaluator.evaluate(test_loader)
print(metrics)
```

### 支持的指标

- Accuracy
- Precision / Recall / F1
- Confusion Matrix
- AUC-ROC

## Inferencer

推理器负责单样本/批量推理：

```python
from my_project.engine import Inferencer

inferencer = Inferencer(model, device=device)
predictions = inferencer.predict(image_paths)
```