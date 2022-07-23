---
layout: post
title:  "Graph clustering (Node2Vec, Geometrical and Bisections)."
date:   2022-07-23 16:00:00 +0300
categories: Graph-clustering
usemathjax: true
---

In this short post I want to illustrate some graph clustering/partitioning ideas. 
First, I generate a random gabriel graph with 50 vertices 
(how to generate such graphs I described in the previous [post](https://mkrechetov.github.io/gabriel_graphs)).
First, we will need the following imports:

```
from geometric import random_gabriel_graph
import networkx as nx
import numpy as np
from gensim.models import Word2Vec
from sklearn.cluster import KMeans
import matplotlib.colors as mcolors
import matplotlib.pyplot as plt
```

And the code below gives us a graph.

```
G = random_gabriel_graph(50, seed=10)
points = nx.get_node_attributes(G, 'pos')
nx.draw_networkx_nodes(G, points, node_size=20)
nx.draw_networkx_edges(G, points, width=0.2)
plt.axis('off')
plt.savefig('gabrielGraph.png', dpi=300)
```

![gabriel_graph](../assets/clustering/gabrielGraph.png)


Node2Vec
=========

Geometrical
=========

Kernighan–Lin Partitioning
=========

