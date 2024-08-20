# When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline
This is the official repository for the paper "When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline" (Submitted to AAAI 2025).
# New Benchmark Datasets
In the paper, we introduce 4 new heterophilous hypergraph datasets: actor, amazon-ratings, twitch-gamers, and pokec. You can find these datasets in the data folder. Note: These data have been widely used in semi-supervised node classification tasks. We construct hyperedge relationships by mining their co-occurrence information to make them suitable for hypergraph learning.
- Actor is an actor co-occurrences network within films, derived from the broader [Movie-Actor-Director-Writer Network](https://www.aminer.org/lab-datasets/soinf/).
- Amazon-ratings is a product co-purchasing network based on data from [SNAP Datasets](https://snap.stanford.edu/data/amazon-meta.html).
- Twitch-gamers is a twitch streaming platform network based on accounts provided by [SNAP Datasets](http://snap.stanford.edu/data/twitch_gamers.html).
- Pokec is an online social network based on the communication platform in Slovakia from [SNAP Datasets](https://snap.stanford.edu/data/soc-Pokec.html).

Our datasets come from different domains and exhibit a wide range of structual properties. We provide some statistics of our datasets in the table below:

# Reproducing Experiments
To ensure the reproduction of the results presented in the manuscript, we advise downloading the original codes for HGNN (Feng et al. 2019), UniGCNII (Huang and Yang 2021), ED-HNN (Wang et. al 2023) and SheafHyperGNN (Duta et al. 2023) from the following links:
- [HGNN](https://github.com/iMoonLab/HGNN) can be run by accessing its original source code. However, to reproduce the results, you need to replace the model instantiation with `dhg.models.HGNN`, which is supplied by the [DHG](https://github.com/iMoonLab/DeepHypergraph); 
- HyperGCN and UniGNN family (including UniGCN, UniSAGE, UniGAT, and UniGCNII) can be reproduced by the original codes from [UniGNNs](https://github.com/OneForward/UniGNN); 
- HyperND, AllDeepSets, AllSetTransformer and ED-HNN can be reproduced by the original codes from [ED-HNN](https://github.com/Graph-COM/ED-HNN);
- [SheafHyperGNN](https://github.com/IuliaDuta/sheaf_hypergraph_networks) can be reproduced by accessing its original source code. 

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
python
```
