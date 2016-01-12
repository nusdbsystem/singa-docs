
# Development Schedule

| Release | Module| Feature | Status |
|---------|---------|-------------|--------|
| 0.1 Sep 2015     | Neural Network |1.1. Feed forward neural network, including CNN, MLP | done|
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
|0.2 Jan 2016 | Neural Network |2.1. Feed forward neural network, including AlexNet, cuDNN layers, etc.| done |
|         |                |2.2. Recurrent neural network, including GRULayer and BPTT|done |
|         | |2.3. Model partition and hybrid partition|done|
|         | Tools |2.4. Integration with Mesos for resource management|done|
|         |               |2.5. Prepare Docker images for deployment|done|
|         |               |2.6. Visualization of neural net and debug information |done|
|         | Binding        |2.7. Python binding for major components |done|
|         | GPU            |2.8. Single node with multiple GPUs |done|
|0.3 Mar 2016 | GPU | 3.1 Multiple nodes, each with multiple GPUs||
|        |     | 3.2 Heterogeneous training using both GPU and CPU [CcT](http://arxiv.org/abs/1504.04343)||
|         | Tools| 3.3 Deep learning as a service ||
|         | Binding| 3.4 Enhance Python binding for training||
|         |  | 3.5 Add R binding||
|         | Applications | 3.6 Image classification, product search, etc.||
|         | Optimization | 3.7  ||

