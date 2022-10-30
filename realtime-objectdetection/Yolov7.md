## Introduction
- MCUNet and NanoDet focused on producting low-power single-chip and improving the inference speed on edge CPU
- YOLOX and YOLOR focused on improving the inference speed of various GPUs.
- real-time object detectors based on CPU, MobileNet/ShuffleNet/GhostNet
- for GPU, ResNet/DarkNet/DLA/CSPNet
- Yolov7 is efficient on from mobile GPU(edge) to GPU(Cloud)
- Yolov7 focused on both architecture optimizaton and the optimization of training process
- The trend of network training and object detection is model re-parameterization and dynamic label assignment
- Above two concepts(re-parameterizartion and dynamic label assignment) generated new issues.
<Contributions>
- improve the detection accuracy without increasing the inference cost
- address two issues
    (1) how re-parameterized module replaces original module
    (2) how dynamic label assignment strategy deals with assignment to difference output layers
    (3) extend and compound scaling methods

## Related Works
### real-time object detectors
- state of the art real-time object detectors are based on YOLO and FCOS
  [requirements]
  - a faster and stronger network architecture
  - a more effective feature integration method
  - a more accurate detection method
  - a more robust loss function
  - a more efficient label assignment method
  - a more efficient training method

### Model re-parameterization
- model re-parameterization technique can be regarded as an ensemble technique
    (1)module-level ensemble
        train multiple identical models with different training data and average weights of multiple trained models.(more popular)
    (2)model-level ensemble
        a weightned average of the weight of models at different iteration number
### Model scaling
- a way to scale up or down an already designed model and make it fit in different computing devices
    [scalingfactors]
    - resolution(size of input image)
    - depth(number of layer)
    - width(number of channel)
    - stage(number of feature pyramid)
    [tradeoff]
    - network parameters
    - computation
    - inference speed
    - accuracy


## Architecture
### Extended efficient layer aggregation networks
- memory access cost/ analyze the influence of the input/output channel ratio, the number of branches of the architecture, and the element-wise operation on the network inference speed, the number of elements in the output tensors of convolutional layers
- gradient path = enable the weight of different layers to learn more diverse features
- features of previous efficient network architecture
    - cross stage connection
    - stacked computation blocks
    - expansion
- yolov7
[features]
    - expand cardinality
    - shuffle cardinality
    - merge cardinality

### Model scaling for concatenation-base models
- concatenated-based models cannot analyze scaling up depth and width separately.
- propose corresponding compound model. Taking scaling up depth as an example,  when we scale up depth in computational block, we must calculate the change of the output channel of that block.

## Trainable bug-of-freebies
### Planned re-parameterized convolution
- find the better combinatins of RepConv, RepConvN(RepConv without identity connections), Conv
- RepConv(3 X 3convolution, 1 X 1 convolution , identity connection)
[reference] RepVGG(https://arxiv.org/abs/2101.03697)

### Coarse for auxiliary and fine for lead loss
- DeepSupervision is to add extra auxiliary head in the middle layer and the shallow network weights with assistant loss as the guide
- Two label assigners were propsed
    - Lead head guided label assigner(generate soft labels on optimization process)
    - Coarse-to-fine lead head guided label assigner(generate 2 label, coarse label(positive sample assignment/restrictions in decoder)/fine label)

strategy for label assignment
[reference] OTA(Optimal Transport Assignment)


### Supplemently
[Deep Supervision](https://uiiurz1.hatenablog.com/entry/2018/12/20/193741)


