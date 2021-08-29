# Nueral Style Transfer

This notebook is an attempt to recreate the work done by [Gatys et al. (2015)](https://arxiv.org/abs/1508.06576) to generate new images using a content and style image.

## Pre-Trained Convolutional Model

For this notebook, we will utilize a network architecture and set of weights that have already been developed and trained. Tensorflow offers a few famous options to choose from, but we will be using the VGG19 network from [Simonyan et al(2015)](https://arxiv.org/abs/1409.1556), which has been developed to understand the effect of a conv. net's depth on its performance. The VGG19 proved that deep networks (16-19 layers) can be highly effective with small (3x3) convolutional filters.

