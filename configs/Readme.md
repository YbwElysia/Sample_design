# Configs

配置文件目录，用于存储训练、评估、推理的配置。

## 配置文件格式

使用 YAML 格式：

```yaml
# configs/default.yaml

# 数据配置
data:
  root: "data/"
  batch_size: 32
  num_workers: 4
  image_size: 224

# 模型配置
model:
  name: "resnet50"
  num_classes: 10
  pretrained: true

# 训练配置
train:
  epochs: 100
  lr: 1e-4
  weight_decay: 1e-4
  optimizer: "adamw"
  scheduler: "cosine"

# 评估配置
eval:
  metrics: ["accuracy", "f1", "precision", "recall"]

# 日志配置
logging:
  use_tensorboard: true
  use_wandb: false
  log_dir: "logs/"
```

## 使用配置文件

```python
import yaml

with open('configs/default.yaml') as f:
    config = yaml.safe_load(f)

# 访问配置
print(config['model']['name'])
```

## 配置覆盖

命令行参数可以覆盖配置文件：

```bash
python train.py --config configs/default.yaml --epochs 200 --lr 1e-3
```