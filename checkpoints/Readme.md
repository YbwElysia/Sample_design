# Checkpoints

模型检查点存储目录。

## 目录结构

```
checkpoints/
├── pretrained/      # 预训练权重
├── experiments/     # 实验检查点
│   ├── exp1/
│   │   ├── best.pth
│   │   └── last.pth
│   └── exp2/
└── Readme.md
```

## 检查点格式

检查点保存为 `.pth` 文件，包含：

```python
checkpoint = {
    'epoch': epoch,
    'model': model.state_dict(),
    'optimizer': optimizer.state_dict(),
    'scheduler': scheduler.state_dict(),
    'best_acc': best_acc,
    'config': config,
}
```

## 加载检查点

```python
checkpoint = torch.load('checkpoints/best.pth')
model.load_state_dict(checkpoint['model'])
```

## 注意事项

- `.gitignore` 应忽略 `*.pth` 文件
- 预训练权重需要单独下载