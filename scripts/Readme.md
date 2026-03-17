# Scripts

常用脚本目录，包含训练、测试、数据处理等脚本。

## 脚本列表

| 脚本 | 说明 |
|------|------|
| `train.sh` | 训练脚本 |
| `test.sh` | 测试脚本 |
| `download_data.sh` | 数据下载脚本 |
| `preprocess.py` | 数据预处理脚本 |

## 使用示例

```bash
# 训练
bash scripts/train.sh

# 测试
bash scripts/test.sh

# 数据预处理
python scripts/preprocess.py --input raw_data/ --output processed_data/
```

## 后台运行

```bash
# 使用 nohup 后台运行
nohup bash scripts/train.sh > logs/train.log 2>&1 &

# 查看日志
tail -f logs/train.log
```