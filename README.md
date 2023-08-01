# ReGaP

This repository contains the ReGaPs used in our paper in YAML format and a binary that can be used to replicate the results of the paper.
The binary was built on the Ubuntu 18.04 subsystem for Windows.
Note that the binary is a bit bloated in size, which we understand may seem suspicious.
This is because the binary was built from a Python implementation of the ReGaP matcher, which was then compiled to C, together with all its dependencies, using Nuitka in order to introduce an additional layer of obfuscation.
This process introduces a lot of bloat in the resulting C code.
We would much rather make the source code available than having to go through all this process, but unfortunately we are not authorized to do so.
Nonetheless, any trust issues regarding the binary can be solved by running it contained within a virtual machine.

You can run the binary with default settings as follows:
```
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

The benchmarks used in the experimental evaluation can be obtained from [here](https://open-access-data.s3.eu-west-1.amazonaws.com/csn_python_cfgs.zip).

© 2023 OutSystems
