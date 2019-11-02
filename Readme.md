# **IFDN**: Image forgery detection netwrok

***
This is image forgery detection network adapted from ManTraNet (See citation below). We intend to improve the network by allowing for detection of style transferred detection. 

```
  @inproceedings{Wu2019ManTraNet,
      title={ManTra-Net: Manipulation Tracing Network For Detection And Localization of Image ForgeriesWith Anomalous Features},
      author={Yue Wu, Wael AbdAlmageed, and Premkumar Natarajan},
      journal={The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
      year={2019}
  }
```

***

# Overview
Model developed based on ManTraNet, with improvement on neural style transferred detection.
This is an end-to-end image forgery detection and localization solution, which means it takes a testing image as input, and predicts pixel-level forgery likelihood map as output.

  1. **Simplicity**: ManTraNet needs no extra pre- and/or post-processing
  2. **Fast**: ManTraNet puts all computations in a single network, and accepts an image of arbitrary size.
  3. **Robustness**: ManTraNet does not rely on working assumptions other than *the local manipulation assumption*, i.e. some region in a testing image is modified differently from the rest.

Technically speaking, IFDN is composed of two sub-networks as shown below:
  1. Image Manipulation Trace Feature Extractor: the feature extraction network for the image manipulation classification task, which is sensitive to different manipulation types, and encodes the image manipulation in a patch into a fixed dimension feature vector.
  2. Local Anomaly Detection Network: the anomaly detection network to compare a local feature against the dominant feature averaged from a local region, whose activation depends on how far a local feature deviates from the reference feature instead of the absolute value of a local feature.  

![ManTraNet](https://github.com/ISICV/ManTraNet/blob/master/data/ManTraNet-overview.png)

# Extension
ManTraNet is pretrained with all synthetic data. To prevent overfitting, we
1. Pretrain the Image Manipulation Classification ([385 classes](https://github.com/ISICV/ManTraNet/blob/master/data/IMC385.png)) task to obtain the Image *Manipulation Trace Feature Extractor*
2. Train ManTraNet with four types of synthetic data, i.e. copy-move, splicing, removal, and enhancement, style transferred

# Dependency
ManTraNet is written in Keras with the TensorFlow backend.

  - Keras: 2.2.0
  - TensorFlow: 1.8.0

Other versions might also work, but not tested.

# Demo
One may simply download the repo and play with the provided ipython notebook.

Alternatively, one may play with the inference code using [this google colab link](https://colab.research.google.com/drive/1ai4kVlI6w9rREqqYnTfpk3gM3YX9k-Ek).

# Contact
For any questions, please contact `dhtdean@stanford.edu, yitaoqiu@stanford.edu`
