# ResNet-34 Architecture

ResNet-34, short for Residual Network with 34 layers, is a deep convolutional neural network (CNN) designed to address the vanishing gradient problem that hampers the training of deep networks. Introduced by Kaiming He et al. in their paper ["Deep Residual Learning for Image Recognition"](https://arxiv.org/abs/1512.03385), ResNet-34 utilizes "skip connections" or "residual connections" which allow for easier gradient flow through the network.

## Key Features

### Residual Blocks

Instead of learning the underlying mapping, residual blocks learn the residuals (or the difference) between the input and output. This is done by introducing shortcut connections that skip one or more layers. 

A residual block typically has the following structure:
- Two 3x3 convolutional layers.
- Batch normalization (BN) after each convolutional layer.
- ReLU activation function after each BN.
- A shortcut connection that adds the input of the block to the output.

### Skip Connections

These connections bypass one or more layers by performing identity mapping and then adding the output to the skipped layer’s output. This helps mitigate the vanishing gradient problem by allowing gradients to flow directly through the network.

### Network Depth and Layer Composition

ResNet-34 is composed of 34 layers, which include:
- Convolutional Layers: Perform feature extraction by applying filters to the input.
- Pooling Layers: Reduce the spatial dimensions (height and width) of the input, keeping the depth the same.
- Fully Connected Layers: Perform classification tasks based on the extracted features.

### Layer Breakdown

1. Initial Convolution and Pooling:
   - 1 Convolution layer with 64 filters of size 7x7, stride 2.
   - 1 MaxPooling layer with size 3x3, stride 2.

2. Residual Blocks:
   - Conv2_x: 3 blocks, each with 2 convolutional layers of size 3x3 and 64 filters.
   - Conv3_x: 4 blocks, each with 2 convolutional layers of size 3x3 and 128 filters. The first block uses a convolutional layer with stride 2 to reduce spatial dimensions.
   - Conv4_x: 6 blocks, each with 2 convolutional layers of size 3x3 and 256 filters. The first block uses a convolutional layer with stride 2 to reduce spatial dimensions.
   - Conv5_x: 3 blocks, each with 2 convolutional layers of size 3x3 and 512 filters. The first block uses a convolutional layer with stride 2 to reduce spatial dimensions.

3. Final Layers:
   - 1 Average Pooling layer with size 7x7.
   - 1 Fully Connected layer with 1000 neurons (for classification into 1000 classes).
