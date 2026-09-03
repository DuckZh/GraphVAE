
# GraphVAE - 分子生成

基于 VAE 的分子图生成模型，参考 [GraphVAE: Towards Generation of Small Graphs Using Variational Autoencoders](https://link.springer.com/chapter/10.1007/978-3-030-01418-6_41) 实现。

## 环境要求

- Python 3.10+
- PyTorch 1.10+
- RDKit

## 安装

```bash
# 克隆仓库
git clone https://github.com/你的用户名/仓库名.git
cd 仓库名

# 安装依赖
pip install -r requirements.txt
```

## 训练

```bash
# 使用 ZINC 数据集（20 个节点以内）
python scripts/train_graphvae.py zinc-20 --max_num_nodes=20

# 使用 QM9 数据集
python scripts/train_graphvae.py qm9 --max_num_nodes=9

# 启用图匹配（MPM）
python scripts/train_graphvae.py zinc-20 --max_num_nodes=20 --mpm
```

## 生成分子

```bash
python scripts/sample_graphvae.py --weights weights/gvae_xxx.pth.pick
```

## 数据集

- **ZINC**: `zinc_leq20nodes.txt`，分子最多 20 个原子
- **QM9**: `qm9_smiles.txt`，分子最多 9 个原子

## 参考

- [GraphVAE 论文](https://link.springer.com/chapter/10.1007/978-3-030-01418-6_41)
- [原始实现](https://github.com/john-bradshaw/GraphVAE)