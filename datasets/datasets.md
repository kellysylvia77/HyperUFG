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

Note: We constructed hyperedges for each dataset based on the co-occurrence relationship, and features is embedded from the attribute information. Other information of the dataset naturally exists in its source data.
