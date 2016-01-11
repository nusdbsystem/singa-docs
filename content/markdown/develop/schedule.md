
# Development Schedule

| Release | Module| Feature | Status |
|---------|---------|-------------|--------|
| 0.1 Sep     | Neural Network |1.1. Feed forward neural network, including CNN, MLP | done|
|         |          |1.2. RBM-like model, including RBM | done|
|         |                |1.3. Recurrent neural network, including standard RNN | done|
|         | Architecture   |1.4. One worker group on single node (with data partition)| done|
|         |                |1.5. Multi worker groups on single node using [Hogwild](http://www.eecs.berkeley.edu/~brecht/papers/hogwildTR.pdf)|done|
|         |                |1.6. Distributed Hogwild|done|
|         |                |1.7. Multi groups across nodes, like [Downpour](http://papers.nips.cc/paper/4687-large-scale-distributed-deep-networks)|done|
|         |                |1.8. All-Reduce training architecture like [DeepImage](http://arxiv.org/abs/1501.02876)|done|
|         |                |1.9. Load-balance among servers | done|
|         | Failure recovery|1.10. Checkpoint and restore |done|
|         | Tools|1.11. Installation with GNU auto tools| done|
|0.2 Dec | Neural Network |2.1. Feed forward neural network, including VGG model, CSV input layer, HDFS output layer, etc.||
|         |                |2.2. Recurrent neural network, including GRU and LSTM| |
|         | |2.3. Model partition and hybrid partition||
|         | Configuration   |2.4. Configuration helpers for popular models, e.g., CNN, MLP, Auto-encoders||
|         | Tools |2.5. Integration with Mesos for resource management||
|         |               |2.6. Prepare Docker images for deployment||
|         | Binding        |2.7. Python binding for major components ||
|         | GPU            |2.8. Single node with multiple GPUs ||
|0.3 Mar | GPU | 3.1 Multiple nodes, each with multiple GPUs||
|        |     | 3.2 Heterogeneous training using both GPU and CPU [CcT](http://arxiv.org/abs/1504.04343)||
|        | Phi | 3.3 Integration with Intel Phi co-processors (depending on the availability of the hardware)||
|         | Tools| 3.4 Deep learning as a service ||
|         | Applications | 3.5 Image classification, product search, etc.||
|         | Optimization | 3.6 ... ||

