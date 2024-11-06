# When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline
This is the official repository for the paper "When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline" (AAAI2025 Submission-9978).
# Synthetic Hypergraphs

# New Benchmark Datasets
In this work, we introduce four new heterophilous hypergraph datasets: Actor, Amazon-ratings, Twitch-gamers, and Pokec. The datasets, which can be accessed in the accompanying folder, are constructed by mining co-occurrence information to establish hyperedge relationships, making them particularly suited for hypergraph learning methodologies. Their broad applicability in node classification tasks provides a valuable resource for researchers in the field.
- Actor: A hypergraph representing actor co-occurrences in films, derived from the larger **[Movie-Actor-Director-Writer Network](https://www.aminer.org/lab-datasets/soinf/)**.
- Amazon-ratings: A product co-purchasing network built from data in the **[SNAP Datasets](https://snap.stanford.edu/data/amazon-meta.html)**.
- Twitch-gamers: A network from the Twitch streaming platform, constructed using account information from **[SNAP Datasets](http://snap.stanford.edu/data/twitch_gamers.html)**.
- Pokec: An online social network from Slovakia, based on communication data in **[SNAP Datasets](https://snap.stanford.edu/data/soc-Pokec.html)**.

These datasets exhibit varying structural properties, offering a wide spectrum of challenges for hypergraph learning algorithms. A summary of the dataset statistics is provided in the following table.
|                Datasets               |    Actor    | Amazon-ratings | Twitch-gamers |    Pokec    |
|:-------------------------------------:|:-----------:|:--------------:|:-------------:|:-----------:|
|     Hypernodes, $\|\mathcal{V}\|$     |   16, 255   |     22, 299    |    16, 812    |   14, 998   |
|    Hyperedges, $\|\mathcal{E}\|$      |   10, 164   |     2, 090     |     2, 627    |    2, 406   |
|        Avg. hyperedge size            | 5.43 ± 2.65 |   3.10 ± 0.62  |  6.23 ± 3.37  | 2.29 ± 0.65 |
|             Features, $d$             |      50     |       111      |       7       |      65     |
|              Classes, $c$             |      3      |        5       |       2       |      2      |
| Node hom. ratio, $\mathcal{H}_{node}$ |    0.4815   |     0.4805     |     0.4893    |    0.4952   |
| Edge hom. ratio, $\mathcal{H}_{edge}$ |    0.4675   |     0.3677     |     0.4857    |    0.4529   |

# Implementing Classic HGNN Models on New Benchmark Datasets
To facilitate the reproduction of the experimental results reported in the paper, we recommend utilizing the original implementations of several hypergraph neural network models, including HGNN (Feng et al., 2019), UniGCNII (Huang and Yang, 2021), ED-HNN (Wang et al., 2023), and SheafHyperGNN (Duta et al., 2023). The following outlines the reproduction process for each model:
- **[HGNN](https://github.com/iMoonLab/HGNN)**: The original source code for HGNN can be used, with the model instantiation replaced by `dhg.models.HGNN`, as provided by the **[DHG](https://github.com/iMoonLab/DeepHypergraph)** library.
- HyperGCN and the UniGNN family (including UniGCN, UniSAGE, UniGAT, and UniGCNII) can be reproduced using the original codes from the **[UniGNN](https://github.com/OneForward/UniGNN)** repository.
- HyperND, AllDeepSets, AllSetTransformer, and ED-HNN can be reproduced using the original codes available from **[ED-HNN](https://github.com/Graph-COM/ED-HNN)**.
- **[SheafHyperGNN](https://github.com/IuliaDuta/sheaf_hypergraph_networks)**: The source code for SheafHyperGNN is accessible for reproducing its results. 

The commands that we have used to execute the models and obtain the experimental results in the manuscript are detailed as follows:

For HGNN:
```
python train.py --dataset='actor' --max_epoch=1000 --n_hid=256 --lr=1e-2 --weight_decay=5e-4 --drop_out=0.3
```

For HyperGCN:
```
python train.py --dataset='actor' --model_name='HyperGCN' --epochs=2000 --patience=100 --nlayer=2 --nhid=32 --nhead=8 --lr=1e-2 --wd=5e-4 --dropout=0.6
```

For UniGCNII:
```
python train.py --dataset='actor' --model_name='UniGCNII' --epochs=2000 --patience=100 --nlayer=2 --nhid=128 --nhead=8 --lr=3e-3 --wd=2e-4 --lamda=0.5 --dropout=0.1

```

For HyperND:
```
python train.py --dname='actor' --model_name='HyperND' --MLP_hidden=256 --Classifier_hidden=256 --lr=1e-3 --wd=5e-4 --dropout=0.5
```

For AllDeepSets:
```
python train.py --dname='actor' --model_name='AllDeepSets' --MLP_hidden=512 --Classifier_hidden=512 --lr=1e-3 --wd=5e-4 --dropout=0.5
```

For AllSetTransformer:
```
python train.py --dname='actor' --model_name='AllSetTransformer' --MLP_hidden=256 --Classifier_hidden=256 --lr=1e-3 --wd=5e-4 --dropout=0.5
```

For ED-HNN:
```
python train.py --dname='actor' --model_name='EDGNN' --edconv_type='EquivSet' --MLP_hidden=256 --Classifier_hidden=256 --lr=1e-3 --wd=5e-4 --dropout=0.5
```

For SheafHyperGNN:
```
python train.py --dname='actor' --model_name='SheafHyperGCNDiag' --MLP_hidden=256 --Classifier_hidden=256 --lr=1e-2 --wd=5e-4 --dropout=0.5
```
