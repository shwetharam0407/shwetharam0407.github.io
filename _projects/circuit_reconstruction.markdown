---
layout: page
title: Circuit Reconstruction from EM Images
description: Deep Learning (CS 291K) Course Project
img: /assets/projects/circuit_reconstruction/img/test_results.png
---

Automatic reconstruction of neurons and neuronal connectivity is a central problem in neuroanatomy. This is necessary to efficiently map 3D brain structure and connectivity. We address the problem of 2D segmentation of ssTEM image stacks which is often the first step in the pipeline. 


<div class="img">
<img class="col three left" src="{{ site.baseurl }}/assets/projects/circuit_reconstruction/img/test_results.png" alt="" title="example image"/>
</div>
<div class="col three caption">
    2D Neuron segmentation - test results
</div>

To segment biological neuron membranes, we use artificial neural network as a pixel classifier. A Convolutional Neural Network takes raw pixel values in a square window centered around each pixel as input and outputs the probability of that pixel being a non-membrane. The label of each pixel (membrane or non- membrane) is predicted by postprocessing the output of our Convolutional Neural Network.


<div class="img">
<img class="col three left" src="{{ site.baseurl }}/assets/projects/circuit_reconstruction/img/convnet_architecture.png" alt="" title="example image"/>
</div>
<div class="col three caption">
    ConvNet Architecture
</div>

---
### Results
- Training Accuracy: 77.45%
- Validation Accuracy: 72.78%
- Test Accuracy: 69.32%

Please see [report](/assets/projects/circuit_reconstruction/291k-circuit-reconstruction.pdf) and [slides](/assets/projects/circuit_reconstruction/circuit_reconstruction.pdf) for more details.
