# **CS230 Project**: Image Level Forgery Detection and Pixel Level Forgery Localization Network
***
Baseline model is from paper below. We therefore forked the framework from his and incorporated our model later on.
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
Technically speaking, the network is composed of two sub-networks as shown below:
  1. Image Manipulation Trace Feature Extractor: the feature extraction network for the image manipulation classification task, which is sensitive to different manipulation types, and encodes the image manipulation in a patch into a fixed dimension feature vector.
  2. Local Anomaly Detection Network: the anomaly detection network to compare a local feature against the dominant feature averaged from a local region, whose activation depends on how far a local feature deviates from the reference feature instead of the absolute value of a local feature.  
  
# Dependency
ManTraNet is written in Keras with the TensorFlow backend.

  - Keras: 2.2.0
  - TensorFlow: 1.8.0

Other versions might also work, but not tested.

# Contact
For any questions, please contact `dhtdean@stanford.edu, yitaoqiu@stanford.edu`
