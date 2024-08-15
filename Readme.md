# When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline
This is the official repository for the paper "When Hypergraph Meets Heterophily: New Benchmark Datasets and Baseline" (Submitted to AAAI 2025).
# New Benchmark Datasets
In the paper, we introduce 4 new heterophilous hypergraph datasets: actor, amazon-ratings, twitch-gamers, and pokec. You can find these datasets in the data folder. Note: These data have been widely used in semi-supervised node classification tasks. We construct hyperedge relationships by mining their co-occurrence information to make them suitable for hypergraph learning.
- Actor is an actor co-occurrences network within films, derived from the broader [Movie-Actor-Director-Writer Network](https://www.aminer.org/lab-datasets/soinf/).
- Amazon-ratings is a product co-purchasing network based on data from [SNAP Datasets](https://snap.stanford.edu/data/amazon-meta.html).
- Twitch-gamers is a twitch streaming platform network based on accounts provided by [SNAP Datasets](http://snap.stanford.edu/data/twitch_gamers.html).
- Pokec is an online social network based on the communication platform in Slovakia from [SNAP Datasets](https://snap.stanford.edu/data/soc-Pokec.html).

