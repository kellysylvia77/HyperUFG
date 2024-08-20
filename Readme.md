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
- a
- a
- a

The commands that we have used to execute the models and obtain the experimental results in the manuscript are detailed as follows:
