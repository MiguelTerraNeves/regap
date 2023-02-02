# ReGaP

This repository contains the ReGaPs used in our paper in YAML format and a binary that can be used to replicate the results of the paper.
The binary was built on the Ubuntu 18.04 subsystem for Windows.

You can run the binary with default settings as follows:
```console
./main.bin <path to graphs file> <path to regap file>
```
This will run the ReGaP matcher with the given ReGaP for each graph in the given graphs file.
Information regarding the result of each matcher call is outputted to `stdout`.
GraphViz visualizations are generated for each match, with the graph nodes that match the non-wildcard nodes in the ReGaP highlighted in blue.
These visualizations are stored in the folder `_tmp/viz`.

The binary provides the following options:
- `-t`/`--matcher-timeout`: set the timeout for each call to the ReGaP matcher
- `--disable-node-merge`: disable the node merging preprocessing heuristic
- `--graphviz`: generate GraphViz visualizations for the input graphs and the ReGaP
